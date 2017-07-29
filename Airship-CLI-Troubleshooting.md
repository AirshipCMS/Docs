## You do not have permission to perform this action.
A session expires after 24 hours. Login again and continue to run airship cli commands.

## `airship login` doesn't work
- Are you in the right directory?
- Did you forget the subdomain in the command?  
- Did you enter the subdomain correctly?
- Did you log in to the correct site?

Formats that won't work:
- `airship login`  
- `airship login www.sitename.com`  
- `airship login sitename.com`  
- `airship login www.sitename.airshipcms.io`  

Formats that work:
- `airship login sitename.airshipcms.io`  
- `airship login sitename` 

## `airship serve` doesn't work
- Are you serving a different site in another terminal? You can only serve one site at a time.
- Are you using port 9001 for something else?  
- Hard refresh the browser. Does this fix it?  
- Run `localStorage.clear();` Does this fix it?  
- Clear browser cache. Does this fix it?  

## 401: Unauthorized
When I refresh the browser, it returns:
```{"statusCode":401,"error":"Unauthorized","message":"Invalid token","attributes":{"error":"Invalid token"}}```
Your auth token may have expired (it refreshes every 24hours). Login again.

## I'm getting a 413 error for `airship launch`  
you are uploading too many things and have exceeded the cap of 10mb load size per item for assets.
or > 5mb for templates & layouts (this is really hard to do for text files. you may be putting stuff you aren't supposed to in these directories). 

no layout or template set.

Debugging after `airship launch`
If you launched your project and you don't see your changes on the live site, try doing a hard-refresh on the browser for the live site. If that doesn't work, try clearing your browser cache. Your local cache may be very sticky. If that doesn't work either and it has been more than 5 minutes since you have launched your site, there might be some other issue.

hitting api over https

## I'm logged in to the wrong directory, though I can still run `airship serve`
You might have logged in to an airship site in the wrong directory at some point. You may have a `.airship` durectory floating around in your root directory. Find the ghost `.airship` directory and delete it.
