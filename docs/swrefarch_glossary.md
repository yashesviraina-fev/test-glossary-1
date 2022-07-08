## Application Components
* Status - <span class="status-style">INITIAL</span>
* Meaning  - This software implements the features, which are directly felt by the end user
Example : Lane centering, Lane Keep Assist, Lane Change Decision.
* Source - ZF
* Responsibility / Owner - Central Software Architecture


## Application Layer
* Status - <span class="status-style">INITIAL</span>
* Meaning  - This layer consists of deliverable features, functions which can be experienced by End users. It also includes 3rd party vendor or customer features & functions.
Examples : Lateral Support System (LSS).

* Application layer is divided into 2 parts :-
    1. Application Components
    2. Application Service Components

* Source - ZF
* Responsibility / Owner - Central Software Architecture


## Application Service Components
* Status - <span class="status-style">INITIAL</span>
* Meaning  - This software implements functions which are required to fulfill features defined in Application components. 
Example : Perception, CubiX
* Source - ZF
* Responsibility / Owner - Central Software Architecture


## Bootloader
* Status - <span class="status-style">INITIAL</span>
* Meaning  - The bootloader will initialize necessary hardware, then find the next valid application software to run. In some cases it loads that application software into memory, and then jump to start of this program to start executing it.
* Source - <a href="https://www.embedded.com/bootloaders-101-making-your-embedded-design-future-proof/">https://www.embedded.com/bootloaders-101-making-your-embedded-design-future-proof/</a>
* Responsibility / Owner - External


## BSP
* Abbreviation - board support package
* Status - <span class="status-style">INITIAL</span>
* Meaning  - This layer conains software for hardware-specific drivers and other routines that allows operating system (traditionally a real-time operating system, or RTOS) to function on a dedicated hardware environment. Third-party developers who wish to support a given RTOS must create a BSP that allows RTOS to run on their platform. In most cases, RTOS and BSP are bundled together by the hardware vendor.
* Source - <a href="https://en.wikipedia.org/wiki/Board_support_package">https://en.wikipedia.org/wiki/Board_support_package</a>
* Responsibility / Owner - External


## Feature (Customer / Vehicle)
* Status - <span class="status-style">INITIAL</span>
* Meaning  -
    - This layer consists of the software which the user is able to touch or feel and is directly linked to end user expereince 
    - 1:n mapping to underlying functions expected (a feature consists of multiple SW-Functions)
    - Examples: ACC, AEB, Predictive Maintenance
* Source - ZF
* Responsibility / Owner - Operation Field [Resort - Division/Department]


## Function (System Level)
* Status - <span class="status-style">INITIAL</span>
* Meaning  -
    - This layer consists of the software which the end-user does not care about directly but is necesssary to address the feature exectution needs on architecture level
    - 1:1 mapping to underlying functions expected, 1:n mapping possible for detailed view _x000b_    (system function as one unit, but could be decomposed into multiple SW-Functions)
    - Examples: AD Gen 1.5 Trajectory Planner L4, Lane Data Interface LKA
* Source - ZF
* Responsibility / Owner - Operation Field [Resort - Division/Department]


## Function Adapter
* Status - <span class="status-style">INITIAL</span>
* Meaning  - This layer consists of the software which realizes abstract communication between Software Component and Middleware. For every software component, there exist a function adapter.
The interfaces of function adapter is described in human readable Interface Discription Langauge.
* Source - ZF
* Responsibility / Owner - Central Software Architecture


## Hardware Support Layer
* Status - <span class="status-style">INITIAL</span>
* Meaning  - This layer shall consists of the components to adapt different HW and devices specific SW.
It can automate choice of resource to run a function/feature and has configuration settings necessary to run SW on various hardware elements..
E.g. : Drivers, frame server, fan control etc
* Source - ZF
* Responsibility / Owner - Central Software Architecture


## Hypervisor
* Status - <span class="status-style">INITIAL</span>
* Meaning  - An embedded hypervisor is software that allows more than one operating system (OS) to run simultaneously on a single system on a chip (SoC). It enables system designers to consolidate diverse operating systems (OSs) and applications with different reliability, safety and security requirements on one SoC.
    - Type 1 Hypervisor runs directly on hardware
    - Type 2 Hypervisor run on Host OS
* Source - <a href="https://www.embedded.com/embedded-hypervisors/">https://www.embedded.com/embedded-hypervisors/</a>
* Responsibility / Owner - External


