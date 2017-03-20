# **DSI Administrator Guide**

### Introduction
* Platform overview
* pre-installation
* Installation & configuration
* Platform validation
* Administrations duties
* Platform and performance troubleshooting

### Prerequisite knowledge
* TCPIP networking
* Database and SQL operations
* Logic processing
* Enterprise back office systems and ERPs

## **Platform overview**

The Platform is a comprehensive enterprise mobility solution comprised of a mobile application development platform and an integrated middleware server.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/8f0c4cfe1ff362f3ad8bb25677454e8dbf8d5fa1/platover.png">

## **Mobile applications development platform**

With its flexible integrated development environment, or IDE, the DSI Platform allows you to develop high impact, database-driven application that can run on a variety of mobile devices.

The applications can be built to operate in multiple modes, On-Network within the four walls of a warehouse or distribution center, or Off-Network, as standalone database-driven mobile applications outside the four walls, in the field.

With these applications, workers can connect to the server to bring down a set of business data to their mobile devices, work with this data, and then reconnect to the server to synchronize data.

The system tracks changes from host data to Platform data repository and finally to individual device databases. Smart replication tracks only relevant records to eliminate unnecessary traffic.

## **On-Network applications**

On-Network applications are designed to operate while the device is in a connected state, meaning it uses data form the enterprise or back office data souces. these are primarily used in manufacturing and distribution environments where network connectivity is not an issue.

## **Off-Network applications**

Off-Network applications are design to operate while the device is not in a connected state.
these applications use data that is replicated locally to the device via DSI _Platform Replication_. Off-Network applications are primarily used in field environments, for example, proof of delivery or field inventory.

## **Integrated middleware server**

We consider the DSI _Application Server_ the information bridge between mobile devices and enterprise or back office systems. It streamlines common business processes by allowing end users to complete transactions at the point of activity. The system contains components that operate at all three layers of the client server computing model.

DSI builds and maintains integration interfaces that are installed in the back office or ERP system. The _Application Server_ acts as the traffic cop between the mobile client device and the back off system. Finally, DSI builds and maintains a mobile client application that turns on a variety of mobile devices and servers as a container for executing application logic built within in DSI _Application Studio_.

The heart of the DSI Platform is the DSI _Application Server_ which serves two purposes:

* Primarily, to act as a server to the mobile devices, also known as _Mobile Client™_ devices. There are two primary client types supported, _Full Client (Device Mobile Client™)_. Support for HTML5 will be available in a future release.

* Secondarily, the _Application Server_ acts as a client to the ERP or back office system to the Platform is interfacing whit. Information is collected by the mobile device(_Mobile Client™_) and is sent directly to the DSI _Application Server_. This is known as a device request. The DSI _Application Server_ interprets the device request, logs it, formats it and passes it to the ERP or back office system for processing.

## **User interfaces**

The DSI Platform main user interface in web-based and better known as the DSI _Platform Manager_. User interaction is conducted through a supported web browser and no deployment of software is required for Platform administration and development.

Mobile device and users, on the other hand, utilize the DSI _Mobile Client™_ as the user interface. There are many types of _Mobile Client™_ including _Mobile Client™_ PC, iOS, Android, _Device Mobile Client™_, _Mobile Client™ Web_ and the use of a Telnet emulator to access _Mobile Client™_ via Telnet. Windows Phone and HTML5 will be available in a future.

## **Architecture**

### Element of the architecture:
* The first element is the **_Enterprise Tier_**.  This is the place in the enterprise where the ERP or back office systems and other databases reside.

* The second element is the **_Middleware Tier_**.  This is where the primary elements of the DSI Platform reside. The Platform components at the Middleware Tier are the heart and soul of the solution.

* The **_Device Tier_** is the third element of the architecture.  This tier includes any device that requires access to a business process or operational transaction.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/howitworksarchitecture.png">

## **Enterprise tier**

Is the place in the enterprise where the ERP or back office system and other databases reside. The Platform includes components for access to industry standard database platforms.  In addition, DSI maintains standard interfaces to a large combination of back office systems, including those from _Oracle_ (JDE EnterpriseOne, JDE World, EBS), _SAP_, _Lawson_ (Movex, M3), and _Infor_ (BPCS).

Supported databases include _Oracle_, _Microsoft SQL_, _DB2_ and other _OLE_ compliant databases.

Additionally, the DSI Platform supports standard _SOAP_ and Rest Web Services integration.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/enterpricetier.png">

## **Middleware tier**

This is where the primary elements of the Platform reside.   
The Platform allows for development and deployment of business processes and operational transactions on a mobile device.  The Platform components at the Middleware Tier are the heart and soul of the solution. The Platform provides access to the Enterprise Tier when needed and also manages device connectivity requests from the Device Tier.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/middlewaretier.png">

## **Device tier**

