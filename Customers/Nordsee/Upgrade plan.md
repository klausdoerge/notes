
* [ ] Create a new resource group for Umbraco 13 upgrad
- [ ] Move the  App Service  Plan to a Shared Group
- [x] Test Cloudflare CDN
- [ ] Copy database to Umbraco 13 and test the content
- [ ] Ensure legacy-support for nested-content is activated
- [ ] Create CI for Umbraco 13 deployment

Cloudflare setup for test

cftest.nordseehighlights.com
cftest.nordseehighlights.dk
cftest.nordseehighlights.de

Setup the 3 sub-domains and have them point to /index.html, /index_de.html, index_dk.html

Test that the routing of Vue works as expected, and that we get the correct meta-data from the language-specific files when sharing the links.

If Cloudflare does not work out-of-the-box, we will go back to using Microsoft Frontdoor.
- Cloudflare and Azure do not play well together when renewing domains/certificates due to the way Cloudflare handles domains/DNS. We will use Frontdoor like the other solutions.


Wiki

1. Create a storage account & setup as static web-site
2. Add Frontdoor CDN to the storage account
3. Create a web-app for Umbraco
	1. Target .Net 10
	2. Windows
	3. Unselect App insights

Frontdoor profile
profile: nshighlightsfrontdoorprofile
name: nshighlightsfrontdoor

Managed identity
nshighlights-ci

Free - General Purpose - Serverless: Standard-series (Gen5), 2 vCores