# Piwik for Joomla

## UNMAINTAINED PROJECT
This project is no longer maintained. Any issues will not be actively picked up. Pull Requests will be merged unchecked. The sources here are up-for-grabs.

## Introduction
This plugin allows you to integrate Piwik in your Joomla site, while not using any client-side code. The benefit of this is first of all that the Piwik integration will not slow down the client side loading. Additionally, it is fully compliant with EU cookie-regulations and requires no cookie banner to ask for user permission. All tracking is done on the server side.

## Setup
- Install the plugin in the Extension Manager
- Enable the plugin in the Plugin Manager
- Configure your Piwik API in the plugin settings

## Usage
- Install this plugin using the Extension Manager
- Within the Plugin Manager, enable and configure this plugin
- Configure the (numeric) website ID: This is found under the Websites-tab in Piwik itself.
- Configure the API-token. This is found under the API-page in Piwik.

To use Piwik within your 404 pages as well, you need to modify the error.php file of your Joomla template. Add the following code:

    include_once JPATH_SITE . '/plugins/system/piwik/piwik.php';
    if (class_exists('PlgSystemPiwik')) {
        PlgSystemPiwik::callPiwik();
    }

## FAQ: What is the difference between the normal Piwik widget and this plugin?
Usually Piwik is integrated through a JavaScript widget, which sets a cookie in the browser. This Piwik plugin works through the PHP API, and works without cookies. Note that the PHP API is not aware of JavaScript-measured statistics like screen resolution. If you want to know more about difference, please refer to the Piwik website.
