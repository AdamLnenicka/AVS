Zde je detailnější dokumentace vytvořená z vašich poznámek:

---

## Deployment of Devices

### Servers:
- **Jupiter10**
- **Jupiter21**

### iLO Access:
- **Server:** Jupiter21
- **iLO URL:** [jupiter21-ilo.mendelu.cz](http://jupiter21-ilo.mendelu.cz)
- **iLO IP:** 10.26.55.121

### Management Network:
- **MAC Address:** 5C:BA:2C:57:F6:54
- **IP Address:** 10.26.56.121/24
- **Gateway:** .1
- **DNS:** 195.178.72.150

### Storage Area Network (SAN):
- **MAC Address:** 5C:BA:2C:57:F6:55
- **IP Address:** 10.26.57.121/24

### Virtual Machines (VM):
- **MAC Address:** 9C:DC:71:BF:C0:84
- **DNS:** 195.178.72.150
- **VLAN 1558:**
  - **IP Address:** 10.26.58.121/24 a .221
  - **Gateway:** .1
- **VLAN 1559:**
  - **IP Address:** 10.26.59.121/24 a .221
  - **Gateway:** .1

### Migration Network:
- **MAC Address:** 9C:DC:71:BF:C0:85
- **IP Address:** 10.26.60.121/24

## Deployment Steps

1. **Accessing iLO Server and Starting Console:**
   - Connect to the iLO server and initiate console access.

2. **Installing VMware ESXi 8.0.2:**
   - Install VMware ESXi 8.0.2 from a local ISO file.

3. **Configuring Network Management:**
   - Set up static IPv4 addressing, subnet masks, and gateways.
   - Assign hostnames according to the provided addresses.

4. **Accessing ESXi Host Client:**
   - Log in to the ESXi Host Client using credentials created during installation.

5. **Networking Configuration:**
   - Create a virtual switch for the SAN network.
   - Establish a SAN port group and include it in the SAN switch.
   - Allocate SAN addresses according to the provided scheme.
   - Create a TRUNK switch and configure port groups for VLAN 1558 and VLAN 1559.
   - Set up a Migration switch and port group, assigning addresses accordingly.

6. **Virtual Machines Setup:**
   - Create a new virtual machine with the following specifications:
     - OS: Red Hat Enterprise Linux 9
     - CPUs: 4 sockets, 2 cores per socket
     - RAM: 8GB
     - HDD: 200GB
   - Assign the VM to VLAN 1558.
   - Power on the VM.

## Conclusion

This documentation outlines the detailed steps undertaken during the deployment of devices and network configuration for virtualization. Each step contributes to the setup and management of virtual machines and associated networks in the environment.