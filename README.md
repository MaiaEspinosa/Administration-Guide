# **DSI Administrator Guide**

### Introduction
* Platform overview
* pre-installation
* Installation & configuration
* Platform validation
* Administrations duties
* Platform and performance troubleshooting

### Prerequisite Knowledge
* TCPIP networking
* Database and SQL operations
* Logic processing
* Enterprise back office systems and ERPs

## **Platform overview**

The Platform is a comprehensive enterprise mobility solution comprised of a mobile application development platform and an integrated middleware server.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/8f0c4cfe1ff362f3ad8bb25677454e8dbf8d5fa1/platover.png">

## **Mobile Applications Development Platform**

With its flexible integrated development environment, or IDE, the DSI Platform allows you to develop high impact, database-driven application that can run on a variety of mobile devices.

The applications can be built to operate in multiple modes, On-Network within the four walls of a warehouse or distribution center, or Off-Network, as standalone database-driven mobile applications outside the four walls, in the field.

With these applications, workers can connect to the server to bring down a set of business data to their mobile devices, work with this data, and then reconnect to the server to synchronize data.

The system tracks changes from host data to Platform data repository and finally to individual device databases. Smart replication tracks only relevant records to eliminate unnecessary traffic.

## **On-Network applications**

On-Network applications are designed to operate while the device is in a connected state, meaning it uses data form the enterprise or back office data souces. these are primarily used in manufacturing and distribution environments where network connectivity is not an issue.

## **Off-Network Applications**

Off-Network applications are design to operate while the device is not in a connected state.
these applications use data that is replicated locally to the device via DSI _Platform Replication_. Off-Network applications are primarily used in field environments, for example, proof of delivery or field inventory.

## **Integrated middleware server**

We consider the DSI _Application Server_ the information bridge between mobile devices and enterprise or back office systems. It streamlines common business processes by allowing end users to complete transactions at the point of activity. The system contains components that operate at all three layers of the client server computing model.

DSI builds and maintains integration interfaces that are installed in the back office or ERP system. The _Application Server_ acts as the traffic cop between the mobile client device and the back off system. Finally, DSI builds and maintains a mobile client application that turns on a variety of mobile devices and servers as a container for executing application logic built within in DSI _Application Studio_.

The heart of the DSI Platform is the DSI _Application Server_ which serves two purposes:

* Primarily, to act as a server to the mobile devices, also known as _Mobile Client™_ devices. There are two primary client types supported, _Full Client (Device Mobile Client™)_. Support for HTML5 will be available in a future release.

* Secondarily, the _Application Server_ acts as a client to the ERP or back office system to the Platform is interfacing whit. Information is collected by the mobile device(_Mobile Client™_) and is sent directly to the DSI _Application Server_. This is known as a device request. The DSI _Application Server_ interprets the device request, logs it, formats it and passes it to the ERP or back office system for processing.

## **User Interfaces**

The DSI Platform main user interface in web-based and better known as the DSI _Platform Manager_. User interaction is conducted through a supported web browser and no deployment of software is required for Platform administration and development.

Mobile device and users, on the other hand, utilize the DSI _Mobile Client™_ as the user interface. There are many types of _Mobile Client™_ including _Mobile Client™_ PC, iOS, Android, _Device Mobile Client™_, _Mobile Client™ Web_ and the use of a Telnet emulator to access _Mobile Client™_ via Telnet. Windows Phone and HTML5 will be available in a future.

## **Architecture**

### Element of the architecture:
* The first element is the **_Enterprise Tier_**.  This is the place in the enterprise where the ERP or back office systems and other databases reside.

* The second element is the **_Middleware Tier_**.  This is where the primary elements of the DSI Platform reside. The Platform components at the Middleware Tier are the heart and soul of the solution.

* The **_Device Tier_** is the third element of the architecture.  This tier includes any device that requires access to a business process or operational transaction.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/howitworksarchitecture.png">

### **Enterprise Tier**

Is the place in the enterprise where the ERP or back office system and other databases reside. The Platform includes components for access to industry standard database platforms.  In addition, DSI maintains standard interfaces to a large combination of back office systems, including those from _Oracle_ (JDE EnterpriseOne, JDE World, EBS), _SAP_, _Lawson_ (Movex, M3), and _Infor_ (BPCS).

Supported databases include _Oracle_, _Microsoft SQL_, _DB2_ and other _OLE_ compliant databases.

Additionally, the DSI Platform supports standard _SOAP_ and Rest Web Services integration.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/enterpricetier.png">

### **Middleware Tier**

This is where the primary elements of the Platform reside.   
The Platform allows for development and deployment of business processes and operational transactions on a mobile device.  The Platform components at the Middleware Tier are the heart and soul of the solution. The Platform provides access to the Enterprise Tier when needed and also manages device connectivity requests from the Device Tier.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/middlewaretier.png">

### **Device Tier**

This tier includes any device that requires access to a business process or operational transaction. Devices include smartphones running _iOS_, _Android_ or _Windows Phone_ as well as tablet. Additionally, ruggedized handheld or truck mounted computers are also supported.  Devices could include voice or _RFID_ technology.  Label printers could also be included.

These devices are typically deployed within the four walls of an organization’s operations and are normally connected to the enterprise network via hard wired or wireless infrastructure. These could be accessing the enterprise network from anywhere with WWAN (cellular data) connectivity.

It should be noted that devices are able to run Off-Network applications without an active connection. Applications can be specifically designed to run in an Off-Network state.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/devicetier.png">
