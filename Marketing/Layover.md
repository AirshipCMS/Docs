# Layover
You have probably experienced many instances where you simply needed to point your naked, apex domain to "www", and discovered that it actually takes several steps to make that happen. **Layover** simplifies those steps for you, and provides secure Apex Domain Domain A Records, as a service.

**Why would you want to point your Apex Domain to "www" instead of the other way around?**  
Shopify, Big Commerce, Airship CMS, and other externally-hosted services require that you point a subdomain such as `www` or `shop` to their servers. These services don't allow you to enter your apex domain as the main domain for your externally-hosted site. Why is that? **Because _it is simply not possible_ to create a CNAME Record for an Apex Domain.** It's not a restriction put in place by the hosted service; it is a limitation of all DNS Providers, period. 

_So_, instead of forwarding `www` to your Apex domain, you need to forward your Apex domain to `www` and then `www` can point to your externally-hosted service. 

It can be a headache. _We_ don't even like setting everything up every  time we are ready to launch a project. So to make our lives easier, we built **Layover** as a service that can handle some of this redundant and complex routing. Simply follow the steps on this page to point your naked, apex domain to "www". 

**HTTPS for your apex domain, for Free!**  
Layover automatically handles `https://` for your apex domain, so you don't have to worry about setting up an SSL certificate. If your site is hosted on Airship CMS, your Airship subdomain and any CNAMEs pointing to your Airship subdomain will automatically enforce `https://` as well. Your DNS Provider may already have their own forwarding service that points your apex domain to `www`. However, the service may not automatically enforce `https://`.

**Usage**  
This service is Free. You do not have to use Airship CMS in order to use Layover (simply set the CNAME to another externally-hosted site). You also do not have to use Layover to use Airship CMS. This service will be actively maintained and updated as long as this webpage is active. Last Update: 1/9/2018.

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

**Alternates**  
Some DNS Providers have a "Domain Forwarding" service where you can simply tell the service to forward your apex domain to "www". If this service exists, you can use it. Note that you will want to forward the apex domain to "www", and not the other way around (do not point "www" to your apex domain). These services are probably not set up to automatically serve your site over https. / If you are super server-side-savvy, you can even create your own service. Though if that's the case, you will probably know what's best :]

**Limited DNS**  
Some DNS Providers don't let you set some values for certain record types. (You should really use a different DNS provider).

**TXT Step**  
Add TXT Record part when that is ready.
