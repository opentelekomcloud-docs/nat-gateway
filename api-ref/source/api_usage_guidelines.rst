:original_name: nat_api_0047.html

.. _nat_api_0047:

API Usage Guidelines
====================

Public cloud Application Programming Interfaces (APIs) comply with the RESTful API design principles. REST-based web services are organized into resources. Each resource is identified by one or more Uniform Resource Identifiers (URIs). An application accesses a resource based on the resource's Uniform Resource Locator (URL). A URL is usually in the following format: *https://Endpoint/uri*. In the URL, **uri** indicates the resource path, that is, the API access path.

Public cloud APIs use HTTPS as the transmission protocol. Requests/Responses are transmitted by using JSON messages, with media type represented by **Application/json**.

For details about how to use APIs, see `API Usage Guidelines <https://docs.otc.t-systems.com/en-us/api/apiug/apig-en-api-180328001.html?tag=API%20Documents>`__.

Welcome to *NAT Gateway API Reference*. Public NAT gateways provide the network address translation (NAT) function for servers, such as Elastic Cloud Servers (ECSs) in a Virtual Private Cloud (VPC) or for servers in on-premises data centers that connect to a VPC through Direct Connect or Virtual Private Network (VPN). It allows these servers to access the Internet using Elastic IP (EIP) or to provide services for the Internet. Private NAT gateways provide private IP address translation services for servers, such as Elastic Cloud Servers (ECSs) in a Virtual Private Cloud (VPC) or for servers in on-premises data centers that connect to a VPC through Direct Connect or Virtual Private Network (VPN). Private NAT gateways help avoid private IP address conflicts.

This document describes how to use application programming interfaces (APIs) to perform operations on NAT gateways, such as creating or deleting NAT gateways, or adding SNAT rules. For details about all supported operations, see :ref:`API Overview <nat_api_0052>`.
