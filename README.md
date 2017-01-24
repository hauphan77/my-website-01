Follow-Up System Server
=====

### Requirement
- Git
- Ruby
- Rails
- MySql

### Deployment

##### 1. Clone this repository:
```bash
git clone https://github.com/mdluo/follow-up-server.git
```

##### 2. And go into the directory:
```bash
cd follow-up-server
```

##### 3. Install bundle:

3.1 参考 https://ruby.taobao.org/ 配置 Gem 镜像

3.2 安装 bundler

```bash
gem install bundler
```

3.3 然后

```bash
bundle config mirror.https://rubygems.org https://ruby.taobao.org

bundle install --without production
```

##### 4. Then run the migration:

4.1  ~~安装好 MySql 并启动~~ **(默认配置已改为使用 sqlite3，无需依赖 MySql，直接跳到 4.3 )**

4.2 ~~创建名为 `follow_up_development` 的 database~~

4.3 ~~把 `follow-up-server/config/database.yml` 文件第 23-24 行改为相应参数~~

4.3 把 config/database.yml.sample 复制并改名为 database.yml，config/config.yml.sample 复制并改名为 config.yml (无需修改其内容)

4.4 然后

```bash
rake db:create db:migrate db:seed
```

##### 5. One more thing, start the server:
```bash
rails s
```

##### 6. Done! Go to http://127.0.0.1:3000
