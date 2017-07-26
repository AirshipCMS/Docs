# Making Your Site Live
Simple steps for making your site live.

---

## DNS Provider
- Log in to your DNS Provider (Namecheap, GoDaddy, Google Domains, etc).

## 1. Create a CNAME
Create a CNAME for the `www` subdomain for your domain:  
- Subdomain: `www`
- Value: `subdomain.airshipcms.io`

In the above value, the _subdomain_ is your subdomain on AirshipCMS.io.  
Settings may take several minutes to hours to take effect, depending on your DNS provider.  

**Example:**  
For my site "doodlipoop.com":  
- Subdomain: `www`
- Value: `doodlipoop-shop.airshipcms.io`  

Result: `www.doodlipoop.com` points to and serves `doodlipoop-shop.airshipcms.io`.  
  
## 2. Create a Redirect (Recommended)
Create a Temporary 302 Redirect to point your root domain `yourdomain.com` to your `www` subdomain `www.yourdomain.com`  
Settings may take several minutes to hours to take effect, depending on your DNS provider.  

**Example:**  
For my site "doodlipoop.com", set:
- Temporary 302 Redirect for `doodlipoop.com`
- Point to `www.doodlipoop.com`

Result: `doodlipoop.com` points to `www.doodlipoop.com` and serves `doodlipoop-shop.airshipcms.io`.

## 2. Cannot Set a Redirect? (Alternative)
Some DNS providers do not have an option to set a Temporary Redirect for the root domain. In this case, you will need to create an ANAME and point your root domain to a static IP Address. This method is less recommended, becase IP Addresses of servers can change. This seldom happens, though it _can_ happen if there are server upgrades, optimizations, or other system changes.

For some Airship Sites where we do not have access to the DNS Provider, or the DNS Provider does not have redirect controls, we use the [redirect.name](http://redirect.name) service.

**Example:**
For my site "doodlipoop.com":
- I have already set the CNAME for `www` to point to `doodlipoop-shop.airshipcms.io`
- Following the instructions at [redirect.name](http://redirect.name), I added the TXT record `_redirect` with the value `Redirects to http://www.doodlipoop.com`
- Following the instructions at [redirect.name](http://redirect.name), I added the A record for the root domain with the value `45.55.72.95`

**Example:**  
For my site "doodlipoop.com", set:
- Temporary 302 Redirect for `doodlipoop.com`
- Point to `www.doodlipoop.com`

Result: `doodlipoop.com` points to `www.doodlipoop.com` and serves `doodlipoop-shop.airshipcms.io`.

---

In case you are wondering why you cannot just point your root domain to your Airship Site, and then allow either "www" or your plain root domain serve the site, it is beause you cannot set a CNAME for root domains (that's just how domains work). Thus, we need to set a CNAME for "www" and point your root domain to "www."


