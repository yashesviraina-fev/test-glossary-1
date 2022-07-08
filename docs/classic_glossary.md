## BSW 
* Abbreviation - Basic Software
* Domain - Software
* Meaning  - Standardized software modules (mostly) with no explicit automotive job, but offers services needed to run the functional part of the upper software layer
* Source - <a href="https://en.wikipedia.org/wiki/AUTOSAR">https://en.wikipedia.org/wiki/AUTOSAR</a>
* Status - INITIAL


## RTE 
* Abbreviation - Runtime Environment
* Domain - Software
* Meaning  - Middleware which abstracts from the network topology for the inter- and intra-ECU information exchange between the application software components and between the Basic Software and the applications
* Source - <a href="https://en.wikipedia.org/wiki/AUTOSAR">https://en.wikipedia.org/wiki/AUTOSAR</a>
* Status - INITIAL


## ASW
* Abbreviation - Application Software
* Domain - Software
* Meaning  - Application software components that interact with the runtime environment
* Source - <a href="https://en.wikipedia.org/wiki/AUTOSAR">https://en.wikipedia.org/wiki/AUTOSAR</a>
* Status - INITIAL


## Methodology
* Domain - Software
* Meaning  - System Configuration Description includes all system information and the information agreed between different ECUs (e.g. definition of bus signals).
ECU extract: contains the information from the System Configuration Description needed for a specific ECU (e.g. those signals where a specific ECU has access to).
ECU Configuration Description: contains all basic software configuration information that is local to a specific ECU. Use this information to build the executable software, the code of the basic software modules and the code of the software components out of i
* Source - <a href="https://en.wikipedia.org/wiki/AUTOSAR">https://en.wikipedia.org/wiki/AUTOSAR</a>
* Status - INITIAL


## Microcontroller Abstraction Layer
* Abbreviation - MCAL
* Domain - Software
* Meaning  - The Microcontroller Abstraction Layer is the lowest software layer of the Basic Software. It contains internal drivers, which are software modules with direct access to the μC and internal peripherals.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## ECU Abstraction Layer
* Domain - Software
* Meaning  - The ECU Abstraction Layer interfaces the drivers of the Microcontroller Abstraction Layer. It also contains drivers for external devices.
It offers an API for access to peripherals and devices regardless of their location (μC internal/external) and their connection to the μC (port pins, type of interface)
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Complex Drivers Layer
* Abbreviation - CDD
* Domain - Software
* Meaning  - Provide the possibility to integrate special purpose functionality, e.g. drivers for devices:
- which are not specified within AUTOSAR,
- with very high timing constraints or
- for migration purposes etc.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Services Layer
* Domain - Software
* Meaning  - The Services Layer is the highest layer of the Basic Software which also applies for its relevance for the application software: while access to I/O signals is covered by the ECU Abstraction Layer, the Services Layer offers:
- Operating system functionality
- Vehicle network communication and management services
- Memory services (NVRAM management)
- Diagnostic Services (including UDS communication, error memory and fault treatment)
- ECU state management, mode management
- Logical and temporal program flow monitoring (Wdg manager)
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Handler
* Domain - Software
* Meaning  - A handler is a specific interface which controls the concurrent, multiple and asynchronous access of one or multiple clients to one or more drivers. I.e. it performs buffering, queuing, arbitration, multiplexing.
The handler does not change the content of the data.
Handler functionality is often incorporated in the driver or interface (e.g. SPIHandlerDriver, ADC Driver).
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Manager
* Domain - Software
* Meaning  - A manager offers specific services for multiple clients. It is needed in all cases where pure handler functionality is not enough to abstract from multiple clients.
Besides handler functionality, a manager can evaluate and change or adapt the content of the data.
In general, managers are located in the Services Layer
Example: The NVRAM manager manages the concurrent access to internal and/or external memory devices like flash and EEPROM memory. It also performs distributed and reliable data storage, data checking, provision of default values etc.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Libraries
* Domain - Software
* Meaning  - Libraries are a collection of functions for related purposes
Libraries:
- can be called by BSW modules (that including the RTE), SW-Cs, libraries or integration code
- run in the context of the caller in the same protection environment
- can only call libraries
- are re-entrant
- do not have internal states
- do not require any initialization
- are synchronous, i.e. they do not have wait points
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## IOC
* Abbreviation - Inter OsApplication Communicator 
* Domain - Software
* Meaning  - The IOC provides communication services which can be accessed by clients which need to communicate across OS-Application boundaries on the same ECU. The IOC is part of the OS.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## AUTOSAR Interface
* Domain - Software
* Meaning  - An "AUTOSAR Interface" defines the information exchanged between software components and/or BSW modules. This description is independent of a specific programming language, ECU or network technology. AUTOSAR Interfaces are used in defining the ports of software-components and/or BSW modules. Through these ports software-components and/or BSW modules can communicate with each other (send or receive information or invoke services). AUTOSAR makes it possible to implement this communication between Software-Components and/or BSW modules either locally or via a network.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Standardized AUTOSAR Interface
* Domain - Software
* Meaning  - A "Standardized AUTOSAR Interface" is an "AUTOSAR Interface" whose syntax and semantics are standardized in AUTOSAR. The "Standardized AUTOSAR Interfaces" are typically used to define AUTOSAR Services, which are standardized services provided by the AUTOSAR Basic Software to the application Software-Components.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Standardized Interface
* Domain - Software
* Meaning  - A "Standardized Interface" is an API which is standardized within AUTOSAR without using the "AUTOSAR Interface" technique. These "Standardized Interfaces" are typically defined for a specific programming language (like "C"). Because of this, "standardized interfaces" are typically used between software-modules which are always on the same ECU. When software modules communicate through a "standardized interface", it is NOT possible any more to route the communication between the software-modules through a network.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## SDU
* Abbreviation - Service Data Unit
* Domain - Software
* Meaning  - SDU is the abbreviation of “Service Data Unit”. It is the data passed by an upper layer, with the request to transmit the data. It is as well the data which is extracted after reception by the lower layer and passed to the upper layer.
A SDU is part of a PDU.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## PDU
* Abbreviation - Protocol Data Unit
* Domain - Software
* Meaning  - PDU is the abbreviation of “Protocol Data Unit”. The PDU contains SDU and PCI.
On the transmission side the PDU is passed from the upper layer to the lower layer, which interprets this PDU as its SDU.
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


## Pre-compile time
* Domain - Software
* Meaning  - Preprocessor instructions
Code generation (selection or synthetization)
* Source - <a href="https://autosar.org">https://autosar.org</a>
* Status - INITIAL


