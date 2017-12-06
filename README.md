
## Bashの実行ログ

```
iso1:~/workspace $ git clone git@github.com:iso-1/lecture-1206.git
Cloning into 'lecture-1206'...
Warning: Permanently added 'github.com,192.30.253.112' (RSA) to the list of known hosts.
remote: Counting objects: 95, done.
remote: Compressing objects: 100% (79/79), done.
remote: Total 95 (delta 2), reused 95 (delta 2), pack-reused 0
Receiving objects: 100% (95/95), 38.69 KiB | 12.89 MiB/s, done.
Resolving deltas: 100% (2/2), done.
iso1:~/workspace $ cd lecture-1206/asagao/
iso1:~/workspace/lecture-1206/asagao (master) $ bundle install
The latest bundler is 1.16.0, but you are currently running 1.15.4.
To update, run `gem install bundler`
The git source `git://github.com/flori/json.git` uses the `git` protocol, which transmits data without encryption. Disable this warning with `bundle config git.allow_insecure true`, or switch to the `https` protocol to keep your data secure.
Warning: the running version of Bundler (1.15.4) is older than the version that created the lockfile (1.16.0). We suggest you upgrade to the latest version of Bundler by running `gem install bundler`.
Using rake 12.2.1
Using concurrent-ruby 1.0.5
Using minitest 5.10.3
Using thread_safe 0.3.6
Using builder 3.2.3
Using erubis 2.7.0
Using mini_portile2 2.3.0
Using crass 1.0.2
Using rack 1.6.8
Using mini_mime 0.1.4
Using arel 6.0.4
Using debug_inspector 0.0.3
Using bundler 1.15.4
Using byebug 9.1.0
Using coffee-script-source 1.8.0
Using execjs 2.7.0
Using thor 0.20.0
Using ffi 1.9.18
Using multi_json 1.12.2
Using json 1.8.6 from git://github.com/flori/json.git (at v1.8@7f4cfd8)
Using rb-fsevent 0.10.2
Using rdoc 4.3.0
Using tilt 2.0.8
Using sqlite3 1.3.13
Using turbolinks-source 5.0.3
Using i18n 0.9.1
Using tzinfo 1.2.4
Using nokogiri 1.8.1
Using rack-test 0.6.3
Using sprockets 3.7.1
Using mail 2.7.0
Using binding_of_caller 0.7.3
Using coffee-script 2.4.1
Using uglifier 3.2.0
Using rb-inotify 0.9.10
Using sdoc 0.4.2
Using turbolinks 5.0.1
Using activesupport 4.2.10
Using loofah 2.1.1
Using sass-listen 4.0.0
Using rails-deprecated_sanitizer 1.0.3
Using globalid 0.4.1
Using activemodel 4.2.10
Using jbuilder 2.7.0
Using spring 2.0.2
Using rails-html-sanitizer 1.0.3
Using sass 3.5.3
Using rails-dom-testing 1.0.8
Using activejob 4.2.10
Using activerecord 4.2.10
Using actionview 4.2.10
Using actionpack 4.2.10
Using actionmailer 4.2.10
Using railties 4.2.10
Using sprockets-rails 3.2.1
Using coffee-rails 4.1.1
Using jquery-rails 4.3.1
Using rails 4.2.10
Using sass-rails 5.0.6
Using web-console 2.3.0
Bundle complete! 15 Gemfile dependencies, 60 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
iso1:~/workspace/lecture-1206/asagao (master) $ cd bin/rake db:create
bash: cd: bin/rake: Not a directory
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rake db:create
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rake db:create
db/development.sqlite3 already exists
db/test.sqlite3 already exists
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rails g model member
      invoke  active_record
      create    db/migrate/20171206013019_create_members.rb
      create    app/models/member.rb
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rake db:migrate
== 20171206013019 CreateMembers: migrating ====================================
-- create_table(:members)
   -> 0.0009s
== 20171206013019 CreateMembers: migrated (0.0010s) ===========================

iso1:~/workspace/lecture-1206/asagao (master) $ bin/rails c
Loading development environment (Rails 4.2.10)
2.4.0 :001 > Member.count
   (0.2ms)  SELECT COUNT(*) FROM "members"
 => 0 
2.4.0 :002 > menber = Member.new
 => #<Member id: nil, number: nil, name: nil, full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: nil, updated_at: nil> 
2.4.0 :003 > member = Member.new                                      
 => #<Member id: nil, number: nil, name: nil, full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: nil, updated_at: nil> 
2.4.0 :004 > member.number = 1
 => 1 
2.4.0 :005 > member.name = "Taro"
 => "Taro" 
2.4.0 :006 > member.save
   (0.2ms)  begin transaction
  SQL (3.2ms)  INSERT INTO "members" ("number", "name", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["number", 1], ["name", "Taro"], ["created_at", "2017-12-06 01:35:41.524743"], ["updated_at", "2017-12-06 01:35:41.524743"]]
   (8.9ms)  commit transaction
 => true 
