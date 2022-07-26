# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

- Ruby version

- System dependencies

- Configuration

- Database creation

- Database initialization

- How to run the test suite

- Services (job queues, cache servers, search engines, etc.)

- Deployment instructions

- ...

pc@pc:~/Desktop/Ruby*t_6/blog_2$ rails c
Loading development environment (Rails 6.0.5.1)
(0.4ms) SELECT sqlite_version(*)
3.0.0 :002 > Article.create(title: "First Title Article" ,description: "First T"
3.0.0 :002 > Article.all
=> #<ActiveRecord::Relation []>
3.0.0 :003 > Article.create(title: "First Title Article" ,description: "First Title Description")
(0.1ms) begin transaction
Article Create (0.3ms) INSERT INTO "articles" ("title", "description", "created*at", "updated_at") VALUES (?, ?, ?, ?) [["title", "First Title Article"], ["description", "First Title Description"], ["created_at", "2022-07-26 07:05:01.731847"], ["updated_at", "2022-07-26 07:05:01.731847"]]
(2.6ms) commit transaction
\_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">
3.0.0 :004 > Article.all
Article Load (0.2ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">]>
=> #<Article id: nil, title: nil, description: nil, created*at: nil, updated_at: nil>
3.0.0 :006 > article.title ="Second Title Article"
3.0.0 :007 > article.description ="Description of Second Article"
3.0.0 :008 > article
=> #<Article id: nil, title: "Second Title Article", description: "Description of Second Article", created_at: nil, updated_at: nil>
3.0.0 :009 > article.save
(0.1ms) begin transaction
Article Create (0.3ms) INSERT INTO "articles" ("title", "description", "created_at", "updated_a
d Article"], ["created_at", "2022-07-26 07:24:06.415371"], ["updated_at", "2022-07-26 07:24:06.415371"]]
(2.2ms) commit transaction
=> true
3.0.0 :010 > Article.all
Article Load (0.3ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First T
e id: 2, title: "Second Title Article", description: "Description of Second Article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 07:24:06">]>
=> #<Article id: 2, title: "Second Title Article", description: "Description of Second Article", 3.0.0 :012 > article = Article.new(title: "Third Title Article" , description: "Third Title Descri
ption")
=> #<Article id: nil, title: "Third Title Article", description: "Third Title Description",...
3.0.0 :013 > article.save
(0.1ms) begin transaction
Article Create (0.4ms) INSERT INTO "articles" ("title", "description", "created*at", "updated_at") VALUES (?, ?, ?, ?) [["title", "Third Title Article"], ["description", "Third Title Description"], ["created_at", "2022-07-26 07:35:32.401065"], ["updated_at", "2022-07-26 07:35:32.401065"]]
(2.6ms) commit transaction
=> true
3.0.0 :014 > Article.all
Article Load (0.2ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "Description of Second Article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 07:24:06">, #<Article id: 3, title: "Third Title Article", description: "Third Title Description", created_at: "2022-07-26 07:35:32", updated_at: "2022-07-26 07:35:32">]>
=> #<Article id: 3, title: "Third Title Article", description: "Third Title Description", created*at: "2022-07-26 07:35:32", updated_at: "2022-07-26 07:35:32">
3.0.0 :016 > exit
pc@pc:~/Desktop/Ruby_t_6/blog_2$ git add .
pc@pc:~/Desktop/Ruby_t_6/blog_2$ git commit -m "Article Was Created and hits in the database"
[master b28e9bd] Article Was Created and hits in the database
1 file changed, 2 insertions(+)
create mode 100644 app/models/article.rb
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Total 5 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:SanthoshRam3/blog_2.git
4015f85..b28e9bd master -> master
pc@pc:~/Desktop/Ruby_t_6/blog_2$ rails c
Running via Spring preloader in process 9774
Loading development environment (Rails 6.0.5.1)
3.0.0 :001 > Article.all
Article Load (0.2ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First T
e id: 2, title: "Second Title Article", description: "Description of Second Article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 07:24:06">, #<Article id: 3, title: "Third Title Article", description: "Third Title Description", created_at: "2022-07-26 07:35:32", updated_at: "2022-07-26 07:35:32">]>
3.0.0 :002 > Article.find(2)
Article Load (0.3ms) SELECT "articles"._ FROM "articles" WHERE "articles"."id" = ? LIMIT ? [["id", 2], ["LIMIT", 1]]
created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 07:24:06">
3.0.0 :003 > Article.first
Article Load (0.2ms) SELECT "articles"._ FROM "articles" ORDER BY "articles"."id" ASC LIMIT ? [["LIMIT", 1]]
\_at: "2022-07-26 07:05:01", updated*at: "2022-07-26 07:05:01">
3.0.0 :004 > Article.last
Article Load (0.2ms) SELECT "articles".* FROM "articles" ORDER BY "articles"."id" DESC LIMIT ? [["LIMIT", 1]]
=> #<Article id: 3, title: "Third Title Article", description: "Third Title Description", created
3.0.0 :005 > articles=Article.all
Article Load (0.2ms) SELECT "articles"._ FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "F...
Article Load (0.1ms) SELECT "articles"._ FROM "articles" LIMIT ? [["LIMIT", 11]]
itle Description", created*at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Articl
"2022-07-26 07:24:06", updated_at: "2022-07-26 07:24:06">, #<Article id: 3, title: "Third Title Ar
22-07-26 07:35:32">]>
3.0.0 :007 > article.description
Traceback (most recent call last):
1: from (irb):7:in `<main>' NameError (undefined local variable or method `article' for main:Object)
Did you mean? articles
3.0.0 :008 > article.title = "Sample Article"
2: from (irb):7:in `<main>' 1: from (irb):8:in `rescue in <main>'
NameError (undefined local variable or method `article' for main:Object) Did you mean? articles 3.0.0 :009 > article= Article.find(2) Article Load (0.2ms) SELECT "articles".* FROM "articles" WHERE "articles"."id" = ? LIMIT ? [[" => #<Article id: 2, title: "Second Title Article", description: "Description of Second Arti... 3.0.0 :010 > article.title => "Second Title Article" 3.0.0 :011 > article.description => "Description of Second Article" 3.0.0 :012 > article.description="edited - Description of second article" => "edited - Description of second article" 3.0.0 :013 > articles => #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "Description of Second Article", created_at: ticle", description: "Third Title Description", created_at: "2022-07-26 07:35:32", updated_at: "2022-07-26 07:35:32">]> (0.1ms) begin transaction Article Update (0.4ms) UPDATE "articles" SET "description" = ?, "updated_at" = ? WHERE "articles"."id" = ? [["description", "edited - Description of second article"], ["updated_at", "2022-07-26 08:22:39.722136"], ["id", 2]] (2.2ms) commit transaction 3.0.0 :015 > articles Article Load (0.2ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]] => #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "edited - Description of second article", cre 3.0.0 :016 > article = Article.last [["LIMIT", 1]] => #<Article id: 3, title: "Third Title Article", description: "Third Title Description", c... 3.0.0 :017 > article => #<Article id: 3, title: "Third Title Article", description: "Third Title Description", created_at: "2022-07-26 07:35:32", updated_at: "2022-07-26 07:35:32"> 3.0.0 :019 > articles Article Load (0.2ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]] itle Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "edited - Description of second article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 08:22:39">]> 3.0.0 :020 > 3.0.0 :021 > 3.0.0 :022 > => #<Article id: nil, title: nil, description: nil, created_at: nil, updated_at: nil> 3.0.0 :024 > article.save (0.1ms) begin transaction Article Create (0.3ms) INSERT INTO "articles" ("created_at", "updated_at") VALUES (?, ?) [["created_at", "2022-07-26 09:55:37.426734"], ["updated_at", "2022-07-26 09:55:37.426734"]] (2.4ms) commit transaction => true 3.0.0 :026 > 3.0.0 :027 > 3.0.0 :028 > 3.0.0 :029 > 3.0.0 :030 > reload! Reloading... 3.0.0 :031 > article = Article.new Traceback (most recent call last): 1: from (irb):31:in `<main>'
SyntaxError (/home/pc/Desktop/Ruby_t_6/blog_2/app/models/article.rb:2: syntax error, unexpected symbol literal, expecting `do' or '{' or '(') validates :title , presence :true ^ (0.1ms) SELECT sqlite_version(*) Article Load (0.3ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]] => #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "edited - Description of second article", cre escription: nil, created_at: "2022-07-26 09:55:37", updated_at: "2022-07-26 09:55:37">]> 3.0.0 :033 > Article.destroy(4) Traceback (most recent call last): 1: from (irb):33:in `<main>'
SyntaxError (/home/pc/Desktop/Ruby_t_6/blog_2/app/models/article.rb:2: syntax error, unexpected sy
validates :title , presence :true
3.0.0 :034 > Article.destroy(4)
Article Load (0.1ms) SELECT "articles".* FROM "articles" WHERE "articles"."id" = ? LIMIT ? [["id", 4], ["LIMIT", 1]]
(0.1ms) begin transaction
Article Destroy (0.3ms) DELETE FROM "articles" WHERE "articles"."id" = ? [["id", 4]]
=> #<Article id: 4, title: nil, description: nil, created*at: "2022-07-26 09:55:37", updated_at: "2022-07-26 09:55:37">
3.0.0 :035 > articles
Article Load (0.2ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Articl
ated_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 08:22:39">]>
3.0.0 :036 > articles
Article Load (0.1ms) SELECT "articles"._ FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "edited - Description of second article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 08:22:39">]>
=> #<Article id: nil, title: nil, description: nil, created_at: nil, updated_at: nil>
3.0.0 :038 > article.save
(0.1ms) begin transaction
Article Create (0.5ms) INSERT INTO "articles" ("created_at", "updated_at") VALUES (?, ?) [["created_at", "2022-07-26 10:00:19.489280"], ["updated_at", "2022-07-26 10:00:19.489280"]]
=> true
Article Load (0.2ms) SELECT "articles"._ FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First T
e id: 2, title: "Second Title Article", description: "edited - Description of second article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 08:22:39">, #<Article id: 5, title: nil, description: nil, created_at: "2022-07-26 10:00:19", updated_at: "2022-07-26 10:00:19">]>
3.0.0 :040 > Article.destroy(5)
Article Load (0.2ms) SELECT "articles"._ FROM "articles" WHERE "articles"."id" = ? LIMIT ? [["id", 5], ["LIMIT", 1]]
Article Destroy (0.5ms) DELETE FROM "articles" WHERE "articles"."id" = ? [["id", 5]]
(2.5ms) commit transaction
"2022-07-26 10:00:19">
3.0.0 :041 > articles
Article Load (0.2ms) SELECT "articles"._ FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Articl
ated_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 08:22:39">]>
3.0.0 :042 > article = Article.new
3.0.0 :043 > reload!
Reloading...
=> true
3.0.0 :044 > article = Article.new
Traceback (most recent call last):
1: from (irb):44:in `<main>' mbol literal, expecting `do' or '{' or '(')
validates :title , presence :true
3.0.0 :045 > reload!
Reloading...
3.0.0 :046 > article = Article.new
3: from (irb):46:in `<main>' 2: from app/models/article.rb:1:in `<main>'
1: from app/models/article.rb:2:in `<class:Article>' 3.0.0 :047 > reload! => true 3.0.0 :048 > article = Article.new 1: from (irb):48:in `<main>'
SyntaxError (/home/pc/Desktop/Ruby*t_6/blog_2/app/models/article.rb:2: syntax error, unexpected sy
validates :title , presence :true
^
Reloading...
3.0.0 :050 > article = Article.new
(0.1ms) SELECT sqlite_version(*)
3.0.0 :051 > article.save
=> false
=> #<ActiveModel::Errors:0x00007f58f1074350 @base=#<Article id: nil, title: nil, description: nil
error=>:blank}]}>
3.0.0 :053 > article.errors.full*messages
=> ["Title can't be blank"]
Reloading...
3.0.0 :055 > article = Article.new
(0.1ms) SELECT sqlite_version(*)
3.0.0 :056 > article.errors
=> #<ActiveModel::Errors:0x00007f58f0688bc0 @base=#<Article id: nil, title: nil, description: nil
3.0.0 :057 > article.errors.full*messages
3.0.0 :058 > reload!
Reloading...
3.0.0 :059 > article = Article.new
=> #<Article id: nil, title: nil, description: nil, created_at: nil, updated_at: nil>
=> false
3.0.0 :061 > article.errors
=> #<ActiveModel::Errors:0x00007f58f0fb53b0 @base=#<Article id: nil, title: nil, description: nil, created_at: nil, updated_at: nil>, @messages={:title=>["can't be blank"], :description=>["can't be blank"]}, @details={:title=>[{:error=>:blank}], :description=>[{:error=>:blank}]}>
3.0.0 :062 > article.errors.full_messages
=> ["Title can't be blank", "Description can't be blank"]
Reloading...
=> true
3.0.0 :064 > article = Article.new(title: "a", description:"b")
(0.1ms) SELECT sqlite_version(*)
=> #<Article id: nil, title: "a", description: "b", created*at: nil, updated_at: nil>
3.0.0 :065 > article.save
=> false
=> ["Title is too short (minimum is 6 characters)", "Description is too short (minimum is 10 characters)"]
3.0.0 :067 > article.title ="This should pass validations"
=> "This should pass validations"
3.0.0 :068 > article.description ="Edited Article Description"
=> "Edited Article Description"
3.0.0 :069 > article.save
Article Create (0.3ms) INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?) [["title", "This should pass validations"], ["description", "Edited Article Description"], ["created_at", "2022-07-26 10:49:38.198692"], ["updated_at", "2022-07-26 10:49:38.198692"]]
(2.6ms) commit transaction
=> true
3.0.0 :070 > articles
Article Load (0.3ms) SELECT "articles".* FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "edited - Description of second article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 08:22:39">, #<Article id: 6, title: "This should pass validations", description: "Edited Article Description", created_at: "2022-07-26 10:49:38", updated_at: "2022-07-26 10:49:38">]>
3.0.0 :071 > articles
Article Load (0.2ms) SELECT "articles".\* FROM "articles" LIMIT ? [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Article id: 1, title: "First Title Article", description: "First Title Description", created_at: "2022-07-26 07:05:01", updated_at: "2022-07-26 07:05:01">, #<Article id: 2, title: "Second Title Article", description: "edited - Description of second article", created_at: "2022-07-26 07:24:06", updated_at: "2022-07-26 08:22:39">, #<Article id: 6, title: "This should pass validations", description: "Edited Article Description", created_at: "2022-07-26 10:49:38", updated_at: "2022-07-26 10:49:38">]>
3.0.0 :072 > exit
pc@pc:~/Desktop/Ruby_t_6/blog_2$ git add .
pc@pc:~/Desktop/Ruby_t_6/blog_2$ git commit -m "Validations CRUD operations and showing articles in the routes"
[master eaf5bd4] Validations CRUD operations and showing articles in the routes
5 files changed, 11 insertions(+), 2 deletions(-)
delete mode 100644 app/controllers/article_controller.rb
create mode 100644 app/controllers/articles_controller.rb
create mode 100644 app/views/articles/show.html.erb
pc@pc:~/Desktop/Ruby_t_6/blog_2$ git push origin master
Enumerating objects: 20, done.
Counting objects: 100% (20/20), done.
Delta compression using up to 4 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (12/12), 1.25 KiB | 1.25 MiB/s, done.
Total 12 (delta 4), reused 0 (delta 0)
remote: Resolving deltas: 100% (4/4), completed with 4 local objects.
To github.com:SanthoshRam3/blog_2.git
b28e9bd..eaf5bd4 master -> master
pc@pc:~/Desktop/Ruby_t_6/blog_2$
