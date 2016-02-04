# HomeAssistant app for Splunk
This is a Splunk app designed to be used with the [HomeAssistant](https://home-assistant.io) home automation platform, to give you more insight into your system.

## Requirements
* You need to have at least Splunk 6.3 installed, since this uses the HTTP Event Collector introduced in that version.
* HomeAssistant installed on a machine that can connect to the one running Splunk.

## Installation
* Install the app by copying the `homeassistant` directory to `$SPLUNK_HOME/etc/apps/homeassistant` and restarting Splunk so that the app is recognized.
* At this moment, you must manually enable the HTTP Event Collector and add a token for HomeAssitant:
 - Go Settings > Data Inputs and choose HTTP Event Collector
 - For "All Tokens", select "Enabled", and click "Save"
 - Choose "New Token"
 - Give your token a name and click "Next"
 - Under "Source type", choose "Select", and then "Structured > homeassistant_event"
 - Under Index, set your index ("homeassistant", by default) as the "Default Index"
 - When you're done, you'll be given the "Token Value".  Place this in your HomeAssistant configuration as per the Splunk component's documentation.

## Features
* Provides analogues to HomeAssistant's native reporting, including a range-configurable History view and a filterable logbook.
* Provides a Device Tracker view that shows time spent per location/device
* Provides an Energy Usage dashboard (although this may need to be customized to your HomeAssistant configuration)
