# sec-interview
以下为信息安全各个方向涉及的面试题，星数越多代表问题出现的几率越大，没有填答案是希望大家如果不懂能自己动手找到答案，祝各位都能找到满意的工作:)

注:做这个List的目标不是全，因为无论如何都不可能覆盖所有的面试问题，更多的还是希望由点达面，查漏补缺。

## TODO LIST

- [x] 渗透测试
- [x] Web安全
- [x] PHP安全
- [x] Java安全
- [x] Linux相关
- [ ] Windows相关
- [ ] 内网渗透
- [x] 安全研发
- [ ] 甲方安全运营

## 渗透测试
- 如何绕过CDN找到真实IP，请列举五种方法 (★★★)
- redis未授权访问如何利用，利用的前提条件是？(★★★)
- mysql提权方式有哪些?利用条件是什么? (★)
- windows+mysql，存在sql注入，但是机器无外网权限，可以利用吗? (★)
- 常用的信息收集手段有哪些，除去`路径扫描`，`子域名爆破`等常见手段，有什么猥琐的方法收集企业信息? (★★)
- `SRC挖掘`与`渗透测试`的区别是什么，针对这两个不同的目标，实施过程中会有什么区别 (★★)
- 存储xss在纯内网的环境中，可以怎么利用？(★★)
- mssql中，假设为sa权限，如何不通过`xp_cmdshell`执行系统命令 (★★)
- 假设某网站存在waf，不考虑正面绕过的前提下，应该如何绕过(分情况讨论 云waf/物理waf) (★)

## Web安全相关

- 介绍一下自认为有趣的挖洞经历（或CTF经历）(★★★)
- CSRF的成因及防御措施（不用token如何解决) (★)
- SSRF的成因及防御措施 (★★)
- SSRF如何探测非HTTP协议(★)
- 简述一下SSRF的绕过手法(★★)
- 简述一下SSRF中DNSRebind的绕过原理及修复方法(★)
- 介绍 SQL 注入漏洞成因，如何防范？注入方式有哪些？除了拖取数据库数据，利用方式还有哪些？(★★)
- 如何通过sql注入写shell,写shell的前提条件是什么?(★★)
- 介绍一下XSS漏洞的种类，dom型XSS和反射XSS的区别是什么?(★★)
- 如何防范 XSS 漏洞，在前端如何做，在后端如何做，哪里更好，为什么？(★★)
- 讲述一下找回密码可能涉及的逻辑漏洞(★)
- 假设你是甲方的一名安全工程师，应该如何降低逻辑漏洞的出现率?(★★)
- oauth认证过程中可能会出现什么问题，导致什么样的漏洞?(★)
- CSP应该如何使用及配置，有哪些绕过CSP的方式(★★)
- 已知某网站存在LFI(本地文件包含)，但是无法上传任何文件，针对该情况有哪些利用方式?(★★)
- 简述一下XXE漏洞产生的原理，针对PHP和JAVA，XXE分别可以进行哪些恶意利用?(★★)

## PHP安全

- PHP中如何使用`phar://`伪协议触发反序列化，利用场景以及前提条件有哪些?(★★)
- 如何绕过`php.ini`中`disable_function`的限制，有哪些方法，其中成功率最高的方法是哪个，为什么?(★★★)
- 文件上传中`%00`截断的原理是什么，官方是如何设计修复方案的?(★★)
- 实现一个一句话webshell，绕过RASP的方式有哪些，绕过机器学习检测的方式有哪些，绕过AST-Tree的方式有哪些(★★)
- PHP伪协议的攻击场景有哪些？(★★)
- `mail`函数的攻击面有哪些?(★)
- 如何不通过数字以及字符构造webshell，其原理是什么，此类特性还会造成什么安全问题?(★)

## JAVA安全

- `ClassLoader`是什么? 加载自定义`ClassLoader`的前提是什么? (★)
- 大概讲一下`CommonCollections1`的利用链，该利用链有什么样的限制?  (★★)
- fastjson的反序列化和普通反序列化漏洞的区别是什么? (★★)
- 在tomcat中实现内存马有哪些方式，有办法实现重启之后依然不会消失的内存马吗？ (★)
- 单向代码执行链如何实现执行多条语句，如`CommonCollections1` (★)

## 安全研发相关

- 简要介绍自己常用的扫描器和其实现上的特点(★★)
- 如果让你设计一个HIDS，应该如何设计(★)
- 介绍一下Python中的迭代器、生成器、装饰器(★)
- 介绍自己常用的python库(★)
- 讲一讲celery的特点以及原理(★)
- 简述Python中的GIL锁，以及如何打破GIL锁的限制(★★)
- masscan号称世界上最快的扫描器，快的原因是什么，如何实现一个自己的masscan?(★★)
- 简述协程，线程，以及进程的区别(★★)

## Linux相关

- 简述一下守护进程的概念，如何生成一个守护进程? (★)
- Linux 服务器的安全运维操作有哪些？如何保护 SSH？(★★)
- 入侵 Linux 服务器后需要清除哪些日志？(★★)
- 反弹 shell 的常用命令？一般常反弹哪一种 shell？为什么？(★★★)
- 从主机的层面，反弹shell如何监控 (★★★)
- Rootkit的种类有哪些，针对不同种类的Rootkit应该如何防护以及检测 (★★)
- A账户创建了权限为766的文件夹`adir`，该文件夹中有B账户的文件`password.txt`，权限为B账户的700，请问B账户能否读取到`adir/password.txt`文件的内容 (★)
- ssh软链接后门的原理是什么，可以通过该原理构造其他后门吗?(★)
- Linux中fork的原理是什么，子进程一定会拷贝父进程的资源状态吗？(★★)
- 实现R3层HOOK的方式有哪些，R0层的HOOK又有哪些? (★)
- Linux下如何准确实现应用识别，如识别`nginx` `mysql`等  (★)
- 假设某Linux机器存在命令审计(方法未知)，有哪些可能的绕过方法? (★★)
- Linux常见的提权方法有哪些?(★★)

## 内网渗透

- psexec的底层实现原理是什么? (★)

- SSP接口中修复了哪个模块杜绝了mimikatz的恶意利用，具体是如何修复的？(★★)

- 内网KDC服务器开放在哪个端口，针对kerbores的攻击有哪些? (★★★)

- 在win10或者winserver2012中，如果需要使用mimikatz，该如何使用，修改注册表后如何在不重启机器的情况下获取NTLM? (★★)

- 域内如何查询员工对应的机器？ (★)

- 如何查询域之间的信任关系？ (★)

- 域控开放的常见端口有哪些？(★)

- windows内网中ntlm协议认证过程 (★★★)

- cobalt strike中上线方式有哪些，各自是什么原理，如果需要绕过监控，如何绕？ (★★)

- 横向渗透中，wmic如何构造有回显的命令执行? (★★)

- windows应急响应中，需要查看哪些安全日志ID，分别对应哪些攻防场景，如果该windows主机为域控，又应该查看哪些事件日志？ (★★★)

- golden ticket和sliver ticket的区别是什么？ (★★★)

- 在非域主机的情况下，如何快速发现域主机？ (★★)

- mimikatz的原理，哪个补丁导致了mimikatz无法利用，如何绕过? (★★)

- NTLM relay的攻击场景有哪些，使用NTLM relay会受到哪些限制？ (★)


## 其他安全相关
- RSA加解密流程(★)
- HTTPS是如何实现的(★★)
- 如何防护运营商的DNS劫持/链路劫持(★★)
- 如何防范羊毛党？(★)
- 一个大范围影响的0day被曝光，作为甲方安全工程师，应该如何处理(★★)
