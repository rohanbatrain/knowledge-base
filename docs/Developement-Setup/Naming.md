# Device Naming Convention

This document outlines our device naming scheme, regardless of ownership.


## Rules 

For Personal Computer, we are using string instruments name.

For mobile devices, we are using flute instruments

For router we are using names which power all these instruments like dhun, dhwani. etc


## Desktops

### Harshdeep

| Name  | Device           | IP Address  | MAC Address       |
|-------|------------------|-------------|-------------------|
| Vina  | Harshdeep's PC   |             |                   |

## Laptops



### Rohan

| Name  | Device             | IP Address    | MAC Address       |
|-------|--------------------|---------------|-------------------|
| Sitar | MSI GF63-Thin      |               |                   |

### Harshdeep

| Name  | Device                   | IP Address    | MAC Address       |
|-------|--------------------------|---------------|-------------------|
|    Ektara   | Apple MacBook Air M2     |               |                   |

## Smartphones

### Harshdeep

| Name  | Device                   | IP Address    | MAC Address       |
|-------|--------------------------|---------------|-------------------|
|    Shankh   | Poco x3 pro    |               |                   |


### Rohan

| Name  | Device      | IP Address    | MAC Address       |
|-------|-------------|---------------|-------------------|
|   Murli    | OnePlus 8t  |               |                   |

## iPhones

### Rohan

| Name  | Device      | IP Address    | MAC Address       |
|-------|-------------|---------------|-------------------|
|   Rohan Batra's Iphone [^1]    | iPhone 6s   |               |                   |

## Routers

| Name            | Device          | IP Address    | MAC Address       |
|-----------------|-----------------|---------------|-------------------|
|       Dhun          | Airtel-Extreme       |               |                   |
|       Dhvani        | Pfsense              |               |                   |


# Proxmox

## Naming Convention

### VMs

#### Production

##### **VM Name:**
- The VM name should be formatted as "HOSTNAME".
- Example: "webserver" (where hostname is webserver).

##### **VID Range:**
- VID for production VMs should start from 200 and go up to 300.

##### **Example:**
- If the hostname is "win10", the VM name would be "win10". The VM displayed in the Proxmox dashboard is using this format "VID (HOSTNAME)".

![image](https://github.com/rohanbatrain/knowledge-base/assets/116573125/980bf30a-1f0c-4baf-bbca-ca7755ba4b3f)

#### Testing

##### **VM Name:**
- The VM name for testing purposes should also be formatted as "HOSTNAME".
- Example: "testvm" (where hostname is testvm).

##### **VID Range:**
- VID for testing VMs should start from 700 and go up to 800.

##### **Example:**
- If the hostname is "testvm", the VM name would be "testvm". The VM displayed in the Proxmox dashboard is using this format "VID (HOSTNAME)".

### Containers

#### Production

##### **Container Name:**
- The container name should be formatted as "HOSTNAME".
- Example: "webserver" (where hostname is webserver).

##### **CID Range:**
- CID for production containers should start from 200 and go up to 300.

#### **Example:**
- If the hostname is "webapp", the container name would be "webapp". The container displayed in the management console is using this format "CID (HOSTNAME)".

#### Testing

##### **Container Name:**
- The container name for testing purposes should also be formatted as "HOSTNAME".
- Example: "testcontainer" (where hostname is testcontainer).

##### **CID Range:**
- CID for test


## Naming of

### VM


| VID | Hostname       | VM Name               |
|-----|----------------|-----------------------|
|  |     |         |
|  | |    |


### Containers


| VID | Hostname       | Container Name               |
|-----|----------------|-----------------------------|
| |       |     |
|  | | |



[^1]: Iphone doesn't have a generic device name, as usual apple decided that we need to name i-devices based on usernames.As usual apple things, due to these very reasons we are just keeping apple ecosystem as minimally integrated as possible.  
