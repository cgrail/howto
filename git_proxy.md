# How to configure git behind a proxy on a Mac

Configuring a proxy is pretty straightforward and can be done with the following command:
```
git config --global http.proxy http://proxy:8080
```

That works perfectly, if you just need communicate with an external Git/Github instance. 

If you have a mixture of internal and external git servers, you need to specify which hosts can be reached through the proxy and which not.

This can be done by editing the `.gitconfig` file in your user directory.

In my case I want to define that git shouldn't use a proxy for the internal Github server:

```
[http]
	proxy = http://proxy:8080
[http "https://github.wdf.sap.corp"]
	proxy = 
```