## IDL
* Abbreviation - Interface Discription Langauge
* Status - <span class="status-style">INITIAL</span>
* Meaning  - Interface Description Language, describes the interfaces of software component in platform independent way. It can be realsized in JSON or arxml format.
* Source - ZF
* Responsibility / Owner - Central Software Architecture


## Middleware Layer
* Status - <span class="status-style">INITIAL</span>
* Meaning  - Middleware is the infrastructure which facilitates execution of core services which will be utilized by Application layer. This enables communication and data management for Application service components
    It is stable and configrable platform abstracting the layer below.
    Middleware works as an abstraction layer that abstract the details about hardware and thus allows independent development of Application lyer.
    * Middleware layers are defined in architecture ppt, [click here](./soa_ref_arch_layers.md){ . } to view layers in ppt

* Source - ZF
* Responsibility / Owner - Central Software Architecture


## Midleware Stack
* Status - <span class="status-style">INITIAL</span>
* Meaning  - Middleware enables communication and data management for distributed features/functions.
This includes Service Manager which queries Platform abstraction for capabilities
* Source - ZF
* Responsibility / Owner - Central Software Architecture


## OS
* Abbreviation - Operating system
* Status - <span class="status-style">INITIAL</span>
* Meaning  - 
This is software system manages hardware CPU, peripheral, software resources and provide common resources to all applications. It provides mechanisms to handle concurrent access mechanism with safety.
* Source - <a href="https://en.wikipedia.org/wiki/Operating_system">https://en.wikipedia.org/wiki/Operating_system</a>
* Responsibility / Owner - External


## Service
* Status - <span class="status-style">INITIAL</span>
* Meaning  - A service is a discrete unit of functionality which can be remotely accessed and independently
    updated. It is a collection of self-contained services (system functions) that communicate with well-defined messages without any knowledge of location and implementation of each other.
    SOA is a software architecture that starts with an interface definition and builds the entire feature with predefined interfaces. Typical communication  patterns are publish-subscribe, the Remote Procedure Call (RPC) and the fire-forget method driven by feature requirement.
    SOA is a relationship of service providers and service consumers, both software components large enough to represent a complete feature/function.

    - Following is not SOA service definition :-
    Service in ROS are just synchronous remote procedure calls; they allow one node to call a function that executes in another node. A ROS service is a client/server system. It is synchronous. The client sends a requests, and blocks until it receives a response. A service is defined by a name, and a pair of messages.

* Source - ZF
* Responsibility / Owner - Central Software Architecture


## SOA
* Abbreviation - Service Oriented Architecture
* Status - <span class="status-style">INITIAL</span>
* Meaning  - Service-orientated Architecture (SoA) is a way of designing architecture where the participating components provide and consume services over a predefined protocol over a network. It is a software development model that allows services to communicate across different programs through function adapter to form feature.
    * In SOA, a service is a self-contained unit of software designed to complete a specific feature.
    allows the decoupling of services from the underlying hardware and network infrastructure implemented as individual software components(SWCs) the communication among SWCs occurs through well-defined standard interfaces
    * Service oriented architecture layers are defined in architecture ppt, [click here](./soa_ref_arch_layers.md){ . } to view layers in ppt

* Source - <a href="https://en.wikipedia.org/wiki/Service-oriented_architecture">https://en.wikipedia.org/wiki/Service-oriented_architecture</a>
* Responsibility / Owner - External


## SoC
* Abbreviation - System on chip
* Status - <span class="status-style">INITIAL</span>
* Meaning  - A system on a chip is an integrated circuit that combines many elements of a computer system into a single chip. An SoC always includes a CPU, but it may also include system memory, peripheral controllers (for USB, storage), and more advanced peripherals such as graphics processing units (GPUs), specialized neural network circuitry, radio modems (for Bluetooth or Wi-Fi), depending on the chip hardwre achitecture.
* Source - <a href="https://en.wikipedia.org/wiki/System_on_a_chip">https://en.wikipedia.org/wiki/System_on_a_chip</a>
* Responsibility / Owner - External


## Software
* Status - <span class="status-style">INITIAL</span>
* Meaning  - It is a collection of data or computer instructions that tell the computer how to work
* Source - <a href="https://en.wikipedia.org/wiki/Software">https://en.wikipedia.org/wiki/Software</a>
* Responsibility / Owner - External


## System Service Components
* Status - <span class="status-style">INITIAL</span>
* Meaning  - This component implmentes either the OEM specific infrastructure add-on components and also the abstraction for several services from base software to application service layer. Goal is to be bale to update the Application service components within very minimum integration efforts.
* Source - ZF
* Responsibility / Owner - Central Software Architecture


