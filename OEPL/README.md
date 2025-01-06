This folder contains code used with the [Home Assistant OpenEPaperLink integration](https://github.com/OpenEPaperLink/Home_Assistant_Integration).

# Contents
There are two versions:
## Original version by @MuddyRock

waste_collection_automation.yaml - An automation used with the [Waste Collection Schedule](https://github.com/mampfes/hacs_waste_collection_schedule) integration to display which bins (refuse cans) go out each day. Requires some sensors setting up in YAML. See the [sample file](./waste-collection-sample-sensors.yaml) for some examples.

waste_collection_script.yaml - The script called by the automation, which sends data to the tag.

![The tag on the night the bin should go out (the day before they're emptied)](./bins_tag.jpg)

The automation calls a script where the tag display is drawn and sends several parameters to the script. A full set of examples is in the automation. Parameters are:

      tag_mac: The MAC address of the tag to update
      trash_sensor1: The sensor to use for the first quadrant e.g. sensor.black_bin_schedule
      trash1_name: The name to give the refuse container in the first quadrant e.g. "Black Bin" or "Refuse"
      trash_sensor2: The sensor to use for the second quadrant e.g. sensor.blue_bin_schedule
      trash2_name: The name to give the refuse container in the first quadrant e.g. "Blue Bin" or "Paper"
      trash_sensor3: The sensor to use for the third quadrant e.g. sensor.brown_bin_schedule
      trash3_name: The name to give the refuse container in the first quadrant e.g. "Brown Bin" or "Glass"
      trash_sensor4: The sensor to use for the fourth quadrant sensor.green_bin_schedule
      trash4_name: The name to give the refuse container in the first quadrant e.g. "Green Bin" or "Garden"
      dark_mode: Set to true or false - will turn dark mode on or off
      translation_today: The word to use on the day the refuse is due to be picked up e.g. "Today" or "Heute"
      translation_tonight: The word to use on the day before pick-up e.g. "Tonight" or "Ce Soir"
      translation_days: Translate the word "days" into your language e.g. "days" or "tagen".
      translation_unknown: Translate the word "Unknown" into your language

For a full write-up on how to implement the waste-collection tag, see [php-systems' blog](https://blog.php-systems.com/epaper-displays-and-waste-management/). Note that the code on that page might not be as up to date as the code in this repository.

## Modified version by [@svenove](https://github.com/svenove/)

waste_automation_svenove.yaml - This version supports unlimited number of bins and will display the next 4 bins. It also requires at least v1.0.0 of the integration.

To use this version, simply modify the variables and select the tag-device.
