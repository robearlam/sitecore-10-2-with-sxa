# sitecore-10-2-with-sxa
A repository showing how to configure an instance of Sitecore 10.2 using SXA

# Setup
Execute the following command to install setup the sitecore instance:

```
.\compose-init.ps1 `
    -Topology 'XM1' `
    -LicenseXmlPath <<PATH_TO_LICENSE_FILE>> `
    -IdHost 'xm1id.localhost' `
    -CdHost 'xm1cd.localhost' `
    -CmHost 'xm1cm.localhost' `
    -SitecoreAdminPassword 'b' `
    -SqlSaPassword 'Password123456!!'
```

Run `docker-compose up -d` to start the Sitecore containers