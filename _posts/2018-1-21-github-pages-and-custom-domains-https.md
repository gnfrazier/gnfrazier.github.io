---
layout: post
title: Using GitHub Pages with Custom Domain and HTTPS with Cloudflare
tags: github-pages https cloudflare cdn
---

Initial posts I found about enabling https with a custom domain on GitHub Pages were from 2014 and seemed overly complex. However, the process has become very easy with [Cloudflare](https://www.cloudflare.com "cloudflare.com - Homepage").

Easy enough I won't go into the details. In summary:

-   Buy your domain from your provider of choice.
-   Add the domain name in the settings tab of your github.io repository.
-   Sign up for the free level of Cloudflare.
-   Follow the on-boarding steps for Cloudflare to use their name servers.
-   Make sure to set the SSL level to Full.

Done. I set mine up at a low traffic time of day and my DNS updated in a few minutes.  Cloudflare is clear that issuing a certificate takes roughly 24 hours. 

#### Update

In Cloudflare's Crypto section my certificate stayed in the 'Authorizing Certificate' state for 3 days. I contacted their support using the support form. It was easy to use, even on my phone. I submitted this as a low priority bug, everything else was working. Within 30 minutes I got this nice response back.

> Hi,
>
> Thank you for contacting Cloudflare Support. Sorry that you are experiencing some issues here.
>
> It looks like your SSL certificate stuck at Authorization state. I've canceled it and placed a new SSL order for you and will update you once it's successfully deployed.

2 hours later.

> Hi,
>
> SSL Certificate is now Active for your domain.
>
> Sorry for the delays and thank you for your patience while we were working on this.
>
> I will mark this as solved but do let us know if you have any further questions or issues by replying to this e-mail or ticket.

Expectations met and exceeded! I am on the free tier, Cloudflare had better support times than some services I pay for. 

### Additional Reading

[Life Is About to Get a Whole Lot Harder for Websites Without HTTPS](https://www.troyhunt.com/life-is-about-to-get-harder-for-websites-without-https/ "TroyHunt.com - Life Is About to Get...")

[Explanation of Full vs Full(Strict) SSL on Cloudflare](https://www.troyhunt.com/cloudflare-ssl-and-unhealthy-security-absolutism/ "TroyHunt.com - CloudFlare, SSL and unhealthy security absolutism")