This tier includes any device that requires access to a business process or operational transaction. Devices include smartphones running _iOS_, _Android_ or _Windows Phone_ as well as tablet. Additionally, ruggedized handheld or truck mounted computers are also supported.  Devices could include voice or _RFID_ technology.  Label printers could also be included.

These devices are typically deployed within the four walls of an organization’s operations and are normally connected to the enterprise network via hard wired or wireless infrastructure. These could be accessing the enterprise network from anywhere with WWAN (cellular data) connectivity.

It should be noted that devices are able to run Off-Network applications without an active connection. Applications can be specifically designed to run in an Off-Network state.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/devicetier.png">

## **Tier overview**

Let’s peel back the covers on the Application Server and take a look at the components that make up the DSI Platform architecture.   

This is the enterprise connectivity component that allows the Platform to communicate with the back office systems.

This is DSI Application Server, which is at the core of the Platform.  The Application Server is a Windows-based system that runs on a Microsoft Server operating system.

These are the device Mobile Clients that run applications developed in the DSI Application Studio. They provide end users with the interface necessary to interact with back office systems.

Additionally, there are ancillary components that are used in specific situations for supporting functionality of the solution such as label printing, asynchronous transaction processing and data replication.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/tieroverview.png">

## **Enterprise tier details**

The enterprise tier contains standard back office integrations optimized for mobile environments. DSI builds and maintains these integrations for a variety of ERP systems and across various versions. 

The DSI Platform supports integration with industry standard OLE compliant databases. 

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/enterprisetiredetails.png">

## **Middleware tier details**

The DSI Application Server consists of several components.  Let’s review these major components.

First, is the Manager Service which is responsible for all system functions including management of the local data store, agent control and monitoring, scheduling, license checking, sever-to-server communication and system event logging.

The Manager Service is a required service. If this service is not running, devices will not connect and administrators will not be able to access the Platform Manager. 

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/middlewaretier.1.png">

The DSI Platform requires information in order for it to operate. This information includes licensing, user, configuration, security and application data. This data is stored in a non-database storage system in the form of encrypted XML files. Only the Manager Service has access to read and write to this local data store.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/middlewaretier.2.png">

Agents perform specific system functions and run as separate processes. They can be scheduled but are controlled by the Manager Service. 

The Communication Agent is responsible for mobile client communication, server-to-server communication and application server to back office systems communication. 

The Asynchronous Function Agent is responsible for processing asynchronous API requests. 

The Log Maintenance Agent is responsible for maintaining the Platform’s logging system.

Data Replication Agent is responsible for replicating data from back office systems to the middle tier database. 

Backup Agent is responsible for backing up critical system information.

Licensing Agent is responsible for updating Platform licensing. 

Printing Agent is responsible for processing Label print requests. 

The Platform has flexibility for additional, future Agent functionality.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/middlewaretier.3.png">

The Platform Manager is the primary user interface for administration, configuration and application development. The Platform Manager is hosted by a Microsoft IIS instance installed on the Application Server’s host operating system. It is built using standard web platform development tools including ASP .NET, AJAX, JavaScript and HTML5.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/middlewaretier.4.png">

### **Device tier details**

There are two Mobile Client types, Full Mobile Client and Thin Mobile Client. 

The Full Mobile Client is installed directly on the mobile device. It leverages device native features. It is a .NET application, built for specific platforms including Android, iOS, Windows and Windows Phone, with HTML5 coming in a future release. 

It is required for applications that are designed to work in an Off-Network state. 

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/devicetierdetails.PNG">

The Thin Mobile client uses a compatible web browser or Telnet emulator to run most Platform applications by using a session running on the Application Server. 

The Thin Mobile client only runs in an On-Network state.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/devicetierdetails_1.PNG">

### **Platform database details**

Ancillary database tables are present in the majority of Platform implementations but are not required for base functionality. 

The Transaction Log, for example, is included in most Platform implementations and is required for execution of asynchronous or queue-able API calls and transaction history reporting.

<img scr="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/devicetier.3.png">

Like the Transaction Log, Label Printing requires Label Printing database tables. These tables are used by the Label Printing agent to process label printing requests.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/devicetier.4.png">

### **Server redundancy**

Many production installations often require server redundancy. In the event that multiple DSI Application Servers are required for a single Platform installation – either to provide a redundant system or to scale to meet the transaction processing volume of a customer—they can be configured in a manner depicted here.

Under this scenario, the Manager Services uses Microsoft Message Queuing to synchronize the Local Data Store among each of the DSI Application Servers that are associated with the installation.

Agents can be configured to run only on a specific DSI Application Server, if desired.

If Communication Agent will be active on more than one DSI Application Server, software or hardware Load Balancing can be used to manage the connectivity of DSI Mobile Clients to the Application Server cluster.

<img src="https://github.com/MaiaEspinosa/Administration-Guide/blob/imagenes/serverredundancy.png">

