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

__???__   allocate only

__???__   allocate and free with a very simple, fast, algorithm

__???__   a more complex but fast allocate and free algorithm with memory coalescence

__???__   an alternative to the more complex scheme that includes memory coalescence that allows a heap to be broken across multiple memory areas

__???__   and C library allocate and free with some mutual exclusion protection

There are none of the more advanced features typically found in operating systems like Linux or Microsoft Windows, such as device drivers, advanced memory management, user accounts, and networking. The emphasis is on compactness and speed of execution. FreeRTOS can be thought of as a 'thread library' rather than an 'operating system', although command line interface and POSIX-like I/O abstraction add-ons are available.

FreeRTOS implements multiple threads by having the host program call a thread tick method at regular short intervals. The thread tick method switches tasks depending on priority and a __round-robin scheduling__ scheme. The usual interval is 1 to 10 milliseconds (1/1000 to 1/100 of a second), via an interrupt from a hardware timer, but this interval is often changed to suit a particular application.



## Key features

__???__  Book and reference manuals.

__???__  Small memory footprint, low overhead, and fast execution.

__???__  Tick-less option for low power applications.

__???__  Intended for both hobbyists and professional developers working on commercial products.

__???__  Scheduler can be configured for both preemptive or cooperative operation.

__???__  Coroutine support (coroutines in FreeRTOS are simple and lightweight tasks with limited use of the call stack)

__???__  Trace support through generic trace macros. Tools such as Tracealyzer by FreeRTOS partner Percepio can thereby record and visualize the runtime behavior of FreeRTOS-      based systems for debugging and verification. This includes task scheduling and kernel calls for semaphore and queue operations. Tracealyzer is a commercial tool.


## FreeRTOS versioning

The FreeRTOS kernel and components are released individually and use semantic versioning. Integrated FreeRTOS releases are made periodically. All releases use date-based versioning with the format YYYYMM.NN, where:

__???__  Y represents the year.

__???__  M represents the month.

__???__  N represents the release order within the designated month (00 being the first release).

For example, a second release in June 2021 would be 202106.01.

Previously, FreeRTOS releases used semantic versioning for major releases. Although it has moved to date-based versioning (FreeRTOS 1.4.8 updated to FreeRTOS AWS Reference Integrations 201906.00), the FreeRTOS kernel and each individual FreeRTOS library still retain semantic versioning. In semantic versioning, the version number itself (X.Y.Z) indicates whether the release is a major, minor, or point release. You can use the semantic version of a library to assess the scope and impact of a new release on your application.

LTS releases are maintained differently than other release types. Major and minor releases are frequently updated with new features in addition to defect resolutions. LTS releases are only updated with changes to address critical defects and security vulnerabilities. No new features are introduced in a given LTS release after launch. They are maintained for at least three calendar years after release, and provide device manufacturers the option to use a stable baseline as opposed to a more dynamic baseline represented by major and minor releases.


## FreeRTOS architecture

FreeRTOS is typically flashed to devices as a single compiled image with all of the components required for device applications. This image combines functionality for the applications written by the embedded developer, the software libraries provided by Amazon, the FreeRTOS kernel, and drivers and board support packages (BSPs) for the hardware platform. Independent of the individual microcontroller being used, embedded application developers can expect the same standardized interfaces to the FreeRTOS kernel and all FreeRTOS software libraries.

