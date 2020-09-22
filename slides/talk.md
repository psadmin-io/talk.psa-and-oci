class: center, middle, white
# Enhanced Security

???

* **Compartments and Tags**
    * https://docs.cloud.oracle.com/en-us/iaas/Content/Identity/Tasks/managingcompartments.htm
    * https://docs.cloud.oracle.com/en-us/iaas/Content/Tagging/Concepts/taggingoverview.htm
* **SL vs. SG**
    * https://k21academy.com/1z0-932/network-security-groups-vs-security-list-and-when-to-use-what/
    * A Security list lets you define a set of security rules that applies to all the VNICs in a subnet whereas Network Security Groups let you define a set of security rules that applies to a group of VNICs of your choice.
    * NSGs’ security rules apply only to the resources in that NSG. By contrast, Security Lists’ rules apply to all the resources in a subnet that uses the list.
* **Instance Principles**
    * https://docs.cloud.oracle.com/en-us/iaas/Content/Identity/Tasks/callingservicesfrominstances.htm
    * Any user who has access to the instance automatically inherits the privileges granted to the instance.
    * Use dynamic groups to assign instances to group, then policy to the group for access
* **Demo**: Secrets from the Vault 
    * Show Vault from the Console
    * From Cloud Shell (psaoci)

    ```bash
    $ ssh -i ~/.ssh/cmtrial opc@
    
    $ oci secrets secret-bundle get --secret-id ocid1.vaultsecret.oc1.iad.amaaaaaaha7drbiar2tqbwvtd24h2m7b2aht3oysnp5h543ws5vnqxr5viwq --auth instance_principal

    $ sudo ioco vault read -q --secret-id=ocid1.vaultsecret.oc1.iad.amaaaaaaha7drbiar2tqbwvtd24h2m7b2aht3oysnp5h543ws5vnqxr5viwq 
    ```

---
class: center, middle, white
# Disaster Recovery

???

* FD/AD/Regions - Show Diagrams 

---
class: center

# OCI Regions

![:img OCI World map, 100%](images/oci-region-map.png)


---
class: center

# OCI Regional Design

![:img OCI Regions, 80%](images/ociregions.png)

---
class: center, middle, white
# Disaster Recovery

???

* Move non-prod/DR to OCI first
* Data Guard
* Backups in Object Storage multi region
* DNS traffic mgmt
    * https://docs.cloud.oracle.com/en-us/iaas/Content/EdgeServices/overview.htm
* Demo: Show region in console

---
class: center, middle, white
# High Availability

???

* **OCI Load Balancer**
    * https://docs.cloud.oracle.com/en-us/iaas/Content/Balance/Concepts/balanceoverview.htm
* **Instance Pool**
    * https://docs.cloud.oracle.com/en-us/iaas/Content/Compute/Tasks/creatinginstancepool.htm
* **FSS/Object Storage**
    * https://docs.cloud.oracle.com/en-us/iaas/Content/File/Concepts/filestorageoverview.htm
    * https://docs.cloud.oracle.com/en-us/iaas/Content/Object/Concepts/objectstorageoverview.htm
* **Demo**: File Storage delta backups
   ```bash
   cd /cm_psft_dpks/.snapshot
   suod mkdir 2020-09-22
   ```

---
class: center, middle, white
# Automation

???

* Cloud Manager
* Terraform
* Resource Manager/Stacks
* `oci-cli`
* Demo: Resource Manager Stacks/Drift Detection
