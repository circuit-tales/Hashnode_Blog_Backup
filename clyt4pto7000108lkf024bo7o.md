---
title: "A Step-by-Step Guide to ESP32 OTA Updates with OTA Drive"
seoTitle: "Step-by-Step Guide to ESP32 OTA Updates Using OTA Drive Platform"
seoDescription: "Learn how to perform OTA updates on your ESP32 devices using the OTA Drive platform. This step-by-step guide covers setup, configuration, and testing for se"
datePublished: Thu Jul 18 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clyt4pto7000108lkf024bo7o
slug: a-step-by-step-guide-to-esp32-ota-updates-with-ota-drive
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1721545440779/ab6f8213-d1dc-4b1c-b1d1-a1611ebb2746.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1721419376879/c3c53f15-193b-497f-8bb4-4836e56946c4.webp
tags: c-programming, iot, micro-controllers, vscode-cjevho8kk00bo1ss2lmqqjr51, firmware-development, esp32, embedded-systems, iot-security, iot-development-services, techtutorials, otaupdates, espidf, esp32projects, wifiprogramming

---

Keeping your IoT devices up-to-date is crucial for performance and security. Over-the-Air (OTA) updates offer a seamless way to deploy firmware updates to your ESP32 devices without physical access. In this guide, we will explore how to use the OTA Drive platform to perform OTA updates on ESP32, ensuring your devices stay current with minimal effort.

### Introduction to OTA Updates

Over-the-Air (OTA) updates allow you to remotely update the firmware of your IoT devices. This is especially useful for devices like the ESP32, which are often deployed in inaccessible locations. OTA updates eliminate the need for physical access, making the process efficient and convenient.

### Setting Up Your ESP32 for OTA

Before we can perform OTA updates, we need to set up our ESP32 using the ESP-IDF platform in VSCode. Here’s what you need to do:

1. **Install VSCode:** If you haven't already, download and install [Visual Studio Code](https://code.visualstudio.com/).
    
2. **Install ESP-IDF Extension:** In VSCode, go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window. Search for "ESP-IDF" and install the official extension by Espressif.
    
3. **Set Up ESP-IDF Tools:** Follow the setup instructions provided by the ESP-IDF extension to install the necessary tools. This typically involves installing Python, Git, and the ESP-IDF itself.
    
4. **Clone ESP-IDF Repository:** Open a terminal in VSCode and clone the ESP-IDF repository by running:
    
    ```bash
    git clone https://github.com/circuit-tales/ESP32_simple_fota_OTA_drive
    ```
    
5. **Connect Your ESP32:** Connect your ESP32 to your computer using a USB cable. Ensure the correct serial port is selected in the ESP-IDF settings in VSCode.
    

### Overview of OTA Drive Platform

OTA Drive is a powerful platform designed to facilitate OTA updates for IoT devices. It offers a user-friendly interface, secure firmware hosting, and comprehensive update management features. With OTA Drive, you can easily manage and deploy firmware updates to your ESP32 devices.

### Configuring OTA Drive

1. **Sign Up:** Go to the [OTA Drive website](https://www.otadrive.com) and create an account.
    
2. **Add Product :** Once logged in, Go to Product tab and add product as ESP32 devices.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721408096715/c107d415-92f2-4fe4-9fa5-645b1bb67ff7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721408391424/b5fcd458-6691-47ab-86de-385a28a1f27b.png align="center")

Provide a name and description for your Product. Optionally you can add Image also

you can say it's nice feature for Identification.

Click on folder Icon You will see this screen

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcd-V7rj6sszN7Bj0kY_6oPoCfc-dYf12Ar_rv_mG4qvllJzkPbBaYJ0iyjhgJiorz2NU3Cc43fM3tpN7n14pDKJQgHBhBsPlW-YUKcCD6ywXKEDMh7ugYj8Pbw2nmOtZfl5rsDZEvaRzQpO29vKYlpXa4?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