![Image of Yaktocat](https://docs.aws.amazon.com/freertos/latest/userguide/images/afreertos-architecture.png)


## FreeRTOS-qualified hardware platforms

__???__  [ATECC608A Zero Touch Provisioning Kit for AWS IoT](https://devices.amazonaws.com/detail/a3G0L00000AANvOUAX/ATECC608a-Zero-Touch-Provisioning-Kit-for-AWS-IoT)

__???__  [Cypress CYW943907AEVAL1F Development Kit](https://devices.amazonaws.com/detail/a3G0L00000AAPg0UAH/CYW943907AEVAL1F)

__???__  [Cypress CYW954907AEVAL1F Development Kit](https://devices.amazonaws.com/detail/a3G0L00000AAPg5UAH/CYW954907AEVAL1F)

__???__  [Espressif ESP32-DevKitC](https://devices.amazonaws.com/detail/a3G0L00000AANtjUAH/ESP32-WROOM-32-DevKitC)

__???__  [Espressif ESP-WROVER-KIT](https://devices.amazonaws.com/detail/a3G0L00000AANtlUAH/ESP-WROVER-KIT)
 
__???__  [Infineon XMC4800 IoT Connectivity Kit](https://devices.amazonaws.com/detail/a3G0L00000AANsbUAH/XMC4800-IoT-FreeRTOS-Connectivity-Kit-WiFi)

__???__  [Marvell MW320 AWS IoT Starter Kit](https://devices.amazonaws.com/detail/a3G0h000000OaRnEAK/MW320-AWS-IoT-Starter-Kit)

__???__  [Marvell MW322 AWS IoT Starter Kit](https://devices.amazonaws.com/detail/a3G0h000000OblKEAS/MW322-AWS-IoT-Starter-Kit)

__???__  [MediaTek MT7697Hx Development Kit](https://devices.amazonaws.com/detail/a3G0L00000AAOmPUAX/MT7697Hx-Development-Kit)

__???__  [Microchip Curiosity PIC32MZEF Bundle](https://devices.amazonaws.com/detail/a3G0L00000AANscUAH/Curiosity-PIC32MZ-EF-FreeRTOS-Bundle)

__???__  [Nordic nRF52840-DK](https://devices.amazonaws.com/detail/a3G0L00000AANtrUAH/nRF52840-Development-Kit)

__???__  [NuMaker-IoT-M487](https://devices.amazonaws.com/detail/a3G0h000000Tg9cEAC/NuMaker-IoT-M487)

__???__  [NXP LPC54018 IoT Module](https://devices.amazonaws.com/detail/a3G0L00000AAOkeUAH/Renesas-Starter-Kit-for-RX65N-2MB)

__???__  [OPTIGA Trust X Security Solution](https://devices.amazonaws.com/detail/a3G0h000007712QEAQ/OPTIGA-Trust-X-Security-Solution)

__???__  [Renesas RX65N RSK IoT Module](https://devices.amazonaws.com/detail/a3G0L00000AAOkeUAH/Renesas-Starter-Kit-for-RX65N-2MB)

__???__  [STMicroelectronicsSTM32L4 Discovery Kit IoT Node](https://devices.amazonaws.com/detail/a3G0L00000AANsWUAX/STM32L4-Discovery-Kit-IoT-Node)

__???__  [Texas Instruments CC3220SF-LAUNCHXL](https://devices.amazonaws.com/detail/a3G0L00000AANtaUAH/SimpleLink-Wi-Fi-CC3220SF-Wireless-Microcontroller-LaunchPad-Development-Kit)

__???__  Microsoft Windows 7 or later, with at least a dual core and a hard-wired Ethernet connection

__???__  [Xilinx Avnet MicroZed Industrial IoT Kit](https://devices.amazonaws.com/detail/a3G0L00000AANtqUAH/MicroZed-IIoT-Bundle-with-FreeRTOS)


Qualified devices are also listed on the [AWS Partner Device Catalog](https://devices.amazonaws.com/search?page=1&sv=freertos).

For information about qualifying a new device, see the [FreeRTOS Qualification Guide](https://docs.aws.amazon.com/freertos/latest/qualificationguide/afr-qualification.html).


## Development workflow

You start development by downloading FreeRTOS. You unzip the package and import it into your IDE. You can then develop an application on your selected hardware platform and manufacture and deploy these devices using the development process appropriate for your device. Deployed devices can connect to the AWS IoT service or AWS IoT Greengrass as part of a complete IoT solution.

![Image of Yaktocat](https://docs.aws.amazon.com/freertos/latest/userguide/images/afr-getting-started-workflow.png)



## FreeRTOS kernel fundamentals

The FreeRTOS kernel is a real-time operating system that supports numerous architectures. It is ideal for building embedded microcontroller applications. It provides:

__???__  A multitasking scheduler.

__???__  Multiple memory allocation options (including the ability to create completely statically-allocated systems).

__???__  Intertask coordination primitives, including task notifications, message queues, multiple types of semaphore, and stream and message buffers.


The FreeRTOS kernel never performs non-deterministic operations, such as walking a linked list, inside a critical section or interrupt. The FreeRTOS kernel includes an efficient software timer implementation that does not use any CPU time unless a timer needs servicing. Blocked tasks do not require timeconsuming periodic servicing. Direct-to task notifications allow fast task signaling, with practically no RAM overhead. They can be used in most intertask and interrupt-to-task signaling scenarios.

The FreeRTOS kernel is designed to be small, simple, and easy to use. A typical RTOS kernel binary image is in the range of 4000 to 9000 bytes.

For the most up-to-date documentation about the FreeRTOS kernel, see [FreeRTOS.org](https://freertos.org/RTOS.html) . FreeRTOS.org offers a number of detailed tutorials and guides about using the FreeRTOS kernel, including a [Quick Start Guide](https://freertos.org/FreeRTOS-quick-start-guide.html#page_top) and the more in-depth [Mastering the FreeRTOS Real Time Kernel](https://freertos.org/Documentation/161204_Mastering_the_FreeRTOS_Real_Time_Kernel-A_Hands-On_Tutorial_Guide.pdf).


### FreeRTOS kernel scheduler

An embedded application that uses an RTOS can be structured as a set of independent tasks. Each task executes within its own context, with no dependency on other tasks. Only one task in the application is running at any point in time. The real-time RTOS scheduler determines when each task should run. Each task is provided with its own stack. When a task is swapped out so another task can run, the task???s execution context is saved to the task stack so it can be restored when the same task is later swapped
back in to resume its execution.

To provide deterministic real-time behavior, the FreeRTOS tasks scheduler allows tasks to be assigned strict priorities. RTOS ensures the highest priority task that is able to execute is given processing time. This requires sharing processing time between tasks of equal priority if they are ready to run simultaneously. FreeRTOS also creates an idle task that executes only when no other tasks are ready to run.



### Memory management

This section provides information about kernel memory allocation and application memory management.


#### __Kernel memory allocation__

The RTOS kernel needs RAM each time a task, queue, or other RTOS object is created. The RAM can be allocated:

__???__ Statically at compile time.

__???__ Dynamically from the RTOS heap by the RTOS API object creation functions.


When RTOS objects are created dynamically, using the standard C library malloc() and free() functions is not always appropriate for a number of reasons:

__???__ They might not be available on embedded systems.

__???__ They take up valuable code space.

__???__ They are not typically thread-safe.

__???__ They are not deterministic.

For these reasons, FreeRTOS keeps the memory allocation API in its portable layer. The portable layer is outside of the source files that implement the core RTOS functionality, so you can provide an application-specific implementation appropriate for the real-time system you're developing. When the RTOS kernel requires RAM, it calls pvPortMalloc() instead of malloc()(). When RAM is being freed,the RTOS kernel calls vPortFree() instead of free().


#### __Application memory management__

When applications need memory, they can allocate it from the FreeRTOS heap. FreeRTOS offers several heap management schemes that range in complexity and features. You can also provide your own heap implementation.

The FreeRTOS kernel includes five heap implementations:

heap_1

Is the simplest implementation. Does not permit memory to be freed.


heap_2

Permits memory to be freed, but not does coalesce adjacent free blocks.


heap_3

Wraps the standard malloc() and free() for thread safety.


heap_4

Coalesces adjacent free blocks to avoid fragmentation. Includes an absolute address placement option.


heap_5

Is similar to heap_4. Can span the heap across multiple, non-adjacent memory areas.




## Derivations of FreeRTOS


### Amazon FreeRTOS

Amazon provides an extension of FreeRTOS, referred to as a:FreeRTOS. This is FreeRTOS with libraries for IOT support, specifically for Amazon Web Services. Since version 10.0.0 in 2017, Amazon has taken stewardship of the FreeRTOS code, including any updates to the original kernel


### SAFERTOS

SAFERTOS was developed as a complementary version of FreeRTOS, with common functionality but designed specifically for safety-critical implementation. FreeRTOS was subjected to HAZOP, and weaknesses were identified and resolved. The result was put through a full IEC 61508 SIL 3 development life cycle, the highest level for a software-only component.

SAFERTOS was developed by WITTENSTEIN High Integrity Systems, in partnership with Real Time Engineers Ltd, primary developer of the FreeRTOS project. Both SAFERTOS and FreeRTOS share the same scheduling algorithm, have similar APIs, and are otherwise very similar, but they were developed with differing objectives. SAFERTOS was developed solely in the C language to meet requirements for certification to IEC61508.

SAFERTOS can reside solely in the on-chip read only memory of a microcontroller for standards compliance. When implemented in hardware memory, SAFERTOS code can only be utilized in its original, already-certified, configuration. This means certification of systems do not need to re-test the kernel portion of their designs. SAFERTOS is included in the ROM of some Stellaris Microcontrollers from Texas Instruments. SAFERTOS source code does not need to be separately purchased. In this usage scenario, a C header file is used to map SAFERTOS API functions to their location in read-only memory.


### OPENRTOS

OPENRTOS is a commercially-licensed version of Amazon FreeRTOS, sold by WITTENSTEIN High Integrity Systems. This product provides support and allows companies to use the Amazon FreeRTOS kernel and libraries without the a:FreeRTOS MIT license.



## Additional resources

These resources might be helpful to you.

__???__ Additional [FreeRTOS Documentation](https://www.freertos.org/Documentation/RTOS_book.html) is available on [freertos.org](https://www.freertos.org/) including the [FreeRTOS v10.0.0 Reference Manual](https://www.freertos.org/fr-content-src/uploads/2018/07/FreeRTOS_Reference_Manual_V10.0.0.pdf).

__???__ For questions about FreeRTOS for the FreeRTOS engineering team, you can open an issue [on the FreeRTOS GitHub page](https://github.com/aws/amazon-freertos/issues).

__???__ For technical questions about FreeRTOS visit the [FreeRTOS Community Forums](https://forums.freertos.org/).

__???__ For more information about connecting devices to AWS IoT, see the [AWS IoT Core Developer Guide](https://docs.aws.amazon.com/iot/latest/developerguide/what-is-aws-iot.html) and the chapter on [Device Provisioning](https://docs.aws.amazon.com/iot/latest/developerguide/iot-provision.html) in that guide.

__???__ For technical support for AWS, visit the [AWS Support Center](https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Fconsole.aws.amazon.com%2Fsupport%2Fhome%3Fstate%3DhashArgs%2523%26isauthcode%3Dtrue&client_id=arn%3Aaws%3Aiam%3A%3A015428540659%3Auser%2Fsupportcenter&forceMobileApp=0&code_challenge=YFEvgwNSzkwGYciU8NX7O-DyaORK58WD4OyMjo6_AQc&code_challenge_method=SHA-256).

__???__ For questions about AWS billing, account services, events, abuse, or other issues with AWS, visit the [Contact Us](https://aws.amazon.com/contact-us/) page.
