---
title: "Getting Started with ESP32: Setting Up Your Development Environment"
seoTitle: ""Getting Started with ESP32: Easy Setup Guide for Your Development Env"
seoDescription: ""Learn how to set up your development environment for ESP32 in this comprehensive guide. Discover how to use Visual Studio Code, and explore the benefits of"
datePublished: Fri Jul 19 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clyuge386000b09l498vibdq5
slug: getting-started-with-esp32-setting-up-your-development-environment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1721495703271/0ec46fa3-0e00-4cab-9891-2d0d4e5aa1dc.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1721499351668/0c3542b9-ab60-4931-a3c9-d22b25a5f25c.webp
tags: c-programming, programming-blogs, programming, iot, wifi, bluetooth, bluetooth-low-energy, vscode-extensions, esp32, embedded-systems, microcontrollers, tech-tutorial, developmentenvironment, espidf, esp-idf

---

1. **Introduction**
    

Welcome to the first post in the "ESP32 Development Series"! In this series, we'll explore the ESP32, a small and powerful computer chip that can connect to WiFi and Bluetooth. The ESP32 is perfect for building all sorts of smart devices, from home gadgets to wearable technology.

The ESP32, made by Espressif Systems, is a low-cost chip that uses little power. It has a dual-core processor, which means it can do more things at once. It also has many built-in features, making it a great choice for projects that need to connect to the internet or other devices.

The goal of this series is to help you get started with the ESP32. We'll begin by setting up your computer with the tools you need to program the ESP32. Then, we'll move on to writing simple programs, connecting to the internet, using sensors, and updating your device wirelessly.

By the end of this series, you’ll understand how to work with the ESP32 and create your own smart projects. Whether you're new to programming or have some experience, this series will guide you step-by-step. Let’s get started and learn about the exciting world of ESP32!

**Overview of ESP32**

The ESP32 is a versatile and powerful chip designed for a variety of smart devices. Here’s a quick look at its key features and specifications:

2. ### Key Features and Specifications:
    

* **WiFi and Bluetooth**: The ESP32 can connect to both WiFi and Bluetooth, making it ideal for many different wireless applications.
    
* **Dual-Core Processor**: It has two cores, which means it can handle multiple tasks at the same time, making it fast and efficient.
    
* **Low Power Consumption**: The ESP32 uses very little power, which is great for battery-powered projects.
    
* **Built-In Sensors**: It includes several built-in sensors, such as touch sensors, temperature sensors, and a hall sensor.
    
* **Rich Peripheral Support**: The ESP32 supports many peripherals like UART, SPI, I2C, and PWM, allowing it to connect to a wide range of sensors and devices.
    
* **High Processing Power**: It can handle complex calculations and processes quickly, thanks to its powerful CPU and ample memory.
    

3. ### Applications and Use Cases:
    

The ESP32 is used in a wide range of applications due to its flexibility and powerful features. Here are some common use cases:

* **Home Automation**: Control lights, thermostats, and other home devices remotely via WiFi.
    
* **Wearable Technology**: Create smartwatches, fitness trackers, and other wearable devices that can connect to your phone.
    
* **IoT Projects**: Build smart devices that can communicate with each other and the internet, such as smart sensors, security cameras, and connected appliances.
    
* **Wireless Networking**: Use the ESP32 to set up small networks of devices that can share data and interact with each other.
    
* **Industrial Automation**: Implement monitoring and control systems for various industrial applications, like temperature control, motor control, and equipment monitoring.
    
* **Robotics**: Develop robots that can sense and respond to their environment, communicate wirelessly, and perform complex tasks.
    

The ESP32 is a powerful tool for anyone interested in building smart devices and learning more about the Internet of Things (IoT). With its extensive features and wide range of applications, the possibilities are nearly endless.

**Setting Up the Development Environment**

To start working with the ESP32, you need to set up your development environment. Here are the required tools and software:

### Required Tools and Software:

1. **Visual Studio Code (VSCode)**
    
