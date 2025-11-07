RWE is running an older version which needs update. 

- [ ] Update API to latest version
- [ ] Create dev and staging environments
- [ ] API to test
	- [ ] Azure sign-in (new)
	- [ ] Dump Service
	- [ ] Echo Service
	- [ ] Logging Service
	- [ ] Message Board Service
	- [ ] Points Service
	- [ ] Poll Service
	- [ ] Presence Service
	- [ ] UserStore Service (new)

**Deployment tasks**

Update Authentication DB
Update-Database -Context AzureAuthenticationDataContext

Update DB with UserStore
Update-Database -Context UserStoreDataContext