6. **Open SDK Configuration:**
    
    * In VSCode, open the SDK configuration settings and ensure the necessary options are correctly set.
        
    * ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721417908436/c7c58501-c111-4a6a-b2be-2b0b5371f8d5.png align="center")
        
    * Navigate through the configuration menu to make sure all required settings for OTA updates are enabled.
        
    * ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcawhgIa53kqEvtnFtT0IOXhoPLqZGq20yzuBOeErKj9ZLCIcyOgOShMI-2UqeNZXBcITx1wjWgwslVnzpOI9aXWDH-JWbcptuVEZEnp8N1SPJQAX7iLcXd-CuJ6X7DEviSf3kE3VYAT9i5Q9iTn4aZox2w?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
        
    * ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXe15PS_riOOHKwM6nx__9s9flg01_nxc2bm2OWuXn0Rt-1H-O5_5mFvkAOLWxNqNrOXErsYUpkE1vrp71DZvArwWE0dxNhq6OYR7kVr_W58m65_zptNQYBnvpGvxHpTbcwWX8UFdGbnMQX45qK49EvMuvXA?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
        
7. **Edit main.c File:**
    
    * Open `main.c` and comment out the highlighted lines. This will temporarily disable parts of your code for the initial setup.
        
    * Update your WiFi credentials by replacing `your_SSID` and `your_PASSWORD` with your actual network details.
        
    * ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXf_XAWEJ5fSoLD0Bf10iNYwyyr-qKaDRYj1RNzy6FnRH94lD5Qn4MyKUQLjUFUa34gecQsdEoBHjfcmtxxQF4KB2gNPXzd2Wng9uDvUXI5snTlVaS91qOsf1l0lBeXMCMzh36jYrRtTipFe964AeL-HoPAj?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
        
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeu4LLunMv0uQ-ZIQb5V1WAuIaJr5tW5YoAbUkvl4S7OSqWrFE4wnxq77FOpqyDARBfWIjqmkMuSpl4pkzSESnnFMwE9RtH7mA5j0AM4fpTuRG3VOJCB82-0j2e_bBVEitY-wsmTYrE-sBWrKoxUVyYdmFV?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
8. **Copy API Key:**
    
    * From the OTA Drive dashboard, copy your unique API key.
        
        ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXclaQeUZYm8M_zj606iP9wAwoZaWQ10XnQDAAeMY1BumKPqlUpTN60Xqf-4DzQKTXXadclNDxBge1hLBgF-dYYSSP1YnGhmyuDzL5JWr_70FPGk5Uu00ObvFPvAOn4cDyufzdEsz-Mk04koSDHm7EEaKllT?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
        
    * Paste this API key into your `main.c` file where specified. Optionally, you can also update the `app_version` for easier tracking.
        

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXd9mzon0Tm18CbQW1E_pgJn2MCYP2jlO1x4Kq3KEAhrLvbg6kpiQJQQujgnC1juePkesbIKrg_-h6wzR8TPSpjcZtMDya5zl86TtYdw7Wucaeh2vjiQ2MCwh-KXNfpUWzAReZSQp7EqtxbvnDY_SnyzJnWl?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

6. **Build the Project:**
    
    * At the bottom of the VSCode window, click on the 'Build' button to compile your project. Note that the initial build may take some time.
        

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcXGWi83MD7RD3Dd02McZ8drVKpKScqfNeNDoZvItFv3LjsCIPGdpVr4HBchfqzSFS0-_dUaB8FEyn-bps3P9eVrcNHDYv60IAhKZYnlGWElOXclKxeftX-Y5rMhM3JVcpLCv8RvEyiAZyXeufCQ47WhRWy?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

