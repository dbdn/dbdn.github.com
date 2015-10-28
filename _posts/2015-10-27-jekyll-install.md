---
layout: post
title: Jekyll安装
category: jekyll
date: 2015-10-27
description: "阅读了标题中的论文后的一些总结"
duoshuo: true

---
---


报错1：

    dbdn@ubuntu:~/develop/blog$ gem install jekyll
    ERROR:  Could not find a valid gem 'jekyll' (>= 0), here is why:
            Unable to download data from https://rubygems.org/ - Errno::ECONNRESET: Connection reset by peer - SSL_connect (https://api.rubygems.org/latest_specs.4.8.gz)
    dbdn@ubuntu:~/develop/blog$ gem install jekyll
    ERROR:  Could not find a valid gem 'jekyll' (>= 0), here is why:
            Unable to download data from https://rubygems.org/ - Errno::ECONNRESET: Connection reset by peer - SSL_connect (https://api.rubygems.org/latest_specs.4.8.gz)
    

解决：

    dbdn@ubuntu:~/develop/blog$ gem sources -l
    *** CURRENT SOURCES ***

    https://rubygems.org/
    http://ruby.taobao.org/

    dbdn@ubuntu:~/develop/blog$ gem sources --remove https://rubygems.org/
    https://rubygems.org/ removed from sources
    
    dbdn@ubuntu:~/develop/blog$ 
    dbdn@ubuntu:~/develop/blog$ 
    dbdn@ubuntu:~/develop/blog$ 
    dbdn@ubuntu:~/develop/blog$ gem sources -l
    *** CURRENT SOURCES ***
    
        http://ruby.taobao.org/
    dbdn@ubuntu:~/develop/blog$ sudo gem install rack 









报错2：


    dbdn@ubuntu:~/develop/blog$ sudo gem install jekyll
    Building native extensions.  This could take a while...
    /usr/lib/ruby/2.1.0/rubygems/ext/builder.rb:73: warning: Insecure world writable dir /usr/local in PATH, mode 040777
    ERROR:  Error installing jekyll:
        ERROR: Failed to build gem native extension.
    
        /usr/bin/ruby2.1 extconf.rb
    mkmf.rb can't find header files for ruby at /usr/lib/ruby/include/ruby.h
    
    extconf failed, exit code 1
    
    Gem files will remain installed in /var/lib/gems/2.1.0/gems/ffi-1.9.10 for inspection.
    Results logged to /var/lib/gems/2.1.0/extensions/x86_64-linux/2.1.0/ffi-1.9.10/gem_make.out

解决：
```
sudo apt-get install ruby2.1-dev
```

报错3:

    dbdn@ubuntu:~/develop/blog$ jekyll 
    /var/lib/gems/2.1.0/gems/execjs-2.6.0/lib/execjs/external_runtime.rb:135: warning: Insecure world writable dir /usr/local in PATH, mode 040777
    /var/lib/gems/2.1.0/gems/execjs-2.6.0/lib/execjs/runtimes.rb:48:in `autodetect': Could not find a JavaScript runtime. See https://github.com/rails/execjs for a list of available runtimes. (ExecJS::RuntimeUnavailable)
    

解决：
```
sudo apt-get install nodejs
```
