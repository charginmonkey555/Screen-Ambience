# Screen Ambience

This is my Hack Club Forge project. The goal is to create a high-density ambient monitor backlight using an ESP32 and SK6812 ARGBW LEDs (Addressable Red Green Blue White)

The project uses WLED running on an ESP32 to control individually addressable LEDs mounted around the back of a monitor. The LEDs provide ambient lighting, custom effects, and can be controlled wirelessly over Wi-Fi.

## Why I Made This

Most monitor backlights from brands like Philips Hue or Govee are either expensive or have low-density LEDs that create visible hotspots. I wanted to make my own version using a high-density SK6812 strip to achieve smoother colours and gradients while learning more about electronics, wiring, and LED control.

The project is essentially an extension of my monitor that adds a layer of immersion while watching TV, playing games, etc. It can elevate the theme of my desktop setup, illuminate the whole room with a colourful vibe, and can significantly reduce eye strain when looking at a monitor in the dark. I have always thought this was quite important, and have felt the strain of looking at a bright monitor in the dark, and so this project will help remove this issue whilst also providing an immersive experience to anything I do at my computer.

## Features

- High-density 144 LEDs/m SK6812 RGBW strip
- ESP32 controller running WLED
- Wi-Fi control
- Individually addressable LEDs
- Power injection to reduce voltage drop
- Custom colours, effects, and presets
- Designed specifically for use behind a monitor
- Compatible with SignalRGB's screen ambience effect to match a whole setup.

## Hardware

The current design consists of:

- ESP32 development board
- SK6812 RGBW LED strip x 2 (144 LEDs/m)
- 5V 10A power supply
- Power injection wiring
- WLED firmware

## Wiring

The ESP32 is powered directly from the 5V power supply.

The LED strip is powered from both ends to reduce voltage drop and maintain consistent brightness across the entire strip.

Connections:

The PSU's 5V will go to both the ESP32's 5V pin and the ARGB strip's 5V pin ON EITHER SIDE (for power injection to prevent voltage drop.)
The PSU'S GND will go to the ESP32'S GND pin and again to either side of the strip on the GND pin. This is not necessary but is good practice.
The strip will recieve data from the ESP32's GPIO18 pin, because after doing some research, I have learned that the GPIO18 pin is a reliable output pin that does not affect the ESP32 boot process and is widely used in WLED projects.
I will solder the 2 strips together to create 1 continuous strip that is 2 meters long and has 288LEDS

<img width="792" height="561" alt="Screenshot 2026-11-04 213851" src="https://github.com/user-attachments/assets/f41b6d9b-b28b-419c-a333-811b7dc064ab" />
<img width="741" height="535" alt="Screenshot 2026-11-04 213828" src="https://github.com/user-attachments/assets/4c3ebcf8-cf8f-4210-8a4b-40fbdb5d1f1d" />
<img width="965" height="544" alt="Screenshot 2026-11-04 213742" src="https://github.com/user-attachments/assets/828b6333-1854-4e15-9e12-1f3ef19036c3" />


## Software

The project uses WLED running on the ESP32.

Planned setup:

1. Flash WLED to the ESP32
2. Connect the ESP32 to Wi-Fi
3. Configure LED count and GPIO pin
4. Test effects and brightness levels
5. Mount the LEDs to the monitor
6. Connect the ESP32 to SignalRGB via it's IP address
7. Set up correct LED count and orientation
8. relax :)

## Progress

Current progress can be found in my Forge journal:

[Hack Club Forge](https://forge.hackclub.com/projects/1922)

## Bill of Materials

| Name | Quantity | Price (£) | Price ($) | Link |
|--------|--------|--------|--------|--------|
| SK6812 ARGBW Strip | 2 | £19.38 | $26.11 | [Product Page]([https://example.com](https://www.aliexpress.com/item/1005007011130121.html?spm=a2g0o.productlist.0.0.116115e7XG0Yef&mp=1&pdp_npi=6%40dis%21GBP%21GBP+15.63%21GBP+9.69%21%21GBP+9.69%21%21%21%400b88486a17938295960516596e0faf%2112000040696309140%21ct%21UK%216184487227%21%212%210%21)) |
| DC Female Connector | 1 | £1.66 | $2.24 | [Product Page]([https://example.com](https://www.aliexpress.com/item/1005001561298133.html?spm=a2g0o.productlist.main.6.3df4584dHaeRXa&algo_pvid=2e04ed06-6692-4257-8f5f-0ae4271dea61&algo_exp_id=2e04ed06-6692-4257-8f5f-0ae4271dea61-5&pdp_ext_f=%7B%22order%22%3A%222256%22%2C%22eval%22%3A%221%22%2C%22fromPage%22%3A%22search%22%7D&pdp_npi=6%40dis%21GBP%211.68%211.66%21%21%212.20%212.17%21%400b88a96117938310423174702e0e2d%2112000016596862364%21sea%21UK%216184487227%21X%211%210%21n_tag%3A-29919%3Bd%3A301f7349%3Bm03_new_user%3A-29895%3BpisId%3A5000000221153541&curPageLogUid=mh5ndo9wJNgn&utparam-url=scene%3Asearch%7Cquery_from%3A%7Cx_object_id%3A1005001561298133%7C_p_origin_prod%3A)) |
| PSU (Power Supply) | 1 | £9.89 | $13.32 | [Product Page]([https://example.com](https://www.aliexpress.com/item/1005005763465796.html?spm=a2g0o.cart.0.0.773438damNCmuj&mp=1&pdp_npi=6%40dis%21GBP%21GBP+10.72%21GBP+9.89%21%21GBP+9.89%21%21%21%400b88ac1917938313037042215e1053%2112000034265307623%21ct%21UK%216184487227%21%211%210%21)) |

### Total Cost

| Currency | Total |
|-----------|--------|
| GBP (£) | £30.93 |
| USD ($) | $41.67 |
