---
id: 114
title: 'JVM not found &#8211; %JAVA_HOME% problem phonegap / ant'
date: 2013-06-12T18:09:30+00:00
author: Hasan Ali Karaca
layout: post
guid: http://hasanalikaraca.com/?p=114
permalink: /2013/06/java_home-problem-phonegap-ant/
sfw_pwd:
  - mZFmosqcDtpH
categories:
  - Uncategorized
layout: post
---

{{ page.title }}
================

%JAVA\_HOME% = &#8220;C:\Program Files (x86)\Java\jdk1.6.0\_22&#8243;
  
%ANT_HOME% = &#8220;C:\ant&#8221;

They must defined without &#8220;\bin&#8221; but in System variables:

add to following line to **beginning** of the Path variable:
  
%JAVA\_HOME%\bin;%ANT\_HOME%\bin;

&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Phonegap commands(in project&#8217;s directory):

ant playbook build

//after build, install app to simulator
  
ant playbook load-simulator

&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;-
  
sencha touch 2 form panel is buggy on playbook
 