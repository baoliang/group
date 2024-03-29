## 农友网 
## Install

  * You need *Ruby 1.9.2+*, *Rubygems* and *Rails 3.2+* first.
  * Install and start *Redis*, *MongoDB*, *memcached*, *Python*, *Pygments*

and run:

```bash
cp config/config.yml.default config/config.yml
cp config/mongoid.yml.default config/mongoid.yml
cp config/redis.yml.default config/redis.yml
cp config/thin.yml.default config/thin.yml
bundle install
rake assets:precompile
rake db:seed
thin start -O -C config/thin.yml
./script/resque start
bundle exec rake sunspot:solr:start
easy_install pygments # 或者 pip install pygments
rake db:migrate
```

or you can just this issue 

```bash
rake test:init
```

to prepare all the config files and start essential services.

## Deploy

```bash
$ cap deploy
$ cap production remote_rake:invoke task=db:setup
```

# Apply Google JSAPI

* http://code.google.com/intl/zh-CN/apis/loader/signup.html

## Memcached

Dalli requires memcached 1.4.x +
## Thanks

* [Twitter Bootstrap](https://twitter.github.com/bootstrap)
* [GentleFace Icons](http://www.gentleface.com/free_icon_set.html)

Forked from [Homeland Project](https://github.com/huacnlee/homeland)

## License


Released under the MIT license:

