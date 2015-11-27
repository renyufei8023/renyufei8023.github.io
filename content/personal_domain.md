Date: 2013-08-01
Title: 今天我终于有了自己的独立域名
Category: Tech
Tags: 域名, godaddy
Slug: personal_domain

今天折腾了半天，终于搞定了自己的独立域名：<http://www.lizherui.com>

整个过程颇为曲折：

1. 去<https://www.godaddy.com>上用支付宝花80多块钱购买为期一年的顶级域名，并去修改Nameservers为这两个地址：f1g1ns1.dnspod.net、f1g1ns2.dnspod.net。
2. 去<https://www.dnspod.cn>上添加新域名，并申请一条A记录指向Github Pages的ip:207.97.227.245；
3. 在Pelican主目录新建CNAME文件，添上刚刚申请的域名：www.lizherui.com。

有了独立域名后，感觉非常爽，更加坚定了好好打理个人博客的决心。
