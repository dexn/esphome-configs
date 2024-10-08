# Personal ESPHome Device Configs
These are just the configurations for the ESPHome devices I have. I've made them so they share a basic configuration to show similar data. I also added a fast boot factory reset script for devices that are in a hard to reach place, or have a faulty button.

### Adopting
When adopting into the dashboard, it will ask you for a name. In the next step, click skip then ok. Edit the device to change settings, add wifi and anything else you want.

### Substitutions
I have included a few substitutions for some of the most frequently changed settings. If you would like to add or change other settings, I'd suggest using `!extend` or `!remove` [explained below](https://github.com/dexn/esphome-configs#extend-and-remove).
```
# Name used for mDNS and entities
# Can only contain lowercase a-z, 0-9 and hyphens. Can be at most 24 characters long.
name: "athom-smart-plug-v2"

# Name used for the device
# Can also contain uppercase letters, spaces and other characters.
friendly_name: "Athom Smart Plug V2"

# Restore state on bootup
# Available options are `RESTORE_DEFAULT_OFF`, `RESTORE_DEFAULT_ON`, `RESTORE_INVERTED_DEFAULT_OFF`, `RESTORE_INVERTED_DEFAULT_ON`, `ALWAYS_OFF`, `ALWAYS_ON` and `DISABLED`.
restore_mode: RESTORE_DEFAULT_OFF

# Data read and send interval
# Can be a time in seconds `10s`, minutes `5min`, hours `2h` or don't update with `never`.
update_interval: 10s
```

### `!extend` and `!remove`
If you want to make changes or add additional configuration, you can use `!extend config_id`.
```
sensor:
  - id: !extend wifi_signal_db
    internal: true
```
If you want to remove a configuration, you can use `!remove config_id`.
```
sensor:
  - id: !remove wifi_strength
```
or to remove a core configuration, you can use `component !remove`.
```
web_server: !remove
```
