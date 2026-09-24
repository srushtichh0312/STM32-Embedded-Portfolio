# 01_LED_Blink

A beginner-level Embedded Systems project demonstrating **onboard LED blinking using the STM32F103C8T6 Blue Pill microcontroller** and **STM32CubeIDE**.

The onboard LED is controlled through **GPIOC Pin 13 (PC13)** and its state is toggled at a 500 ms interval using the STM32 HAL Library.

---

## 📌 Objective

The objective of this project is to understand the basics of:

* STM32 microcontroller GPIO configuration
* Configuring a GPIO pin as an output
* GPIO Output Push-Pull mode
* Controlling an onboard LED
* Using the STM32 HAL Library
* Creating and programming an STM32 project using STM32CubeIDE

---

## 🛠️ Hardware Used

| Component                   | Description                                     |
| --------------------------- | ----------------------------------------------- |
| **STM32F103C8T6 Blue Pill** | Main microcontroller board                      |
| **ST-LINK/V2**              | Used to program/debug the STM32 microcontroller |

---

## 💻 Software Used

* **STM32CubeIDE**
* **STM32 HAL (Hardware Abstraction Layer) Library**

---

## 🔌 GPIO Configuration

The onboard LED is connected to:

**GPIO Port:** `GPIOC`
**Pin:** `PC13`
**Mode:** GPIO Output Push-Pull

### Configuration

| Parameter | Setting               |
| --------- | --------------------- |
| GPIO Port | GPIOC                 |
| GPIO Pin  | PC13                  |
| GPIO Mode | GPIO Output Push-Pull |
| Function  | Onboard LED control   |

The GPIO configuration is generated/configured using **STM32CubeIDE**.

---

## ⚙️ Working Principle

The program continuously toggles the state of the onboard LED.

The basic sequence is:

```text
Start
  ↓
Initialize HAL
  ↓
Initialize GPIO
  ↓
Configure PC13 as Output Push-Pull
  ↓
Enter infinite loop
  ↓
Toggle PC13
  ↓
Wait 500 ms
  ↓
Toggle PC13
  ↓
Wait 500 ms
  ↓
Repeat
```

The LED state is changed using:

```c
HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
```

A delay of **500 ms** is provided after each toggle:

```c
HAL_Delay(500);
```

Therefore, the LED continuously changes its state at 500 ms intervals.

---

## 🧑‍💻 Code

The main LED blinking logic used in the project is:

```c
while (1)
{
    HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
    HAL_Delay(500);
}
```

The GPIO pin is configured as an output so that the microcontroller can control the LED connected to **PC13**.

---

## 🔍 Code Explanation

### `HAL_GPIO_TogglePin()`

```c
HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
```

This function toggles the output state of **PC13**.

* If the pin is HIGH → it changes to LOW.
* If the pin is LOW → it changes to HIGH.

This change in GPIO state controls the onboard LED.

### `HAL_Delay()`

```c
HAL_Delay(500);
```

This creates a **500 millisecond delay** before the next toggle.

This makes the LED state change slow enough to observe.

---

## 📊 Result

The onboard LED connected to **PC13** continuously toggles its state with a **500 ms delay between successive toggles**.

This confirms the basic GPIO output control using the STM32F103C8T6 and STM32 HAL Library.

---

## 📚 Key Concepts Learned

Through this project, the following Embedded Systems concepts were practiced:

* STM32F103C8T6 microcontroller basics
* GPIO ports and pins
* GPIO output configuration
* Output Push-Pull mode
* Digital GPIO control
* STM32 HAL Library
* `HAL_GPIO_TogglePin()`
* `HAL_Delay()`
* STM32CubeIDE project development
* Basic embedded firmware programming
* Programming an STM32 microcontroller using ST-LINK/V2

---

## 📁 Project Structure

A typical STM32CubeIDE project contains files and folders such as:

```text
01_LED_Blink/
├── Core/
│   ├── Inc/
│   └── Src/
├── Drivers/
├── .ioc
└── ...
```

The exact project structure is generated and managed by **STM32CubeIDE**.

---

## 🎯 Project Outcome

This project provides a basic hands-on introduction to **STM32 GPIO programming and embedded firmware development** using the STM32F103C8T6 Blue Pill.

It serves as a foundation for progressing toward more advanced STM32 peripherals and embedded-system projects.

---

## 👩‍💻 Project

**Project Name:** `01_LED_Blink`
**Microcontroller:** STM32F103C8T6
**Development Environment:** STM32CubeIDE
**Programming Library:** STM32 HAL Library
