# OpenGhost
One-click deployment of Ghost on OpenShift. 

## Current version
Currently deploys **Ghost 0.6.4** on: 
- **Node v0.10**
- **MySQL 5.5** or **PostgreSQL 9.2**

As new versions of Ghost become available, OpenGhost will be updated to reflect them.

## Directions for use

### Deployment
[Click here](https://hub.openshift.com/quickstarts/deploy/155-openghost) to deploy, this setup requires 1 gear. Once the deployment is complete, Ghost's admin panel can be accessed at **http://\<app-domain\>.rhcloud.com/ghost**. 

### Custom domains
1. Point your custom domain's CNAME record to \<app-domain\>.rhcloud.com. 
2. On your application's OpenShift page, click change next your application's URL. 
   ![1](https://cloud.githubusercontent.com/assets/6095637/7897816/be5d9c3c-071d-11e5-9a0b-ccd89269ce15.png)
3. Enter your custom domain, then save.
   ![2](https://cloud.githubusercontent.com/assets/6095637/7897827/6739c786-071e-11e5-8cb8-4c4e4c862f7d.png)
4. Clone the application locally and open `config.js` in a text editor. 
5. Look for all instances of `url: 'http://'+process.env.OPENSHIFT_APP_DNS` and change the value to your custom domain. There should be a total of three. 
   
   **Note:** If you're using CloudFlare's Page Rules to force HTTPS connections, use the HTTP version for your `url` value. 
6. Add, commit and push the changes back up to OpenShift. Once the push is complete, your application should be accessible at the custom domain. 

### Syntax highlighting
Have a look at [this blog post](https://blog.darylchan.net/syntax-highlighting-on-ghost/) and remember to push your changes up to OpenShift when you're done with the process. 

## Credits
All rights belong to their respective owners.
