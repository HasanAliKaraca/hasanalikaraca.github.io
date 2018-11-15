---
id: 178
title: 'TC Kimlik No Doğrulama c#'
date: 2014-12-15T20:54:55+00:00
author: Hasan Ali Karaca
layout: post
guid: http://hasanalikaraca.com/?p=178
permalink: /2014/12/tc-kimlik-no-dogrulama-c/
cyberchimps_slider_image:
  - ""
cyberchimps_slider_hidetitle:
  - "1"
cyberchimps_slider_hidecaption:
  - "1"
sfw_pwd:
  - rKZijsZAAphE
categories:
  - Uncategorized
layout: post
---

{{ page.title }}
================

### Kurallar:

  * 11 haneli bir rakamdır.
  * 0&#8217;la başlayamaz.
  * ilk 10 rakamın toplamının birler basamağı, son rakama eşittir

#### Vikipedi:

  * 1, 3, 5, 7 ve 9. rakamın toplamının 7 katı ile 2, 4, 6 ve 8. rakamın toplamının 9 katının toplamının birler basamağı 10. rakamı;
  * 1, 3, 5, 7 ve 9. rakamın toplamının 8 katının birler basamağı 11. rakamı vermektedir.

#### Programatik olarak düşünürsek, ilk rakam 0. index olduğuna göre:

  * 0, 2, 4, 6, 8. rakamın(çift haneler 10 hariç) toplamının 7 katı ile 1, 3, 5, 7.(tek haneler 9 ve 11 hariç) toplamının 9 katının toplamının birler basamağı(mod10) sondan bir önceki rakama eşittir
  * 0, 2, 4, 6, 8. rakamın toplamının 8 katının birler basamağı(mod10) son rakama eşittir

Buna göre şöyle bir method yazdım:

<script src="https://gist.github.com/HasanAliKaraca/90a2011c3e649108c551a4b63376db63.js"></script>
