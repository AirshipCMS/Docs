# Airship CLI Troubleshooting (Kelli)
(describe)

## Common Issues
(describe)

### `airship login` doesn't work
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

### `airship serve` doesn't work
are you serving a different site in another terminal?  
are you using port 9001 for something else?  
hard refresh the browser. does this fix it?  
run `localStorage.clear();` does this fix it?  
clear browser cache. does this fix it?  

#### 401: Unauthorized
When I refresh the browser, it returns:
```{"statusCode":401,"error":"Unauthorized","message":"Invalid token","attributes":{"error":"Invalid token"}}```
Your auth token may have expired (it refreshes every 24hours). Login again.

In the terminal, when you run any command:
```You do not have permission to perform this action.```
Your auth token may have expired (it refreshes every 24hours). Login again.

### I'm getting a 413 error for `airship launch`  
you are uploading too many things and have exceeded the cap of 10mb load size per item for assets.
or > 5mb for templates & layouts (this is really hard to do for text files. you may be putting stuff you aren't supposed to in these directories). 
