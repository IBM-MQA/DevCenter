---
layout: tutorial
title: Windows 8 Universal end-to-end demonstration
relevantTo: [windows]
weight: 4
---
## Overview
The purpose of this demonstration is to experience an end-to-end flow where an application &amp; an adapter are quickly created using the MobileFirst Operations Console, and the application is able to call a resource on the MobileFirst Server, using an MobileFirst Adapter.

#### Prerequisites:

* Configured Visual Studio 2013/5
* *Optional* Stand-alone MobileFirst Server ([download]({{site.baseurl}}/downloads))

<hr> 

### 1. Starting the MobileFirst Server

> If a remote server was already setup, skip this step.

From a **Terminal** window, navigate to the server's **scripts** folder and run the command: <code>start.bat</code>.

### 2. Creating an application

In a browser window, open the MobileFirst Operations Console by loading the URL: <code>http://your-server-host:server-port/mfpconsole</code>. If running locally, use: [http://localhost:9080/mfpconsole](http://localhost:9080/mfpconsole). The username/password are *demo/demo*.
 
1. Click on the "Create new" button next to **Applications** and select the desired *platform*, *identifier* and *version* values.

    ![Image of selecting platform, and providing an identifier and version](create-an-application.png)
 
2. Click on the **Get Starter Code** tile and select to download the Android Starter Code.

    ![Image of downloading a sample application](download-sample-application.png)

### 3. Creating an adapter

1. Click on the "Create new" button next to **Adapters** and download a sample adapter.

    ![Image of downloading an adapter sample](create-an-adapter.png)

### 4. Editing application logic

1. Open the Visual Studio project.

2. Select the solution's **App.xaml.cs** file and paste the following code snippet:

    ```csharp
    WLResourceRequest code snippet here
    ```

### 5. Running the application

1. In Visual Studio, click on the **Start Debugging** button.

    ![Image of application that successfully called a resource from the MobileFirst Server ]()