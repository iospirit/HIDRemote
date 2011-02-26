## About the HIDRemote class

The HIDRemote Objective-C class provides your application with access to the Apple® Remote IR Receiver under OS X 10.4 (Tiger), OS X 10.5 (Leopard) and OS X 10.6 (Snow Leopard). It is available under a BSD-style license.

## Why you'll want to use the HIDRemote class

The HIDRemote class was developed with the needs of users, standalone applications, media center software, background applications, remote control solutions, drivers and Apple® Remote emulators in mind. The primary goals are to maximize compatibility, interoperability, future-proofness and user-friendlyness. In fact, the more developers use it for supporting the Apple® Remote in their applications, the better the system-wide user experience will be for everyone.

## Features

- Smart, flexible event handling
The HIDRemote class uses the HID system supplied information about the IR Receiver HID Device to build a dynamic button-cookie map it can then use to understand incoming events regardless of the layout of the HID device's HID descriptor. Hence, HIDRemote doesn't need any OS release or driver specific event handling code, making it a user-friendly and flexible choice for developers that's well prepared for the future.

- Support for the white (plastic) and aluminum Apple® Remote
The HIDRemote class auto-detects the remote in use and allows you to determine the remote control type with a single call. Your delegate receives messages for all buttons. Under OS 10.6.2 and later, an extra button code is used for the new, additional Play/Pause button of the new aluminum version.

- Shared, exclusive and exclusive-auto modes
The HIDRemote class can share access with OS X or access it exclusively. Additionally, the exclusive-auto mode can automatically establish/relinquish exlusive access to the remote alongside the application becoming active/inactive.

- Exclusive Lock Lending
Some background applications need to have an exclusive lock on the IR Receiver to implement their task. Consequently, other applications are not able to get access to the IR Receiver (and thus the remote) at the same time. This is something that both developers and users will not want.

The HIDRemote class addresses this issue with its Exclusive Lock Lending feature. It allows aforementioned background applications to "lend" their exclusive lock to other applications for as long as these need it. Example: a background launcher application listens for presses of the Menu button with an exclusive lock. The user starts a slideshow application with remote control support. If both use the HIDRemote class, the slideshow application can ask the background launcher application to temporarily relinquish its lock, so itself can gain access. When the slideshow application stops using the remote or is quit by the user, it notifies the background launcher that it no longer needs access and the background launcher can re-establish its exclusive lock.

With this mechanism in place, users can control both the slideshow and background application in a naturally feeling way.

- Provides detailed metadata to drivers and remote control solutions for seamless integration
With the HIDRemote class, applications can "broadcast" detailed metadata about their remote control support and usage via distributed notifications. This includes the current status (turned off, shared, exlusive or exclusive-auto acccess) and an application-definable list of unused button codes.

This metadata can be used by the Exclusive Lock Lending feature, drivers and remote control solutions (such as Remote Buddy) to deliver the best possible integration and user experience.

- Support for deep sleep
The HIDRemote class will automatically re-acquire access to the IR Receiver when a Mac® wakes up from deep sleep (more widely known as "hibernation").

- Support for multiple devices
Built from ground up to support multiple devices, the HIDRemote class enables applications using it to receive button press events from more than one HID device at a time. This removes a substantial bottleneck for third party developers that wish to implement an Apple® Remote emulation as well as for developers that want their applications to be compatible with them.

- Built-In compatibility checks
The HIDRemote class generally works completely independant from Candelair. It, however, needs the support of Candelair under OS releases where establishing an exclusive lock on the IR Receiver is otherwise not possible (currently this is only the case under 10.6 and 10.6.1). For your convenience, the HIDRemote class provides a method that can be used to determine whether Candelair is required under a particular OS release. An example on how to use it is part of the sample code accompanying the HIDRemote class download and the HIDRemote guide.

- 32- and 64-Bit compatible
Can be used by 32- and 64-Bit applications. Compatible with the new Snow Leopard 32 and 64-Bit kernels.