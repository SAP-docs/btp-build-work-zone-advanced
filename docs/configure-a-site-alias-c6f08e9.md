<!-- loioc6f08e96ebbf44ff8949ce6fc317452c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configure a Site Alias

Administrators can specify a meaningful alias for the site, which will replace the site’s ID in the URL.



## Procedure

You create, edit, or remove an alias in the Site Directory.

1.  In the Site Directory, for the site, click <span class="SAP-icons-V5"></span> \(More options\) and select *Manage Site Alias*.

2.  Enter a valid alias, which contains up to 100 letters, digits, and hyphens only.

    > ### Note:  
    > Do not use `ui` for the alias name.

3.  Save.


The site alias can be seen when hovering over the site and in the Site Settings screen.

> ### Note:  
> To launch the site with its alias, you need to replace in the URL `?siteId=<siteid>` with `/<sitealias>` as demonstrated in the following example:
> 
> Original URL, which includes the full site id:
> 
> ```
> https://<domain>/site?siteId=<siteid>#Shell-home
> ```
> 
> The same URL, which uses the site alias instead:
> 
> ```
> https://<domain>/site/<sitealias>#Shell-home
> ```

