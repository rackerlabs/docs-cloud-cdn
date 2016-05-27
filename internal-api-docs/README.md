# Rackspace Cloud CDN Admin API documentation

This repository contains the source files that generate the following Cloud CDN Admin API documentation: 

* [Cloud CDN Administration Guide](https://pages.github.rackspace.com/IX/internal-docs-cloud-cdn-admin/latest/admin-guide/index.html)
* [Cloud CDN Admin API Reference](https://pages.github.rackspace.com/IX/internal-docs-cloud-cdn-admin/latest/api-operations/index.html)

The CDN Admin documentation is internal only. When you commit changes to the ``internal-api-docs`` 
folder in the master branch of this repository, push updates to the following enterprise 
github repository:  [git@github.rackspace.com:IX/internal-docs-cloud-cdn-admin.git](https://github.rackspace.com/IX/internal-docs-cloud-cdn-admin/).  

1. To push the updates, clone the enterprise repository to your system. 

   ```git clone git@github.rackspace.com:IX/internal-docs-cloud-cdn-admin.git```

2. In the directory where you cloned the repo, add this repository as the upstream remote:

  ```git remote add upstream git@github.com:rackerlabs/docs-cloud-cdn.git```

3. Sync your local clone of the enterprise github with the upstream remote:

   ```git pull --rebase upstream master```
   
4. To publish the internal documentation, push your changes to the enterprise repository on GitHub.

   ```git push origin master```
   
After you push your changes, the [internal build job](https://docs-staging.rackspace.com/jenkins/job/internal-doc-cloud-cdn-admin/) 
kicks off to publish the new content on the gh-pages branch. You can review the updates at the following URL: 
https://pages.github.rackspace.com/IX/internal-docs-cloud-cdn-admin/latest/

You can also access the CDN Administrator Guide and other internal documentation from the following URL.
https://pages.github.rackspace.com/IX/internal-docs-landing-page. 


### Support and feedback

We welcome feedback, comments, and bug reports. Follow the [contributor guidelines](../CONTRIBUTING.md) 
to propose a source file change, or [submit a GitHub issue](https://github.com/rackerlabs/docs-cloud-cdn/issues/new) 
to request an update or to provide feedback.

You can also contact the [Rackspace documentation team](mailto:devdoc@rackspace.com) directly for general 
issues or questions about the content. 
