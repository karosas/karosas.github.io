+++
title = "Key Vault is not for standard app configuration"
date = 2023-09-14T19:36:36+02:00
draft = true
+++

Rant of the day - don't use Azure Key Vaults as a storage for standard, non-secret app configuration.

Obvious to some, but not to everyone.

In my opinion configuration should be (in no particular order):

### 1. Decoupled from application

It shouldn't be needed to rebuild/re-deploy application to update config of running application.

### 2. Easy to update

Developer shouldn't need to jump through hoops to enable a feature flag or change timeout value

### 3. Central

It should be possible to update your application's configuration at one central, easy to access place.

While Key Vault is a central place and does integrate with multiple languages/platforms as configuration provider, it's absolutely annoying to update its values. Only to read a single value it takes around 4 clicks and then the value shown is truncated so you probably need to copy-paste it somewhere to read fully. Oh you want to edit it? No can do, go back and create a new version writing it from scratch.