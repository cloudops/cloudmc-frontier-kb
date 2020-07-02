---
title: "Authenticating with OpenID Connect"
slug: authenticating-with-openid-connect
---


### How to configure an external OpenID Connect provider

Integrating CloudMC with an OpenID Connect provider is a three-step process, described in the following sections:
   - Configure the identity provider
   - Configure CloudMC
   - Submit a **callback URL** to the provider

Any user with the **Reseller** role, or any other role which has the *Authentication: Manage* permission, may add an OpenID Connect identity provider.

Navigate to *System* -> *Authentication* to get to the *Authentication* page, where all configured identity providers are listed.

#### Configure identity provider

To integrate with an identity provider, you will need to configure a client for CloudMC in your OpenID Connect identity provider.  Follow the instructions for configuring your identity provider, and obtain the client credentials required by CloudMC:
   - Issuer URL
   - Client ID
   - Client secret

#### Configure CloudMC

1. Click *Add identity provider*.  The *Add identity provider* page will appear.
![Identity provider page](/assets/1-oidc-add-en.png)
1. OpenID Connect (OIDC) is currently the only option for **Type**.
1. Choose a provider from the pop-up menu labeled **Provider**.  Any identity provider that has already been configured will appear greyed-out in the menu.
![Select identity provider](/assets/2-oidc-add-en.png)
1. Fields for the information required to connect to the identity provider will appear.
![Details for identity provider](/assets/3-oidc-add-en.png)
1. Enter the required details you obtained from the identity provider, then click *Submit*.
1. The *Authentication* page appears and the new provider is listed.  Additionally, the CloudMC login page now presents users with a button to sign on with the identity provider.

#### Submit callback URL to provider

To complete the integration with the identity provider, CloudMC will generate a callback URL to pass to the provider:

1. From the *Authentication* page, select the *Action* menu to the right of your configured identity provider.  Select *Copy callback URL*.
1. In your identity provider's configuration, navigate to the client, and enter the callback URL to the list of authorized redirect URLs.
1. CloudMC will now authenticate properly through your identity provider.
