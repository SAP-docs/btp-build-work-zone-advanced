<!-- loio3d644a1463ba4db7bc7a40b559f3cac1 -->

# Transporting Content via SAP Cloud Transport Management Service

An administrator can use the SAP Cloud Transport Management service to transport content from one system to another. This includes transporting content between landscapes, such as from DEV to TEST, or between data centers.



## Overview

When transporting content, there is a source system and a target system. To use SAP Cloud Transport Management, you need to subscribe to it from the source system.

In SAP Cloud Transport Management, under *Transport Nodes*, you need to configure a source node and a target node, and then you configure a *Transport Route* between the source node and the target node.

The source system communicates with SAP Cloud Transport Management using a dedicated destination that points to this service.

SAP Cloud Transport Management communicates with the target system using another destination that points to the target system.

After integrating SAP Cloud Transport Management, you can transport selected content items.

**Related Information**  


[Integrate SAP Cloud Transport Management Service](integrate-sap-cloud-transport-management-service-37bd3f5.md "The steps required to integrate the SAP Cloud Transport Management service so that it can be used to transport content between subaccounts, which may even reside on different environments or data centers.")

[Transport Selected Content](transport-selected-content-e809cb3.md "Administrators can select in the Content Manager specific content items to transport via the SAP Cloud Transport Management service.")

[Transporting Content](transporting-content-ac16eca.md "Administrators can transport content between different environments and different services. You can also transport certain site content items between subaccounts and data centers.")

