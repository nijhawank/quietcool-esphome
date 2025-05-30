# QuietCool ESPHome Control

> [!NOTE]
> The QuietCool Smart Attic Fan Control works with both whole house fans and attic fans.  In my application, I used it for a whole house fan.

This repository contains ESPHome configurations for controlling QuietCool whole house fans and attic fans. QuietCool fans can be automated and integrated into your smart home using ESP32 devices flashed with these configurations.

The project provides a web-based installation interface using [ESP Web Tools](https://esphome.github.io/esp-web-tools/), making it easy to flash your ESP device directly from your browser.

## Configurations

### quietcool-smart-attic-fan-control.yaml

This configuration file provides smart control for QuietCool attic fans. Features include:

- Temperature-based automatic control
- Manual speed control (Low/High)
- Integration with Home Assistant
- Real-time temperature and humidity monitoring
- Automatic shutdown when attic temperature reaches desired level
- Web-based control interface

## Getting Started

1.  Pair your phone with the Smart Attic Fan Control.
2.  Retrieve the MAC address of your controller from the QuietCool app.
3.  Flash an ESP32 using this template.  See [Packages](https://next.esphome.io/components/packages) for details on how to use this repository in your ESPHome configuration.  The gist is that you can simply add the following YAML to your configuration:

``` yaml
substitutions:
    mac_address: "00:00:00:00:00:00" # Replace with your Smart Attic Fan Control's MAC address

packages:
  remote_package_shorthand: github://awkaplan/quietcool-esphome/quietcool-smart-attic-fan-control.yaml@main
```

4.  Add the ESPHome device to Home Assistant and update the pairing ID with a unique, 16-digit hex string.
5.  Use the QuietCool app to put the controller in pairing mode.
6.  Press the ESPHome device's pair button in Home Assistant.
7.  Forget the bluetooth device on your phone (optional).

## Credits

This project builds upon the research and development done by [@emerose](https://github.com/emerose/quietcool), who created a Python-based BLE client for the QuietCool Wireless RF Control Kit. Their work was instrumental in understanding the QuietCool BLE protocol and making this ESPHome integration possible.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
