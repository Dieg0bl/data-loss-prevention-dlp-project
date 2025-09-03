<!-- hide -->
# DLP Security Policies

> By [@rosinni](https://github.com/rosinni) and [other contributors](https://github.com/breatheco-de/data-loss-prevention-dlp-project/graphs/contributors) at [4Geeks Academy](https://4geeksacademy.co/)

[![build by developers](https://img.shields.io/badge/build_by-Developers-blue)](https://4geeks.com)
[![Twitter Follow](https://img.shields.io/twitter/follow/4geeksacademy?style=social&logo=twitter)](https://twitter.com/4geeksacademy)

*These instructions are also [available in Spanish](https://github.com/breatheco-de/data-loss-prevention-dlp-project/blob/main/README.es.md)*

### Before you start...

> We need you! These exercises are created and maintained in collaboration with people like you. If you find any errors or typos, please contribute and/or report them.

<!-- endhide -->


## 📖 Project Purpose

This educational cybersecurity project focuses on the creation and implementation of **Data Loss Prevention (DLP)** security policies within an organization. Students will learn to apply the principle of least privilege and ensure that only authorized personnel have access to sensitive data through practical, hands-on exercises.

### 🎯 Learning Objectives:
- **Part 1**: Define and establish comprehensive DLP policies that help protect confidential information
- **Part 2**: Implement specific technical measures, such as **restricting USB device access**, to ensure DLP policies are effectively applied in practice

## 🛠️ Technologies Used

This project utilizes the following technologies and tools:

- **Operating System**: Windows (Virtual Machine recommended)
- **Virtualization**: VirtualBox with Extension Pack
- **Policy Management**: Windows Group Policy Editor (`gpedit.msc`)
- **Security Framework**: Data Loss Prevention (DLP) principles
- **Documentation**: PDF reports and policy documentation
- **Testing Environment**: Windows user account management
- **Storage Devices**: USB devices for restriction testing

## 🚀 Prerequisites and Installation

### System Requirements:
- Windows virtual machine (Windows 10/11 recommended)
- VirtualBox with Extension Pack installed
- Administrative privileges on the VM
- USB device for testing restrictions

### 🌱 How to Start This Project

## 📝 Instructions

### Creation of DLP Security Policies

1. **Introduction to Data Loss Prevention.** Write an introduction to DLP, explaining the general concept of DLP and its importance within an organization, highlighting its role in protecting confidential data.

2. **Data Classification.** Define how the organization will classify data based on its sensitivity. Establish at least three classification categories, for example:

    - Public Data
    - Internal Data
    - Sensitive Data

3. **Access and Control.** Apply the principle of least privilege by establishing access policies based on this principle, and define the permission review workflow, indicating which roles within the organization will be responsible for these reviews and how they will be carried out.

4. **Monitoring and Auditing.** Establish rules for monitoring sensitive data and auditing activities related to that data. Provide more detailed descriptions of the monitoring and auditing tools that will be used (e.g., SIEM solutions or specific DLP tools to monitor data usage).

5. **Leak Prevention.** Define how the leakage of sensitive data will be prevented, using technologies such as encryption and DLP tools.

6. **Education and Awareness.** Describe how staff will be trained on security policies and the associated risks.

### 📁 Example of Real Case Report

For a practical illustration, refer to the [Data Loss Prevention Case Study](assets/SecurityPolicyReport.pdf). This example focuses on the use of **Google Drive**, but it can be adapted to any cloud or local storage or collaboration system. The key is ensuring that only authorized users access the information as needed to perform their work, always respecting the **Principle of Least Privilege**.

## Implementation of USB Device Restriction Policies

The second part of this exercise involves implementing policies to restrict the use of **USB devices**. These restrictions are essential to prevent the leakage of confidential data through removable storage devices. This policy is directly linked to the DLP policies created in the first part of the exercise.

> 💡 The following practice will focus on a Windows virtual machine.

### 📋 Setup Instructions

#### Step 1: Virtual Machine Configuration
Before implementing DLP policies, ensure your virtual environment is properly configured:

> ⚠️ **Important**: To apply USB device restrictions, your VM must be able to access USB devices connected to your physical machine (host).

1. **Install VirtualBox Extension Pack**
   - Visit the [official VirtualBox website](https://www.virtualbox.org/wiki/Downloads)
   - Download the Extension Pack matching your VirtualBox version
   - Open VirtualBox → File → Tools → Extensions → Install the downloaded file

2. **Enable USB Support on VM**
   - Shutdown your virtual machine if running
   - Select the VM in VirtualBox → Settings → Ports → USB
   - Enable either `USB 2.0 (EHCI) Controller` or `USB 3.0 (xHCI) Controller`

3. **Connect USB Device to VM**
   - Start the VM and connect USB device to your physical machine
   - In VM menu: Devices → USB → Select your connected device
   - VM will take control of the USB device

#### Step 2: Access Group Policy Editor
- Press `Win + R`, type `gpedit.msc`, and press Enter
- This opens the Group Policy Editor for policy configuration

### 🔒 USB Device Restriction in Windows

#### Step 3: Configure USB Restriction Policies

1. **Navigate to Removable Storage Policies**
   - Go to: `Computer Configuration > Administrative Templates > System > Removable Storage Access`

2. **Configure USB Access Denial Policies**
   Enable the following policies to restrict USB access:
   - **Removable Disks: Deny read access** - Prevents users from reading USB devices
   - **Removable Disks: Deny write access** - Prevents users from writing to USB devices

   > ⚠️ **Result**: This will prevent users from reading or writing to connected USB devices.

3. **Apply Changes**
   - Restart the virtual machine to apply the policy changes


### 🧪 Validation and Testing of USB Restriction

1. **Test the USB Restriction.** Connect a USB device to the VM and try to access it from a standard user account (without administrative privileges).
2. **Verify Access Restriction.** If the policies are correctly configured, standard users should not be able to access the USB device, and a message should appear indicating the denial of access.

### 👤 Creation and Testing of a Regular User

1. **Create a new regular user in Windows.** Open Settings (Win + I), go to `Accounts > Family & other users`.

2. Click `Add someone else to this PC`, select `I don’t have this person’s sign-in information`, then `Add a user without a Microsoft account`.

3. Create the user with a name and password (this will be a standard user without privileges).

4. **Test the restriction with the regular user.** Log in with the new regular user and connect the USB device to verify that access is denied due to the applied restrictions.

### 🔧 Enabling Exceptions for Specific Users

We assume that by this point you are a confident student, so we ask you to research how to enable exceptions for specific users. The idea is that you log in with an administrator account, open the `Group Policy Editor`, and investigate how to enable exceptions in the USB device policies for certain users or groups of users.

Finally, you should verify that the exceptions have been applied by conducting tests with different users.


<!-- hide -->

## Contributors

Thanks to these amazing people ([emoji key](https://github.com/kentcdodds/all-contributors#emoji-key)):

1. [Rosinni Rodriguez (rosinni)](https://github.com/rosinni) contribution: (build-tutorial) ✅, (documentation) 📖
  
2. [Alejandro Sanchez (alesanchezr)](https://github.com/alesanchezr), contribution: (bug reports) 🐛

This project follows the [all-contributors](https://github.com/kentcdodds/all-contributors) specification. Contributions of any kind are welcome!

This and other exercises are used to [learn to code](https://4geeksacademy.com/us/learn-to-code) by students at 4Geeks Academy [Coding Bootcamp](https://4geeksacademy.com/us/coding-bootcamp) led by [Alejandro Sánchez](https://twitter.com/alesanchezr) and many other contributors. Learn more about our [Programming Courses](https://4geeksacademy.com/us/programming-courses) to become a [Full Stack Developer](https://4geeksacademy.com/us/coding-bootcamps/full-stack-developer), or our [Data Science Bootcamp](https://4geeksacademy.com/us/coding-bootcamps/data-science-machine-learning-bootcamp). You can also dive into cybersecurity with our [Cybersecurity Bootcamp](https://4geeksacademy.com/us/coding-bootcamps/cybersecurity-bootcamp).

<!-- endhide -->
