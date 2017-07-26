# Making Your Site Live
Simple steps for making your site live.

---

## DNS Settings
- Log in to your DNS Provider (Namecheap, GoDaddy, Google Domains, etc).
- Create a CNAME to point "www.yourdomain.com" to your Airship site subdomain "subdomain.airshipcms.io".
- Create a Temporary 302 Redirect to point your root domain "yourdomain.com" to the subdomain "www.yourdomain.com".*

---

You won't be able to set a CNAME for your root domain (that's just how domains work), so you need to set a CNAME for "www" and point your root domain to "www."
