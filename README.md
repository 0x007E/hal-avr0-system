[![Version: 1.0 Release](https://img.shields.io/badge/Version-1.0%20Release-green.svg)](https://github.com/0x007e/hal-avr0-system) ![Release](https://github.com/0x007e/hal-avr0-system/actions/workflows/release.yml/badge.svg) [![License GPLv3](https://img.shields.io/badge/License-GPLv3-lightgrey)](https://www.gnu.org/licenses/gpl-3.0.html)

# `hal-avr0-system` - AVR0 System Hardware Abstraction

The `hal-avr0-system` is a lightweight hardware abstraction library for `AVR0` microcontrollers. It provides a clean interface for system clock initialization and software-triggered system reset while hiding direct register-level interaction from higher software layers. The library is intended for projects that want to separate low-level device startup code from application logic and establish a small, reusable system layer for AVR0 targets.

## Features

- System clock configuration for AVR0 devices.
- Software reset support.
- Encapsulation of low-level register access.
- Compact and reusable API for embedded projects.
- Foundation for layered HAL architectures.

> The `hal-avr0-system` library reduces coupling by providing a focused interface for essential system services. This improves portability inside a project, keeps startup code organized, and makes higher-level modules easier to maintain.

## File Structure

![File Structure](https://0x007e.github.io/hal-avr0-system/system_8c__incl.png)

```
hal/
└── avr0/
    └── system/
        ├── system.c
        └── system.h
```

## Downloads

The library can be downloaded (`zip` or `tar`), cloned or used as submodule in a project.

| Type      | File               | Description              |
|:---------:|:------------------:|:-------------------------|
| Library   | [zip](https://github.com/0x007E/hal-avr0-system/releases/latest/download/library.zip) / [tar](https://github.com/0x007E/hal-avr0-system/releases/latest/download/library.tar.gz) | AVR0 system library |

### Using with `git clone`

```sh
mkdir -p ./hal/avr0
git clone https://github.com/0x007E/hal-avr0-system.git ./hal/avr0
mv ./hal/avr0/hal-avr0-system ./hal/avr0/system
```

### Using as `git submodule`

```sh
git submodule add https://github.com/0x007E/hal-avr0-system.git hal/avr0/system
```

## Programming

Additional parameters like clock and peripheral speed can be setup in the [header file](./system.h). A user friendly description can be found [here](https://0x007e.github.io/hal-avr0-system/system_8h.html).

```c
#include "../hal/avr0/system/system.h"

int main(void)
{
	system_init();

    // Application code
    // ...

    // Trigger a software reset if needed
    system_reset();

    while (1) { }
}
```

## Additional Information

| Type       | Link               | Description              |
|:----------:|:------------------:|:-------------------------|
| AVR0-Series | [pdf](https://ww1.microchip.com/downloads/en/DeviceDoc/megaAVR0-series-Family-Data-Sheet-DS40002015B.pdf) | megaAVR® 0-series family datasheet |

---

R. GAECHTER