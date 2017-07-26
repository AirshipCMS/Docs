# Making Your Site Live
Simple steps for making your site live.

---

## DNS Provider
- Log in to your DNS Provider (Namecheap, GoDaddy, Google Domains, etc).

## Create a CNAME
Create a CNAME for the `www` subdomain for your domain:  
- Subdomain: `www`
- Value: `subdomain.airshipcms.io`

In the above value, the _subdomain_ is your subdomain on AirshipCMS.io.

**Example:**  
For my site "doodlipoop.com":  
- Subdomain: `www`
- Value: `doodlipoop-shop.airshipcms.io`  

Result: `www.doodlipoop.com` points to and serves `doodlipoop-shop.airshipcms.io`.
  
## Create a Redirect
Create a Temporary 302 Redirect to point your root domain `yourdomain.com` to your `www` subdomain `www.yourdomain.com`

**Example:**  
For my site "doodlipoop.com"  
- Set Temporary 302 Redirect for `doodlipoop.com` to point to `www.doodlipoop.com`.

Result: `doodlipoop.com` points to `www.doodlipoop.com` and serves `doodlipoop-shop.airshipcms.io`.

---

In case you are wondering why you cannot just point your root domain to your Airship Site, and then allow either "www" or your plain root domain serve the site, it is beause you cannot set a CNAME for root domains (that's just how domains work). Thus, we need to set a CNAME for "www" and point your root domain to "www."