2.4.0 :007 > Member.first
  Member Load (0.4ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
 => #<Member id: 1, number: 1, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:35:41", updated_at: "2017-12-06 01:35:41"> 
2.4.0 :008 > pp Member.first
  Member Load (0.3ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
#<Member:0x000000052fbd40
 id: 1,
 number: 1,
 name: "Taro",
 full_name: nil,
 email: nil,
 birthday: nil,
 gender: 0,
 administrator: false,
 created_at: Wed, 06 Dec 2017 01:35:41 UTC +00:00,
 updated_at: Wed, 06 Dec 2017 01:35:41 UTC +00:00>
 => #<Member id: 1, number: 1, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:35:41", updated_at: "2017-12-06 01:35:41"> 
2.4.0 :009 > member = Member.first
  Member Load (0.4ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
 => #<Member id: 1, number: 1, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:35:41", updated_at: "2017-12-06 01:35:41"> 
2.4.0 :010 > member.number = 41
 => 41 
2.4.0 :011 > member.save
   (0.2ms)  begin transaction
  SQL (0.3ms)  UPDATE "members" SET "number" = ?, "updated_at" = ? WHERE "members"."id" = ?  [["number", 41], ["updated_at", "2017-12-06 01:36:58.143007"], ["id", 1]]
   (6.8ms)  commit transaction
 => true 
2.4.0 :012 > Member.first
  Member Load (0.4ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
 => #<Member id: 1, number: 41, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:35:41", updated_at: "2017-12-06 01:36:58"> 
2.4.0 :013 > 
iso1:~/workspace/lecture-1206/asagao (master) $ mkdir -p db/seeds/development
iso1:~/workspace/lecture-1206/asagao (master) $ touch db/seeds/development/members.rb
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rake db:reset
bin/rake db-- create_table("members", {:force=>:cascade})
   -> 0.0243s
-- initialize_schema_migrations_table()
   -> 0.0817s
-- create_table("members", {:force=>:cascade})
   -> 0.0239s
-- initialize_schema_migrations_table()
   -> 0.0351s
Creating members...
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rake db:seed
Creating members...
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rails c
Loading development environment (Rails 4.2.10)
2.4.0 :001 > pp Member.first
  Member Load (0.2ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
#<Member:0x000000035795b0
 id: 1,
 number: 10,
 name: "Taro",
 full_name: "佐藤 太郎",
 email: "Taro@example.com",
 birthday: Tue, 01 Dec 1981,
 gender: 0,
 administrator: true,
 created_at: Wed, 06 Dec 2017 01:48:26 UTC +00:00,
 updated_at: Wed, 06 Dec 2017 01:48:26 UTC +00:00>
 => #<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:48:26", updated_at: "2017-12-06 01:48:26"> 
2.4.0 :002 > 
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rails db
SQLite version 3.8.2 2013-12-06 14:53:30
Enter ".help" for instructions
Enter SQL statements terminated with a ";"
sqlite> .tables
members            schema_migrations
sqlite> .schema members
CREATE TABLE "members" ("id" INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, "number" integer NOT NULL, "name" varchar NOT NULL, "full_name" varchar, "email" varchar, "birthday" date, "gender" integer DEFAULT 0 NOT NULL, "administrator" boolean DEFAULT 'f' NOT NULL, "created_at" datetime NOT NULL, "updated_at" datetime NOT NULL);
sqlite> SELECT * from members;
1|10|Taro|佐藤 太郎|Taro@example.com|1981-12-01|0|t|2017-12-06 01:48:26.256444|2017-12-06 01:48:26.256444
2|11|Jiro|鈴木 次郎|Jiro@example.com|1981-12-01|0|f|2017-12-06 01:48:26.273653|2017-12-06 01:48:26.273653
3|12|Hana|高橋 花子|Hana@example.com|1981-12-01|1|f|2017-12-06 01:48:26.287615|2017-12-06 01:48:26.287615
4|13|John|田中 太郎|John@example.com|1981-12-01|0|f|2017-12-06 01:48:26.305878|2017-12-06 01:48:26.305878
5|14|Mike|佐藤 次郎|Mike@example.com|1981-12-01|0|f|2017-12-06 01:48:26.329984|2017-12-06 01:48:26.329984
6|15|Sophy|鈴木 花子|Sophy@example.com|1981-12-01|1|f|2017-12-06 01:48:26.351985|2017-12-06 01:48:26.351985
7|16|Bill|高橋 太郎|Bill@example.com|1981-12-01|0|f|2017-12-06 01:48:26.377117|2017-12-06 01:48:26.377117
8|17|Alex|田中 次郎|Alex@example.com|1981-12-01|0|f|2017-12-06 01:48:26.388937|2017-12-06 01:48:26.388937
9|18|Mary|佐藤 花子|Mary@example.com|1981-12-01|1|f|2017-12-06 01:48:26.400729|2017-12-06 01:48:26.400729
10|19|Tom|鈴木 太郎|Tom@example.com|1981-12-01|0|f|2017-12-06 01:48:26.412824|2017-12-06 01:48:26.412824
11|10|Taro|佐藤 太郎|Taro@example.com|1981-12-01|0|t|2017-12-06 01:48:35.107514|2017-12-06 01:48:35.107514
12|11|Jiro|鈴木 次郎|Jiro@example.com|1981-12-01|0|f|2017-12-06 01:48:35.120632|2017-12-06 01:48:35.120632
13|12|Hana|高橋 花子|Hana@example.com|1981-12-01|1|f|2017-12-06 01:48:35.135291|2017-12-06 01:48:35.135291
14|13|John|田中 太郎|John@example.com|1981-12-01|0|f|2017-12-06 01:48:35.145679|2017-12-06 01:48:35.145679
15|14|Mike|佐藤 次郎|Mike@example.com|1981-12-01|0|f|2017-12-06 01:48:35.157344|2017-12-06 01:48:35.157344
16|15|Sophy|鈴木 花子|Sophy@example.com|1981-12-01|1|f|2017-12-06 01:48:35.167592|2017-12-06 01:48:35.167592
17|16|Bill|高橋 太郎|Bill@example.com|1981-12-01|0|f|2017-12-06 01:48:35.177198|2017-12-06 01:48:35.177198
18|17|Alex|田中 次郎|Alex@example.com|1981-12-01|0|f|2017-12-06 01:48:35.188476|2017-12-06 01:48:35.188476
19|18|Mary|佐藤 花子|Mary@example.com|1981-12-01|1|f|2017-12-06 01:48:35.199639|2017-12-06 01:48:35.199639
20|19|Tom|鈴木 太郎|Tom@example.com|1981-12-01|0|f|2017-12-06 01:48:35.208839|2017-12-06 01:48:35.208839
sqlite> 
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rails c
Loading development environment (Rails 4.2.10)
2.4.0 :001 > Member.ids
   (0.2ms)  SELECT "members"."id" FROM "members"
 => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20] 
2.4.0 :002 > member = Members.find(3)
NameError: uninitialized constant Members
        from (irb):2
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :003 > member.email
NoMethodError: undefined method `email' for nil:NilClass
        from (irb):3
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :004 > member.email
NoMethodError: undefined method `email' for nil:NilClass
        from (irb):4
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :005 > member = Member.find_by(name:"Taro")
  Member Load (0.3ms)  SELECT  "members".* FROM "members" WHERE "members"."name" = ? LIMIT 1  [["name", "Taro"]]
 => #<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:48:26", updated_at: "2017-12-06 01:48:26"> 
2.4.0 :006 > member = Member.find_by(gender:0, administrator:false)
  Member Load (0.3ms)  SELECT  "members".* FROM "members" WHERE "members"."gender" = ? AND "members"."administrator" = ? LIMIT 1  [["gender", 0], ["administrator", "f"]]
 => #<Member id: 2, number: 11, name: "Jiro", full_name: "鈴木 次郎", email: "Jiro@example.com", birthday: "1981-12-01", gender: 0, administrator: false, created_at: "2017-12-06 01:48:26", updated_at: "2017-12-06 01:48:26"> 
2.4.0 :007 > member = Member.find_by(gender:1, administrator:true)    
  Member Load (0.2ms)  SELECT  "members".* FROM "members" WHERE "members"."gender" = ? AND "members"."administrator" = ? LIMIT 1  [["gender", 1], ["administrator", "t"]]
 => nil 
2.4.0 :008 > member = Member.where(name: "Taro")
  Member Load (0.4ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ?  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:48:26", updated_at: "2017-12-06 01:48:26">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:48:35", updated_at: "2017-12-06 01:48:35">]> 
2.4.0 :009 > puts member.to_sql
SELECT "members".* FROM "members" WHERE "members"."name" = 'Taro'
 => nil 
2.4.0 :010 > members = Member.where(name: "Taro")
  Member Load (0.2ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ?  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:48:26", updated_at: "2017-12-06 01:48:26">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:48:35", updated_at: "2017-12-06 01:48:35">]> 
2.4.0 :011 > members = Member.where(number <20")
2.4.0 :012"> members = Member.where(name: "Taro").where("number < 20")
2.4.0 :013"> member.email
2.4.0 :014"> members = Member.where(gender: 1).order("number")
2.4.0 :015"> 
2.4.0 :015?>   
2.4.0 :015?>   
SyntaxError: (irb):11: syntax error, unexpected tSTRING_BEG, expecting ')'
ers = Member.where(number <20")
                              ^
(irb):12: syntax error, unexpected tCONSTANT, expecting end-of-input
ers = Member.where(name: "Taro").where("number < 20")
                              ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
iso1:~/workspace/lecture-1206/asagao (master) $ bin/rails c
^[[ALoading development environment (Rails 4.2.10)
2.4.0 :001 > member.email
NameError: undefined local variable or method `member' for main:Object
        from (irb):1
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :002 > 
iso1:~/workspace/lecture-1206/asagao (master) $ 
```