When we hear the word operating system, we subconsciously think of operating systems such as Windows, Linux, Android, IOS and.. But operating systems are not just for computers or mobile phones. About 90% of digital systems have operating systems. Microcontrollers are no exception to this rule, and different operating systems are available for microcontrollers. In the following, we are going to talk about RTOS operating system.


# What is an operating system?

The operating system is a comprehensive software for user interaction with hardware. In fact, the operating system can be considered as an interface between the user and his requests from hardware. By installing and being placed on the operating system, various programs give their requests to the operating system, such as using RAM, using disk memory, using the network, and so on. The operating system will run after receiving the request.

Therefore, with the help of the operating system, we can easily run our programs on the desired system without having to deal with hardware details. In fact, the operating system has the role of resource management. Different programs require access to different hardware while running. The operating system manages the hardware resources, provides the required hardware to the program and thus allows the implementation of the program.


![Image of Yaktocat](https://digispark.ir/wp-content/uploads/2021/02/history-of-the-operating-system.png)


# What is Super Loop or RTOS ?

The usual programming method in which all commands fit into an infinite loop is called a Super Loop. This method is responsive to many simple codes. But in complex code, there are times when the processor needs to do several things at once, and parts such as timers and interrupts do not help. In these cases, the introduced method will not be responsible. The solution to overcome this limitation is to use the RTOS operating system. In the following code, you can see an example of a program with the Super Loop method.


```
Function Main_Function()
{
  Initialization();
  Do_Forever
  {
    Check_Status();
    Do_Calculations();
    Output_Response();
  }
}
```


__RTOS__ stands for Real Time Operating System. In fact, using this operating system on your microcontroller, you can divide your program into different tasks. In fact, RTOS is a software component that allows the processor to move quickly between tasks. Each task has an infinite loop inside, and the tasks run almost simultaneously. You can also use this operating system to select a priority for each task. In this way, if the task has a higher priority, the operating system first performs the priority task and then performs other tasks.

In RTOS operating system, each task is allocated a very short time. If the operating system is running a task and a higher priority task arrives, the operating system leaves the task where it is and goes to the higher priority task until it is the turn of the previous task again.Then the operating system continues the task from the dropped point.This feature is called __Multitasking__.



![Image of Yaktocat](https://digispark.ir/wp-content/uploads/2021/02/Figure-1.png)


## Why should we use RTOS?

Suppose you have to design a circuit that is placed on an industrial device to protect human life. Take the cutting machine, for example. You must design a circuit that, after detecting a human hand, immediately stops the device and holds the blade. In such a system, even a few moments of delay can cause irreparable damage. The need for a system to be real-time in such cases becomes clear. Other applications of RTOS include __car airbag system__ , which is very important to operate in a timely manner. Other benefits of RTOS include:


__1.__    Ability to schedule based on priority is a very powerful tool that allows the processor to perform important tasks faster than non-important ones.

__2.__    Modularity  :  Using RTOS makes coding to be done modularly. So it will be much easier to develop and reuse the code in the future.

__3.__    Team development upgrade : The task-based system allows separate designers and teams to work independently on different parts of their project

__4.__    Easier testing : Modular work based development allows modular work based testing.

__5.__    Reuse the code :  Another advantage of modular work is that similar programs on similar operating systems inevitably lead to create a library of standard tasks.

__5.__    System efficiency is greatly improved because no processing time is wasted on events that did not occur.



# What is freeRTOS?

FreeRTOS is a real-time operating system kernel for embedded devices that has been ported to 35 microcontroller platforms. It is distributed under the MIT License.


![Image of Yaktocat](https://digispark.ir/wp-content/uploads/2021/02/1_elMEPVMRFNKdpvVvZjLwoQ-300x174.png)

Developed in partnership with the world's leading chip companies over a 15-year period, and now downloaded every 175 seconds, FreeRTOS is a market-leading real-time operating system (RTOS) for microcontrollers and small microprocessors. Distributed freely under the MIT open source license, FreeRTOS includes a kernel and a growing set of libraries suitable for use across all industry sectors. FreeRTOS is built with an emphasis on reliability and ease of use.

FreeRTOS includes libraries for connectivity, security, and over-the-air (OTA) updates. FreeRTOS also includes demo applications that show FreeRTOS features on qualified boards.

FreeRTOS is an open-source project. You can download the source code, contribute changes or enhancements, or report issues on the GitHub site at https://github.com/aws/amazon-freertos .We release FreeRTOS code under the MIT open source license, so you can use it in commercial and personal projects.

We also welcome contributions to the FreeRTOS documentation (FreeRTOS User Guide, FreeRTOS Porting Guide, and FreeRTOS Qualification Guide). The markdown source for the documentation is available at https://github.com/awsdocs/aws-freertos-docs . It is released under the Creative Commons (CC BY-ND) license.




## History

The FreeRTOS kernel was originally developed by Richard Barry around 2003, and was later developed and maintained by Barry's company, Real Time Engineers Ltd. In 2017, Real Time Engineers Ltd passed stewardship of the FreeRTOS project to Amazon Web Services. Barry continues to work on FreeRTOS as part of an AWS team.



## Implementation

FreeRTOS is designed to be small and simple. The kernel itself consists of only three C files. To make the code readable, easy to port, and maintainable, it is written mostly in C, but there are a few assembly functions included where needed (mostly in architecture-specific scheduler routines).

FreeRTOS provides methods for multiple __threads__ or __tasks__ , __mutexes__ , __semaphores__ and __software timers__ . A tick-less mode is provided for low power applications. Thread priorities are supported. FreeRTOS applications can be completely statically allocated. Alternatively RTOS objects can be dynamically allocated with five schemes of memory allocation provided:

__•__   allocate only

__•__   allocate and free with a very simple, fast, algorithm

__•__   a more complex but fast allocate and free algorithm with memory coalescence

__•__   an alternative to the more complex scheme that includes memory coalescence that allows a heap to be broken across multiple memory areas

__•__   and C library allocate and free with some mutual exclusion protection

There are none of the more advanced features typically found in operating systems like Linux or Microsoft Windows, such as device drivers, advanced memory management, user accounts, and networking. The emphasis is on compactness and speed of execution. FreeRTOS can be thought of as a 'thread library' rather than an 'operating system', although command line interface and POSIX-like I/O abstraction add-ons are available.

FreeRTOS implements multiple threads by having the host program call a thread tick method at regular short intervals. The thread tick method switches tasks depending on priority and a __round-robin scheduling__ scheme. The usual interval is 1 to 10 milliseconds (1/1000 to 1/100 of a second), via an interrupt from a hardware timer, but this interval is often changed to suit a particular application.



## Key features

__•__  Book and reference manuals.

__•__  Small memory footprint, low overhead, and fast execution.

__•__  Tick-less option for low power applications.

__•__  Intended for both hobbyists and professional developers working on commercial products.

__•__  Scheduler can be configured for both preemptive or cooperative operation.

__•__  Coroutine support (coroutines in FreeRTOS are simple and lightweight tasks with limited use of the call stack)

__•__  Trace support through generic trace macros. Tools such as Tracealyzer by FreeRTOS partner Percepio can thereby record and visualize the runtime behavior of FreeRTOS-      based systems for debugging and verification. This includes task scheduling and kernel calls for semaphore and queue operations. Tracealyzer is a commercial tool.


## FreeRTOS versioning

The FreeRTOS kernel and components are released individually and use semantic versioning. Integrated FreeRTOS releases are made periodically. All releases use date-based versioning with the format YYYYMM.NN, where:

__•__  Y represents the year.

__•__  M represents the month.

__•__  N represents the release order within the designated month (00 being the first release).

For example, a second release in June 2021 would be 202106.01.
Previously, FreeRTOS releases used semantic versioning for major releases. Although it has moved to date-based versioning (FreeRTOS 1.4.8 updated to FreeRTOS AWS Reference Integrations 201906.00), the FreeRTOS kernel and each individual FreeRTOS library still retain semantic versioning. In semantic versioning, the version number itself (X.Y.Z) indicates whether the release is a major, minor, or point release. You can use the semantic version of a library to assess the scope and impact of a new release on your application.


LTS releases are maintained differently than other release types. Major and minor releases are frequently updated with new features in addition to defect resolutions. LTS releases are only updated with changes to address critical defects and security vulnerabilities. No new features are introduced in a given LTS release after launch. They are maintained for at least three calendar years after release, and provide device manufacturers the option to use a stable baseline as opposed to a more dynamic baseline represented by major and minor releases.


## FreeRTOS architecture

FreeRTOS is typically flashed to devices as a single compiled image with all of the components required for device applications. This image combines functionality for the applications written by the embedded developer, the software libraries provided by Amazon, the FreeRTOS kernel, and drivers and board support packages (BSPs) for the hardware platform. Independent of the individual microcontroller being used, embedded application developers can expect the same standardized interfaces to the FreeRTOS kernel and all FreeRTOS software libraries.

![Image of Yaktocat](https://docs.aws.amazon.com/freertos/latest/userguide/images/afreertos-architecture.png)

## FreeRTOS-qualified hardware platforms

__•__  ATECC608A Zero Touch Provisioning Kit for AWS IoT

__•__  Cypress CYW943907AEVAL1F Development Kit

__•__  Cypress CYW954907AEVAL1F Development Kit

__•__  Espressif ESP32-DevKitC

__•__  Espressif ESP-WROVER-KIT
 
__•__  Infineon XMC4800 IoT Connectivity Kit

__•__  Marvell MW320 AWS IoT Starter Kit

__•__  Marvell MW322 AWS IoT Starter Kit

__•__  MediaTek MT7697Hx Development Kit

__•__  Microchip Curiosity PIC32MZEF Bundle

__•__  Nordic nRF52840-DK

__•__  NuMaker-IoT-M487

__•__  NXP LPC54018 IoT Module

__•__  OPTIGA Trust X Security Solution

__•__  Renesas RX65N RSK IoT Module

__•__  STMicroelectronicsSTM32L4 Discovery Kit IoT Node

__•__  Texas Instruments CC3220SF-LAUNCHXL

__•__  Microsoft Windows 7 or later, with at least a dual core and a hard-wired Ethernet connection

__•__  Xilinx Avnet MicroZed Industrial IoT Kit


Qualified devices are also listed on the AWS Partner Device Catalog.

For information about qualifying a new device, see the FreeRTOS Qualification Guide.


[GitHub] (https://devices.amazonaws.com/detail/a3G0L00000AANvOUAX/ATECC608a-Zero-Touch-Provisioning-Kit-for-AWS-IoT)



## Derivations


### Amazon FreeRTOS
Amazon provides an extension of FreeRTOS, referred to as a:FreeRTOS. This is FreeRTOS with libraries for IOT support, specifically for Amazon Web Services. Since version 10.0.0 in 2017, Amazon has taken stewardship of the FreeRTOS code, including any updates to the original kernel

### SAFERTOS
SAFERTOS was developed as a complementary version of FreeRTOS, with common functionality but designed specifically for safety-critical implementation. FreeRTOS was subjected to HAZOP, and weaknesses were identified and resolved. The result was put through a full IEC 61508 SIL 3 development life cycle, the highest level for a software-only component.

SAFERTOS was developed by WITTENSTEIN High Integrity Systems, in partnership with Real Time Engineers Ltd, primary developer of the FreeRTOS project. Both SAFERTOS and FreeRTOS share the same scheduling algorithm, have similar APIs, and are otherwise very similar, but they were developed with differing objectives. SAFERTOS was developed solely in the C language to meet requirements for certification to IEC61508.

SAFERTOS can reside solely in the on-chip read only memory of a microcontroller for standards compliance. When implemented in hardware memory, SAFERTOS code can only be utilized in its original, already-certified, configuration. This means certification of systems do not need to re-test the kernel portion of their designs. SAFERTOS is included in the ROM of some Stellaris Microcontrollers from Texas Instruments. SAFERTOS source code does not need to be separately purchased. In this usage scenario, a C header file is used to map SAFERTOS API functions to their location in read-only memory.

### OPENRTOS
OPENRTOS is a commercially-licensed version of Amazon FreeRTOS, sold by WITTENSTEIN High Integrity Systems. This product provides support and allows companies to use the Amazon FreeRTOS kernel and libraries without the a:FreeRTOS MIT license.



