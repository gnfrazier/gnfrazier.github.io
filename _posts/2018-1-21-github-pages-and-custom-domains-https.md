---
layout: post
title: Using GitHub Pages with Custom Domain and HTTPS
---

Initial posts I found about enabling https with a custom domain on GitHub Pages were from 2014 and seemed overly complex. However, the process has become very easy with [Cloudflare](https://www.cloudflare.com "cloudflare.com - Homepage").

Easy enough I won't go into the details. In summary:

-   Buy your domain from your provider of choice.
-   Add the domain name in the settings tab of your github.io repository.
-   Sign up for the free level of Cloudflare.
-   Follow the on-boarding steps for cloudflare to use their name servers.
-   Make sure to set the SSL level to Full.

Done. I set mine up at a low traffic time of day and my dns updated in a few minutes.  Cloudflare is clear that issuing a certificate takes roughly 24 hours. 

### Additional Reading

[Life Is About to Get a Whole Lot Harder for Websites Without HTTPS](https://www.troyhunt.com/life-is-about-to-get-harder-for-websites-without-https/ "TroyHunt.com - Life Is About to Get...")

[Explanation of Full vs Full(Strict) SSL on Cloudflare](https://www.troyhunt.com/cloudflare-ssl-and-unhealthy-security-absolutism/ "TroyHunt.com - CloudFlare, SSL and unhealthy security absolutism")