6. **Flash the Firmware:**
    
    * After successful build you will see below log in output tab
        
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcssRLQeA_PyijDTBnpYia4yQikvZdD5vXErFsOCfShlGmSoxoPAtgyS7iKFqKocC6Qhj7Qy2XN44mC_aGa3WOZ9q-AnR35SlKr7KwUCMmsWO2qGukW5C5d6hUJVIJWshdYc6IXbk5kzU5YfAVvnNi5nYc?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    * After a successful build, select 'UART' to prepare for flashing the firmware.
        
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfZPhoZfDiTUAF9dVXMxDhpJDTF8B-M8juq0JN9addGYVbxNhM638uY1VT-A8NptHrvGJ1DQ1iQWShePgXNrQnwp2yzekom4PHeQ_bIaQaE1Z7Tx--lxmjefKsOqc82E82dFVVvo8qHsvCvaIvc8p9QcJbl?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    * Ensure your ESP32 is connected to the correct COM port, then click 'Flash'.
        
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfLuzwkuXElxOqsdfz4cJWYE0OvL3UfcmHf07CfBGtFVDOGLhE1FWcE0nKLRJ1grkCDS8Bu8eJlB0H9prgSwywS8Fb7wyA2qMaN4Kn_lOTr1oNbzZN-s-5wBCkrktxYIx8N7jywl_h7fpzS5LFbyMjlbj25?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    * If you see a 'Connecting' message, press and hold the boot button on your ESP32 for 3 seconds and then release it.
        
        ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcFT0g0jhAwhfLG02yzdwc9r-Afeb3eMQIQcgiBXQMGJMHeU626RHynxlmr8QBtQeHms9EpkQdu3c4kdhnB3DzkXkwnvUAedynGmbPSotvcM4NPvt2-YCCPoNll_iBKli7ytoR_JMFDgPju5KCzkkPRiTc?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
        
7. **Verify the Flashing Process:**
    
    * Upon successful flashing, you should see a confirmation message in the output tab of VSCode.
        
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcW5-UW3h7-FmAbZ_ntqFLmToDRRNSrUQQ4KFeHzPQ3I9DpdNzY3mRdu5K8Q7KngXUo4Xp65xbaE_R7iNo0gE0U2xzTKNumU-4LUqE8rpDeVI_KWnqLxc2SnqGlXfqeT8VE3QK0rFnlYXyELk8Wzui7RiYP?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    * Check your ESP32 board. At this stage, only the red LED should be glowing.
        

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXf9Jz87gq94E-MmveEbf5s6NEKPKKCAbYPdCyjB31Lf2jKHLoJ0eCgEUQ22AYOBSg-Qu0mj3JMetWEkEtwwr2pZIGnSZsoIl3A0oCHQtdQeb42urGpbZtOsfvRMOeWacIMG4a6Xmop_7o-DqOoCV7y9yCI?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

6. **Verify Device on OTA Drive:**
    
    * Reload the OTA Drive dashboard page. You should now see your ESP32 device listed.
        
    * ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfqZDGdIlOrrq8l7wf7nU5j4dg3aOUREb1dqLcp3jXm37wHmVy8u7Us9_3Fqq6CRGgKfUKCHc-wSppo6TgOxUOfTkd1dkpNmzIScnyK45VeHnTw9dXsmpUzft0rFSpmffZBN56Dvjd7XdiVhaefxLqIfxo5?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
        
    * Go to the 'Devices' section, click on 'Verify', and confirm by clicking 'OK'.
        
    * ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdkva73C3uUYeiCSQtAceApy-7bobF-1pX_UPuaie2Ging4UHp8PIbsIQa-3OoYBFveO7LLEOGj76Sdw32c0MoWjaSIV8awmGz13AYU1pxizUyd9jbP9uzTBGDp4v5ABugf7UdgFEDMnZmphnpb_nN_OR_2?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
        
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdqRDHFsd4qRTb-H37x2_wV45k15lu7bYHXxG0aJAtHQ0vpgzTssOD54slKhkO_mkmJhpQ4CEGg4QIKcA9iSE9ssXaGb3W0Rx8gLvi3d8H1NjyyTkHBoRufClwAHrTgjUD-_BRvRil-lCHeLRgLfXXkqm_S?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    Now uncomment previous lines
    
7. ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfpbC8M7bLMqCZkwJcMVhrOW84diYDHkSQGMigtVDnv8orHKSsNwuR4bhPOhQZkHUAhVCGT_Lp416JVVeNYNsHhzZ0rM5QFnc1Pqdx6fjPbNZTTgZzTR4xoTwgKS0HBAzUobRUVzuisfEGZwge24pYBg_Y?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfucY8l4HdgdvKgd58rasnb5nPfIpO3W9_GDw_0mzwBbiwvSKbgZWzLcGxHQyOdT-F6oQdn4vIuP3RpKni-ol3Q20V2xdVGyNSowtdYBscCE8yAgLIvPSpfNk4JDt8LHscydg1KpFdAI0NzjzmrTanEpmrg?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    Also you can change version here for tracking
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXckA8wWtpcxYjx34R3P_JQ04YuozMJ2ojtaTspwvurSKo5VCiBVilKOvZQPbuChInBIwE3nnaoInLK9OIclkytuwI3PzNNY4rrDjpUKm6iax8GATckeexFEBa6uVwTNOFXs7NldxliBtxLNU-D2QF0cQ-o?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

8. Now again build but dont flash this time we need to upload flash file to ota drive and over the air it will flash
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcXGWi83MD7RD3Dd02McZ8drVKpKScqfNeNDoZvItFv3LjsCIPGdpVr4HBchfqzSFS0-_dUaB8FEyn-bps3P9eVrcNHDYv60IAhKZYnlGWElOXclKxeftX-Y5rMhM3JVcpLCv8RvEyiAZyXeufCQ47WhRWy?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
9. Now open the project folder in the file explorer and go to the build folder. Select the highlighted .bin file.
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdXNDVhO4gGVzXQk8mlht9ROfbnvAiedVs30sJasK4OUhOvKyFlOcnniqL8cScyB3LW8icuFtpmi5Auo4yiucrak3l3kdT5JPmh0IhjBuWJ5-gSHtZPGyyDWmM33Y3lUgJHJXUXFpUTEOS1YMeed1up5Xcd?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

10. Now click on 'Upload Firmware' and upload this .bin file, or you can simply drag and drop it.
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeA6vTnryaa8hQrwvKTiGHXJChBki1asklbrdKBsRvOtrC4a1LZMl3d9qBkK01HxBZ9CVN_-r08cya_L62_m8aztP66Q11KPHcBZkfmI-4X9uGZPdmXvcKgmDwFjCYfzaCQGvZwq2DFFwtbjZdMwLH9gll2?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

11. After uploading the .bin file, select 'default' to see the updated version of our firmware. Then, click on 'upload'.
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXepm7iPsP6_fdRTPqiDdAdYVI-bgiHG027k6e-Gc5jbgDQAjk3FELK1KHqdgQ7qWiUIF_a5gsrDRYWnq_y1wYvHaF0IZ2D3fZjO_okl3BrDAdlHs0Lk_xuvYPR69nP1qIZYh1XT_19i4CIrQINhUu1D6sxV?key=MbTIV1rKWQSQMOzSR6qI4A align="left")

12. Now go to the 'Devices' section, click on the device folder icon, and you will see that FOTA has started.
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdTBCNV8R7lAaaT4uovPI-iwVxW0ht8B68EN2Jveq59rJTiVmV5MV61wpW08ZjcjoqMFX56TrqosVXD9Bo3FKZgFU7hjp0t7nWf33bS_2qcOJ4wuhS7t0ydD3HqqzOvkcOf6re_TKC55QciVA4Gk2RZINfO?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
13. FIRMWARE OVER THE AIR completed
    
    You should now see the blue LED blinking.
    
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeRMa39U1Hh37_jcuZ9x3hQzpP2Nx2_yIpUw9pfaApUQon0f__gE90AX-CkEHMfpzMDpglI-nmXejf2vYOFk2JSFo6kX0hGcrmVPujwy8eNfo3XUwxViHKD_AsY74tUm21Vzu5l3UTgGf9c__yRSdpr9Ek?key=MbTIV1rKWQSQMOzSR6qI4A align="left")
    
    **If you found this guide helpful, please leave a comment below and share it with your peers. Follow my blog, Circuit Tales, for more insights and tutorials on embedded systems and IoT. Stay tuned for more!**
    
    ---
    
    # \===========THE END==========