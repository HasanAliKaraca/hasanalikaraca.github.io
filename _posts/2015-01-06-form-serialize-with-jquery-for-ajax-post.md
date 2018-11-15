---
id: 193
title: Form serialize with jquery for ajax post
date: 2015-01-06T23:03:46+00:00
author: Hasan Ali Karaca
layout: post
guid: http://hasanalikaraca.com/?p=193
permalink: /2015/01/form-serialize-with-jquery-for-ajax-post/
cyberchimps_slider_image:
  - ""
cyberchimps_slider_hidetitle:
  - "1"
cyberchimps_slider_hidecaption:
  - "1"
sfw_pwd:
  - rFRYqFjk6eOf
categories:
  - Uncategorized
layout: post
---

{{ page.title }}
================

If you have normal form(like all text fields) to serialize form data use 

<pre class="brush: jscript; title: ; notranslate" title="">$("#my-form").serialize(); 
</pre>

Beside that if you have form enctype of &#8220;multipart/form-data&#8221; then use 

<pre class="brush: jscript; title: ; notranslate" title="">new FormData(this)
</pre>

Example:

<pre class="brush: jscript; title: ; notranslate" title="">$('#my-form') .submit( function(e) {
        var formData = new FormData(this);
        $.ajax({
            url: 'http://url',
            type: 'POST',
            data: formData,
            processData: false,  // tell jQuery not to process the data
            contentType: false   // tell jQuery not to set contentType
        });
        e.preventDefault();
    });
</pre>

Ref 

https://developer.mozilla.org/en-US/docs/Web/Guide/Using\_FormData\_Objects

<div class="addtoany_share_save_container addtoany_content_bottom">
  <div class="a2a_kit a2a_kit_size_32 addtoany_list a2a_target" id="wpa2a_14">
    <a class="a2a_button_facebook" href="http://www.addtoany.com/add_to/facebook?linkurl=http%3A%2F%2Fhasanalikaraca.com%2F2015%2F01%2Fform-serialize-with-jquery-for-ajax-post%2F&linkname=Form%20serialize%20with%20jquery%20for%20ajax%20post" title="Facebook" rel="nofollow" target="_blank"></a><a class="a2a_button_twitter" href="http://www.addtoany.com/add_to/twitter?linkurl=http%3A%2F%2Fhasanalikaraca.com%2F2015%2F01%2Fform-serialize-with-jquery-for-ajax-post%2F&linkname=Form%20serialize%20with%20jquery%20for%20ajax%20post" title="Twitter" rel="nofollow" target="_blank"></a><a class="a2a_button_google_plus" href="http://www.addtoany.com/add_to/google_plus?linkurl=http%3A%2F%2Fhasanalikaraca.com%2F2015%2F01%2Fform-serialize-with-jquery-for-ajax-post%2F&linkname=Form%20serialize%20with%20jquery%20for%20ajax%20post" title="Google+" rel="nofollow" target="_blank"></a><a class="a2a_dd addtoany_share_save" href="https://www.addtoany.com/share_save"></a>
  </div>
</div>