2. **ESP-IDF (Espressif IoT Development Framework)**
    
3. **Python and Git**
    

### Installing Visual Studio Code (VSCode):

1. **Download VSCode**: Go to the [Visual Studio Code website](https://code.visualstudio.com/Download) and download the version suitable for your operating system.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721496291192/099d34db-7124-4ab2-b618-4c80eb1234c9.png align="center")

1. **Install VSCode**: Follow the installation instructions on the website to install VSCode on your computer.
    

### Installing ESP-IDF Extension:

1. **Open VSCode**: Once installed, open Visual Studio Code.
    
2. **Install the Extension**: Click on the Extensions icon in the left sidebar. In the search bar, type "ESP-IDF" and install the official ESP-IDF extension by Espressif.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721496375509/03e666c4-f152-4778-bd7f-0bc68ae826cd.png align="center")

click on <mark>Configure Extension</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721496429512/d2a9934e-7cc1-4cf6-8783-2e622ae4579f.png align="center")

Choose <mark>Express </mark> first option.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721496458123/cb4ce7a7-7698-4b51-96a4-9b79cbdff35b.png align="center")

Make sure your <mark>configuration </mark> look like below Image and press Install.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721496530498/85f5b722-8140-4f09-93be-6379d42efacc.png align="center")

After Completion of Installation Click on ESP-IDF <mark>extension</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721496703213/119096fd-28ac-4765-b5fc-d1b4961605af.png align="center")

Then click on Show <mark>Example </mark> Then hello\_world

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721496938918/b65d3db6-f75c-47e4-8b49-345e75367c13.png align="center")

Now Click <mark>Create </mark> project using example

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721497014634/41e01b61-7d4f-4c4c-94bb-f4c8f8f3a9ec.png align="center")

Select <mark>Destination </mark> folder.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721497118927/848ced2c-c106-4b4d-afb2-0a67c9220790.png align="center")

If you able to get below image Window means you have successfully created a project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721497192417/f04985fb-34f8-4794-9c4d-36f84ffda4cf.png align="center")

Then click on main folder and open <mark>hello_world</mark>.c.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721497395641/94bc1951-7f9f-4b5f-a05e-9a3578942131.png align="center")

Now Select your <mark>com port</mark> and click on <mark>build project</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721497659208/2f0f1a3a-9a32-443f-bb2a-c4590ffd7fbf.png align="center")

You can see logs in the terminal window for every new project. The first build will take more time.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721497830983/cb5047e0-a261-4016-a1d8-fd7fa359380a.png align="center")

After successful build you will see below log in output tab.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721498002510/46ef98a6-def5-44e1-9722-306b356ff5d4.png align="center")

Now click on Flash Device and select <mark>UART</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721498084006/5b6eb8cb-f7a7-4e71-bc29-38e75affaf96.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721498139878/26bf040b-65c6-413b-8fd6-b22d9b506a36.png align="center")

You will see the message below in the terminal window. Then, <mark>press </mark> the <mark>boot button </mark> on the ESP32 for 3 <mark>seconds</mark>. After this, the flash will start automatically. If the flash starts before 3 seconds, then, you can <mark>release </mark> the boot button earlier.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721498320261/6ed2e030-b540-4a71-8c62-3d15641e31fc.png align="center")

After successful <mark>flash </mark> you can see below log on terminal window.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721498518728/0712b6c9-9f7c-4f99-90df-02f7ee720bb9.png align="center")

Now from ESP-IDF menu select <mark>Monitor </mark> tab.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721498633160/92bf7ac6-83a0-438d-9fb0-2fb6496d03e8.png align="center")

On serial monitor you can see **<mark>Hello world! </mark>** print and every 10 seconds esp32 will restart and again you can see same print with restarting countdown logs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721498875313/6f115fe6-35e6-4f2b-9955-be067e4239ce.png align="center")

Now you have successfully <mark>installed IDE</mark> and created <mark>Development environment for </mark> ESP-IDF.