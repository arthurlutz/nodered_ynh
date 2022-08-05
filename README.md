<!--
N.B.: This README was automatically generated by https://github.com/YunoHost/apps/tree/master/tools/README-generator
It shall NOT be edited by hand.
-->

# Node-RED for YunoHost

[![Integration level](https://dash.yunohost.org/integration/nodered.svg)](https://dash.yunohost.org/appci/app/nodered) ![Working status](https://ci-apps.yunohost.org/ci/badges/nodered.status.svg) ![Maintenance status](https://ci-apps.yunohost.org/ci/badges/nodered.maintain.svg)  
[![Install Node-RED with YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=nodered)

*[Lire ce readme en français.](./README_fr.md)*

> *This package allows you to install Node-RED quickly and simply on a YunoHost server.
If you don't have YunoHost, please consult [the guide](https://yunohost.org/#/install) to learn how to install it.*

## Overview

Node-RED is a programming tool for wiring together hardware devices, APIs and online services in new and interesting ways.

It provides a browser-based editor that makes it easy to wire together flows using the wide range of nodes in the palette that can be deployed to its runtime in a single-click.

### Features

- Browser-based flow editing
- On-click deployment of the flows
- Over 225,000 modules available
- Custom JavaScript functions can be written

### Override the default settings

From the installation directory, go edit the `/opt/yunohost/nodered/data/settings.user.js`. For example:

```js
module.exports = (defaultSettings) => ({
    lang: "de", // define the language as "de"
    exportGlobalContextKeys: true, // override the `exportGlobalContextKeys` value
logging: { // replace the default logging option ...defaultSettings.logging, // this will reinject the default settings in logging
        console: {
            ...defaultSettings.logging.level, // this will reinject the default settings in logging.console
            level: "debug", // but here, we override the "info" level by "debug"
        },
    },
});
```

You can check the default settings Yunohost generates at `/opt/yunohost/nodered/data/settings.js` and find the documentation for configuring Node-RED here: https://nodered.org/docs/user-guide/runtime/configuration


**Shipped version:** 3.0.2~ynh1

## Screenshots

![Screenshot of Node-RED](./doc/screenshots/screenshot.jpg)

## Disclaimers / important information

YunoHost's permissions system allows you to select which users can have access to Node-RED:
* `main` permission protects `/admin`, the flows editor. The administrator is chosen during installation ;
* `ui` permission protects `/ui`, the dashboard allowing visual interface for the flows. Public access is chosen during installation ;
* `endpoints` permission protects `/`, for API-like endpoints. Public access is chosen during installation.

If you have upgraded Node-RED beyond v2, check that these permissions suit you in your YunoHost admin panel.

## Documentation and resources

* Official app website: <https://nodered.org>
* Official user documentation: <https://nodered.org/docs/>
* Upstream app code repository: <https://github.com/node-red/node-red>
* YunoHost documentation for this app: <https://yunohost.org/app_nodered>
* Report a bug: <https://github.com/YunoHost-Apps/nodered_ynh/issues>

## Developer info

Please send your pull request to the [testing branch](https://github.com/YunoHost-Apps/nodered_ynh/tree/testing).

To try the testing branch, please proceed like that.

``` bash
sudo yunohost app install https://github.com/YunoHost-Apps/nodered_ynh/tree/testing --debug
or
sudo yunohost app upgrade nodered -u https://github.com/YunoHost-Apps/nodered_ynh/tree/testing --debug
```

**More info regarding app packaging:** <https://yunohost.org/packaging_apps>
