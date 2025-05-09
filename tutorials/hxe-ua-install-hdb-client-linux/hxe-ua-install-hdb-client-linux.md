---
parser: v2
author_name: John Currie
author_profile: https://github.com/JCurrie27
primary_tag: products>sap-hana\,-express-edition
tags: [ tutorial>beginner, products>sap-hana\,-express-edition ]
time: 10
---

# Installing SAP HANA HDB Client (Linux)
<!-- description --> Install the client package if you intend to develop XS applications on a machine that will not have a local SAP HANA 2.0, express edition installation.

<!-- loio14767ea1c8174336aa72126a82d8551b -->

## Prerequisites
 - **Tutorials:** You have completed [Start SAP HANA, express edition Server (VM installations)](https://developers.sap.com/tutorials/hxe-ua-getting-started-vm.html) or [Test the Installation (Native Linux installations)](https://developers.sap.com/tutorials/hxe-ua-test-binary.html)

## You will learn
How to install the SAP HANA client on a Linux machine, using either a graphical user interface or a command line.

---

## Intro
The `server machine` in these instructions refers to the laptop on which SAP HANA 2.0, express edition is installed, while `client machine` refers to your local machine. You do not need to install the two on the same machine or VM.

The clients let you access SAP HANA 2.0, express edition, from your client machine. This is the Reduced SAP Client package.

The clients included with the SAP HANA HDB client software package are:

-   JDBC

-   ODBC

-   SQLDBC

-   `ODBO/MDX`

-   Python (`PyDBAPI`)

-   `ADO.NET`


To install the SAP HANA HDB client on a Windows machine, use either a graphical user interface or a command line.

### Download the client package


Install the Download Manager to your client machine and download the client package.

1.  Save the Download Manager installation files to your client machine and open it. For instructions on downloading and running the Download Manager, see either the [Installing SAP HANA 2.0, express edition (Binary Installer Method)](https://developers.sap.com/tutorials/hxe-ua-installing-binary.html) or [Installing SAP HANA 2.0, express edition (Virtual Machine Method)](https://developers.sap.com/tutorials/hxe-ua-installing-vm-image.html) tutorials, or go straight to the SAP HANA, express edition [registration page](https://www.sap.com/products/technology-platform/hana/express-trial.html).

2.  In Download Manager, in the `Image` menu, select either `Virtual Machine` or `Binary Installer`.

3.  Click `Browse` and select a directory where your client package will be saved.

4.  Select the `Clients (Linux X86/64)` package. Clear the Select boxes of all other packages.

5.  Click `Download`. The `clients_linux_x86_64.tgz` file downloads to your save directory.

6.  Extract the compressed clients file:

    Navigate to the directory in which you wish to extract the client files and use the `tar` command:

    ```bash
    cd <preferred_filepath>
    sudo tar <download_filepath>/clients_linux_x86_64.tgz
    ```

    This extracts the following files and their contents:

    -   `hana_ml- <version>.tar.gz`

    -   `hana.ml.r- <version>.tar.gz`

    -   `hdb_client_linux_x86_64.tgz`

    -   `xs.onpremise.runtime.client_linuxx86_64.zip`



### Install the SAP HANA HDB client


To install the SAP HANA client on a Linux machine, do the following:

1.  Go to the directory where you wish to unpack the `hdb_client_linux_x86_64.tgz` files:

    ```bash
    cd <your_destination>
    ```

2.  Unpack the file:

    ```bash
    sudo tar -xvzf <unzipped_filepath>/hdb_client_linux_x86_64.tgz
    ```

    The directory `HDB_CLIENT_LINUX_X86_64` is created.

3.  Navigate to the `HDB_CLIENT_LINUX_X86_64` directory and run `hdbinst` to start the installer:

    ```bash
    cd HDB_CLIENT_LINUX_X86_64
    sudo ./hdbinst
    ```

    Follow the instructions on the screen to install the SAP HANA client.



### Log the installation


The system automatically logs the SAP HANA HDB client installation. The log files are stored at `/var/temp/hdb_client_<time_stamp>` for Linux.


### Connect to SAP HANA, express edition


Connect to a SAP HANA 2.0, express edition system using either JDBC or Python:

[Use Clients to Query an SAP HANA Database](https://developers.sap.com/mission.hana-cloud-clients.html)



### Uninstall the SAP HANA HDB client


Each installation has its own uninstallation tool. Use the `hdbuninst` command to uninstall the client software from your command prompt.

```bash
sudo <unzipped_filepath>/HDB_CLIENT_<version>/hdbuninst
```

Follow the instructions on the screen to uninstall the SAP HANA HDB client.

