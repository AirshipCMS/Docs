## You do not have permission to perform this action.
you probably have to login again. a session expires after 24 hours.

## `airship login` doesn't work
are you in the right directory?  
did you forget the subdomain?  
are you putting in the subdomain correctly?  
are you logging into the right site?  
this won't work: `airship login`  
this won't work: `airship login www.sitename.com`  
this won't work: `airship login sitename.com`  
this won't work: `airship login www.sitename.airshipcms.io`  
this works: `airship login sitename.airshipcms.io`  
this works: `airship login sitename` 

are you logged into a directory containing the one you really wanted? you might have some .airship directories floatin around.

## `airship serve` doesn't work
are you serving a different site in another terminal?  
are you using port 9001 for something else?  
hard refresh the browser. does this fix it?  
run `localStorage.clear();` does this fix it?  
clear browser cache. does this fix it?  

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
