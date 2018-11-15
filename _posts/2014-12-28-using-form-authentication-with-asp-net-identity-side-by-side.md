---
id: 188
title: Using form authentication with asp.net identity side by side
date: 2014-12-28T14:27:22+00:00
author: Hasan Ali Karaca
layout: post
guid: http://hasanalikaraca.com/?p=188
permalink: /2014/12/using-form-authentication-with-asp-net-identity-side-by-side/
cyberchimps_slider_image:
  - ""
cyberchimps_slider_hidetitle:
  - "1"
cyberchimps_slider_hidecaption:
  - "1"
sfw_pwd:
  - MPOuLADoxMA5
categories:
  - Uncategorized
---
If you want to use form authentication and asp.net identity and in your web config

<authentication mode="Forms">

then with a little trick you can use both, the same time

<pre class="brush: csharp; title: ; notranslate" title="">public class ChallengeResult : HttpUnauthorizedResult
{
    public ChallengeResult(string provider, string redirectUri)
        : this(provider, redirectUri, null)
    {
    }

    public ChallengeResult(string provider, string redirectUri, string userId)
    {
        LoginProvider = provider;
        RedirectUri = redirectUri;
        UserId = userId;
    }

    public string LoginProvider { get; set; }
    public string RedirectUri { get; set; }
    public string UserId { get; set; }

    public override void ExecuteResult(ControllerContext context)
    {
        // HERE
        // this line did the trick
        context.RequestContext.HttpContext.Response.SuppressFormsAuthenticationRedirect = true;


        var properties = new AuthenticationProperties() { RedirectUri = RedirectUri };
        if (UserId != null)
        {
            properties.Dictionary[XsrfKey] = UserId;
        }

        context.HttpContext.GetOwinContext().Authentication.Challenge(properties, LoginProvider);
    }
}

</pre>

reference:
  
http://stackoverflow.com/questions/19893718/mvc-5-external-authentication-with-authentication-mode-forms

<div class="addtoany_share_save_container addtoany_content_bottom">
  <div class="a2a_kit a2a_kit_size_32 addtoany_list a2a_target" id="wpa2a_13">
    <a class="a2a_button_facebook" href="http://www.addtoany.com/add_to/facebook?linkurl=http%3A%2F%2Fhasanalikaraca.com%2F2014%2F12%2Fusing-form-authentication-with-asp-net-identity-side-by-side%2F&linkname=Using%20form%20authentication%20with%20asp.net%20identity%20side%20by%20side" title="Facebook" rel="nofollow" target="_blank"></a><a class="a2a_button_twitter" href="http://www.addtoany.com/add_to/twitter?linkurl=http%3A%2F%2Fhasanalikaraca.com%2F2014%2F12%2Fusing-form-authentication-with-asp-net-identity-side-by-side%2F&linkname=Using%20form%20authentication%20with%20asp.net%20identity%20side%20by%20side" title="Twitter" rel="nofollow" target="_blank"></a><a class="a2a_button_google_plus" href="http://www.addtoany.com/add_to/google_plus?linkurl=http%3A%2F%2Fhasanalikaraca.com%2F2014%2F12%2Fusing-form-authentication-with-asp-net-identity-side-by-side%2F&linkname=Using%20form%20authentication%20with%20asp.net%20identity%20side%20by%20side" title="Google+" rel="nofollow" target="_blank"></a><a class="a2a_dd addtoany_share_save" href="https://www.addtoany.com/share_save"></a>
  </div>
</div>