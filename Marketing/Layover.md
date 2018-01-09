# Layover
_or, secure Apex Domain A Records as a service._

You have probably experienced _many instances_ where you simply need to point your naked, apex domain to "www". 

**Why would you want to point your Apex Domain to "www" instead of the other way around?**
For externally hosted services like Shopify, Big Cartel, Big Commerce, or Airship CMS, you need to point a subdomain such as `www` or `shop` to their service. As much as you want to, these services don't seem to allow you to enter your apex domain as the main domain for your externally-hosted site. Why is that? **Because _it is simply not possible_ to create a CNAME Record for an Apex Domain.** It's not a restriction put in place by the hosted service; it is a limitation of all DNS Providers, period. 

_So_, instead of forwarding `www` to your Apex domain, you need to point your Apex domain to `www` and _then_ `www` can point to your externally-hosted service. 

For those not familiar with DNS Providers, it's a big confusing headache. We don't even like setting everything up every single time we build another site. Therefore, we built **Layover** to be a service that can handle some of the routing for you! Simply follow the steps on this page to point your naked, apex domain to "www". 

### HTTPS on your apex domain, for free!
Layover handles https:// for your apex domain, _and more_!


### Other Services like Layover
There are probably many other services like Layover. Many of them are probably


Notes
- This service is FREE, and will be up as long as we exist.
- You don't have to use Airship CMS in order to use this service.
- You don't have to use this service, to use Airship CMS.

---

# Layover with an Airship CMS Site

## Step 1. Create a CNAME Record for _your_ subdomain that points to `airshipsubdomain.airshipcms.io`.
Create a CNAME Record where:
- `airshipsubdomain` is your actual Airship Site subdomain. 
- You can use `www` or some other subdomain that you want to point to your Airship Site subdomain. 
- Set the TTL to `600`, or as short as your DNS provider will allow. @jon?

#### Example for a subdomain of `completelyfabricated.com`:
This creates a `CNAME` that points `www.completelyfabricated.com` to `completely-fabricated.airshipcms.io`.
```
CNAME:
www  CNAME  completelyfabricated.airshipcms.io  600
```
The site will render over https at `https://www.completelyfabricated.com`.

#### Example for a subdomain of `hiarmymuseumsoc.org`:
This creates a `CNAME` that points `shop.hiarmymuseumsoc.org` to `completely-fabricated.airshipcms.io`.
```
CNAME:
shop  CNAME  hams.airshipcms.io  600
```
The site will render over https at `https://shop.hiarmymuseumsoc.org`.

## Step 2. Create an A Record for your Apex Domain
If you are not pointing your primary apex domain to your Airship site, you can stop at Step 1. If you _are_ pointing your primary apex domain to your Airship Site, then Create an A Record:
- Use the Apex Domain (`@`) as the name.
- Value is `34.214.155.73`. This is the IP for the Layover service.
- Set the TTL to `600`, or as short as your DNS provider will allow. @jon?

#### Example for domain `completelyfabricated.com`:
```
A RECORD:
@   A   34.214.155.73   600
```
This will make the apex domain `completelyfabricated.com` route to `www.completelyfabricated.com`. In addition, `completelyfabricated.com` will work as both `http://completelyfabricated.com` and `https://completelyfabricated.com`.

---

**Alternate to Step 2**
Some DNS Providers have a "Domain Forwarding" service where you can simply tell the service to forward your apex domain to "www". If this service exists, you can use it. Note that you will want to forward the apex domain to "www", and not the other way around (do not point "www" to your apex domain). These services are probably not set up to automatically serve your site over https.
