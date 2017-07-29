## CLI: You do not have permission to perform this action.
One of these cases is true:
- Your session expired. Login again and continue to run airship cli commands.
- You are logged in but you don't have superadmin privledges for the site.

## CLI: `airship login` doesn't work
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

## CLI: `airship serve` doesn't work
- Are you serving a different site in another terminal? You can only serve one site at a time.
- Are you using port 9001 for something else?  
- Hard refresh the browser. Does this fix it?  
- Run `localStorage.clear();` Does this fix it?  
- Clear browser cache. Does this fix it?  

## Browser: 401 Unauthorized
When I refresh the browser, it returns:
```
{"statusCode":401,"error":"Unauthorized","message":"Invalid token","attributes":{"error":"Invalid token"}}
```
Your session expired. Login again and continue to run airship cli commands. Then refresh the browser.

## CLI: I'm getting a 413 error for `airship launch`  
- You might be uploading too many things and have exceeded the cap of 10mb load size per item for assets.
- You might have exceeded the cap of 5mb for templates & layouts. (This is really hard to do with text files. You may be putting files you aren't supposed be adding in these directories). 

## Browser: 501 Not Implemented Error
When I load a page or collection, I get this error:
```
{"statusCode":501,"error":"Not Implemented","message":"Error: EISDIR: illegal operation on a directory, read"}
```
You have not set a layout and/or template for the page or collection you are rendering. Set a layout and template in Airship CMS and refresh the page.

## Browser: I launched my site and my styles have not updated
If you launched your project and you don't see your changes on the live site, try doing a hard-refresh on the browser for the live site. 

If that doesn't work, try clearing your browser cache. Your local cache may be very sticky. 

If that doesn't work either and it has been more than 5 minutes since you have launched your site, there might be some other file syncing issue. Add an arbitrary change to the style file (such as a comment) and run `airship launch` again.

If that doesn't work, you can try running `airship land` then making an arbitrary change to the style file, then run `airship launch` again.

## Browser: My site doesn't load over https
You may be making calls to the API over an http connection. Always do API calls over an https connection.

## I'm logged in to the wrong directory, though I can still run `airship serve`
You might have logged in to an airship site in the wrong directory at some point. You may have a `.airship` durectory floating around in your root directory. Find the ghost `.airship` directory and delete it.
