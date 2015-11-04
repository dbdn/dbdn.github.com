---
layout: post
title: erlang学习笔记
category: [erlang, lists]
date: 2015-10-27
duoshuo: true
---

---

##erlang基础


###二进制例子
 
    <<A,B,C,D/bits>> = <<1,1:12,1>>.        #dfda
    <<1,0,16,1:4>>
    
    A = B = C = 1.   
    <<A:7, B:6, C:3>>. 
    <<2,9>>.

<!-- more -->

----------


 - and or 会计算两边表达式；
 - andalso, orelse 只要一方满足条件，另一面就不会计算
 
----------

列表

    A = [1,2,3]. 
    B = [a,d,f].  
    [A|B] = [[1,2,3],a,d,f].
    A ++ B.  [1,2,3,a,d,f].
    ++ 操作时，将小列表放在左边


----------


###erlang进程监控

    link
    monitor
    trap_exit


----------


### gen_server

    hibernate 

    

##性能分析工具
webtool

    webtool:start(standard_path, [{port,8888}, {bind_address, {192,168,1,71}}, {server_name,"user"}]).

找出cpu占用最高的进程，图形界面输出，每10秒更新一次

    spawn(fun() -> etop:start([{interval,10}, {sort, runtime}]) end).
    etop:stop().


找出内存占用较高进程, 输出进程的数量为20，文本形式输出

    spawn(fun() -> etop:start([{output, text}, {lines, 20},  {sort, memory}]) end).
    etop:stop().


查看远程节点etop

    erl -name abc@192.168.17.102 -hidden -s etop -output text -sort memory -lines 20 -node 'test@192.168.17.102' -setcookie mycookie123


###erlang常用函数

    registered().
    processes().
    release_handler_1:get_supervised_procs().


---