---
parser: v2
auto_validation: true
time: 20
tags: [ tutorial>beginner, products>sap-fiori-elements, products>sap-business-technology-platform, products>sap-btp--abap-environment]
primary_tag: products>sap-fiori
contributors: [ Dimitri Herber>https://github.com/fakirdi, Hitesh Parmar>https://github.com/hitesh-parmar, Joachim Fiess>https://github.com/jo-fiess ]
---

# Prepare the RAP-Based Travel Service
<!-- description --> Prepare a travel service based on the SAP ABAP RESTful Application Programming Model (RAP).

## Prerequisites
 - You need a trial account for the SAP Business Technology Platform. Follow these instructions in case you need to set up an account: [Get a Free Account on SAP BTP Trial](hcp-create-trial-account).
 - Prepare your SAP Business Technology Platform ABAP Environment: [Create an SAP BTP ABAP Environment Trial User](abap-environment-trial-onboarding) -- be sure to also check the prerequisites of this linked tutorial which include the installation of the ABAP Development Tools.



## You will learn
  - How to generate a RAP service as a preparation for this tutorial
  - How to publish and test the RAP service using the preview option of the ABAP Development Tools

## Intro
This tutorial shows how to create an individual RAP-based OData service, which can be used within all the steps of the upcoming chapters of the tutorials presented within the tutorial group.

For more information about the ABAP RESTful Application Programming Model (RAP), especially related to the different CDS view files used in the upcoming chapters, please refer to the documentation pages of [Get to Know the ABAP RESTful Application Programming Model](abap-environment-restful-programming-model).

---

### Start the service generator


This tutorial requires an individual OData service having a unique suffix for each participant. This is necessary due to the fact that, within a specific ABAP cloud back-end system, all the development objects (e.g. packages, data-elements, classes, etc.) are globally available for all trial users who are connected to the same system. Since the creation of such an OData service is not the main part of these tutorials, a service generator is used to quickly create an individual service.

>Whenever your unique suffix for creating objects is needed, the object names within this tutorial are named with suffix "######". For the screenshots taken from a real service, the suffix "000100" was used.

1. Load the ABAP generator class

    Be sure to have opened the ABAP perspective within the ABAP Development Tools. In case you don´t see the ABAP perspective icon at the top right of the application (see screenshot below), open the ABAP perspective by **Window** > **Perspective** > **Open Perspective** > **Other...** and choose the ABAP entry within the list of perspectives. Click **Open** to confirm the dialog.

    ![Load generator class](PrepareService_0.png)

    Now choose the toolbar action **Open ABAP Development Object** to open the ABAP class that is needed to generate the service.

    ![Load generator class](PrepareService_1.png)

    The name of the class is **``zdmo_cl_fe_travel_generator`**. Select the class and confirm the dialog by choosing **OK**.

    ![Load generator class](PrepareService_2.png)


2. Start the generator class

    As soon as the class is loaded within the editor, open the context menu via right mouse click and start the service by choosing **Run As** > **ABAP Application (Console)**.

    ![Load generator class](PrepareService_3.png)

    The generation of the service may take some time. After the process has finished you will see a console message similar to the message shown in the screenshot below.

    ![Load generator class](PrepareService_4.png)

3. Assign the new package to your favorite packages

    To keep a better overview of your packages, add them by right clicking on the **Favorite Packages** container and choosing the **Add Package...** option.

    ![Load generator class](PrepareService_5.png)

    Enter the name of your package **`ZFE_TRAVEL_######`** shown in the console message in the dialog and confirm by choosing **OK**.

    ![Load generator class](PrepareService_6.png)

    Now you see the package assigned to your favorite packages.

    ![Load generator class](PrepareService_6a.png)




### Publish the service (Optional)

**You can skip this step since the service has been published automatically. This step is included only to demonstrate how the service can be published.**

You must publish the service to be able to use it within your applications. To do so, open the service binding file `ZUI_FE_TRAVEL_######_O4` in the **Business Services** > **Service Bindings** folder and choose **Publish**. You will see a progress bar while the process is running.

![Load generator class](PrepareService_7.png)

### Preview the service

1. Start the service preview

    Since the service is has been published automatically, its entities are shown within a tree view under **Service Version Details**.

    You can now use the service to create SAP Fiori elements applications.

    To immediately see the service running in an application you can start the preview mode within the ABAP Development Tools. Simply select the main entity **Travel** in the tree view and choose **Preview...** on the right.

    ![Load generator class](PrepareService_8.png)

2. Logon to the service preview

    A separate browser window opens and you need to logon with your cloud trial account. Choose **Log On** after you have entered your credentials.

    ![Load generator class](PrepareService_9.png)

    After logging on, a generated list report object page application is shown in preview mode. Since there are no line item annotations available, no columns are shown in the list report table.

    ![Load generator class](PrepareService_10.png)

    Adding annotations to enrich the service will be the main part of this tutorial - this will now be done within the upcoming steps in the next chapters.






---
