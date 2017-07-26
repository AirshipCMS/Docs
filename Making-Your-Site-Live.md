# Making Your Site Live
Simple steps for making your site live.

---

## DNS Provider
- Log in to your DNS Provider (Namecheap, GoDaddy, Google Domains, etc).

## Create a CNAME
Create a CNAME:  
- Subdomain: **www**
- Value: **subdomain.airshipcms.io**  
Where _subdomain_ is your subdomain on AirshipCMS.io.
  
## Create a Redirect
Create a Temporary 302 Redirect to point your root domain **yourdomain.com** to your "www" subdomain **www.yourdomain.com**

---

In case you are wondering why you cannot just point your root domain to your Airship Site, and then allow either "www" or your plain root domain serve the site, it is beause you cannot set a CNAME for root domains (that's just how domains work). Thus, we need to set a CNAME for "www" and point your root domain to "www."


