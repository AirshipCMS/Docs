# How to Point a Domain with DNS Managed by Digital Ocean to an Airship CMS site
Steps for making your site live.

---

## Login to Digital Ocean
(coming soon)

## Step 1: Set up a CNAME that points to Airship Servers
(coming soon)

## Step 2: Set up a 302 Redirect
(coming soon)

## Step 3: Wait
DNS settings can take up to 24 hours to propagate. 
Periodically check that the plain version of your domain `domain.com` changes to the "www" version of your domain `www.yourdomain.com`, and that the your Airship site loads.

---

## More Resources

**Resource**  
(link)

---

In case you are wondering why you cannot just point your root domain to your Airship Site, and then allow either `www` or your plain root domain serve the site, it is beause you cannot set a CNAME for root domains (that's just how domains work). Thus, we need to set a CNAME for `www` and point your root domain `yourdomain.com` to `www`.
