---
id: 162
title: Saving russian data on Sql Server
date: 2014-04-15T09:56:36+00:00
author: Hasan Ali Karaca
layout: post
guid: http://hasanalikaraca.com/?p=162
permalink: /2014/04/saving-russian-data-on-sql-server/
cyberchimps_slider_image:
  - ""
cyberchimps_slider_hidetitle:
  - "1"
cyberchimps_slider_hidecaption:
  - "1"
sfw_pwd:
  - ptLghcTCzwtI
categories:
  - Uncategorized
---
1) use nvarchar or nchar datatype
  
2) insert values with N prefix. eg: 

insert into tblFoo values(N&#8217;слайд&#8217;)

2) use N prefix on your select statements.eg:

N&#8217;select * from tblFoo&#8217;

3) On c# code dont use datatype as DataType.AnsiString use DataType.String instead
 