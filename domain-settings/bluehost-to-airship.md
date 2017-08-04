# How to Point a Domain registered on BlueHost to an Airship CMS site
Steps for making your site live.

---

## Login to BlueHost
- Click on the **Domains** nav link.

## Step 1: Set up a CNAME that points to Airship Servers
- Click on the **Zone Editor** subnav link
- Select the domain you want to point to Airship Servers
- Set the **Host Record** to **www**
- leave "TTL" as is
- Set "Type" to **CNAME**
- Set "Points to" to **subdomain.airshipcms.io**
  (where "subdomain" is your site subdomain on Airship)
- Click **Add Record**

## Step 2: Set up a 302 Redirect
- Click on the **Redirects** subnav link
- Select **Temporary (302)** Redirect
- Select **Do Not Redirect www**
- Leave "Make this a Wild Card Redirect" unchecked
- Click **Add this Redirect**

## Step 3: Wait
DNS settings can take up to 24 hours to propagate. 
Periodically check that the plain version of your domain `domain.com` changes to the "www" version of your domain `www.domain.com`, and that the your Airship site loads.

Note for Developers: As the developer of an Airship site, if you don't have access to your client's BlueHost Registrar, you send your client the instructions above, or you can ask your client to change the Name Server settings for the domain to point to a separate DNS Provider that you control. 
1. Send your client these simple instructions for **Setting Up your BlueHost Domain to point to an external DNS Service**.
2. In your own DNS Service, set up a CNAME & 302 Redirect.

Other DNS Services:
- **Digital Ocean**
- **Dreamhost**
- **GoDaddy**

---

## More Resources

**Setting up a CNAME on BlueHost**  
https://my.bluehost.com/cgi/help/cname  

**Setting up a 302 Redirect on BlueHost**  
https://my.bluehost.com/cgi/help/182  

---

In case you are wondering why you cannot just point your root domain to your Airship Site, and then allow either "www" or your plain root domain serve the site, it is beause you cannot set a CNAME for root domains (that's just how domains work). Thus, we need to set a CNAME for "www" and point your root domain to "www."
