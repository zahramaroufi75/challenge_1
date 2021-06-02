When we hear the word operating system, we subconsciously think of operating systems such as Windows, Linux, Android, IOS and.. But operating systems are not just for computers or mobile phones. About 90% of digital systems have operating systems. Microcontrollers are no exception to this rule, and different operating systems are available for microcontrollers. In the following, we are going to talk about RTOS operating system.

## What is an operating system?
The operating system is a comprehensive software for user interaction with hardware. In fact, the operating system can be considered as an interface between the user and his requests from hardware. By installing and being placed on the operating system, various programs give their requests to the operating system, such as using RAM, using disk memory, using the network, and so on. The operating system will run after receiving the request.

Therefore, with the help of the operating system, we can easily run our programs on the desired system without having to deal with hardware details. In fact, the operating system has the role of resource management. Different programs require access to different hardware while running. The operating system manages the hardware resources, provides the required hardware to the program and thus allows the implementation of the program.
No hassle with hardware details


![Image of Yaktocat](https://digispark.ir/wp-content/uploads/2021/02/history-of-the-operating-system.png)

##  What is Super Loop or RTOS ?
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
