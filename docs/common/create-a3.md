| Instance Count | Enter the number of instances of a given type. Default is 1. |
| Ambari Server | You must select one node for Ambari Server. The "Group Size" for that host group must be set to "1". |   


6. On the **Network** page, provide the following to specify the networking resources that will be used for your cluster:

    | Parameter | Description |
|---|---|
| Select Network | Select the virtual network in which you would like your cluster to be provisioned. You can select an existing network or create a new network. |
| Select Subnet | Select the subnet in which you would like your cluster to be provisioned. If you are using a new network, create a new subnet. If you are using an existing network, select an existing subnet. |
| Subnet (CIDR)| If you selected to create a new subnet, you must define a valid [CIDR](http://www.ipaddressguide.com/cidr) for the subnet. Default is 10.0.0.0/16. |

7. Next, define security groups for each host group. For each host group, you can either create a new security group and define its rules or use an existing secuirty group:

    | Option | Description |
|---|---|
| New Security Group | <p>(Default) Creates a new security group with the rules that you defined:</p><p><ul><li>A set of [default rules](security.md#default-cluster-security-groups) is provided. You should review and adjust these default rules. If you do not make any modifications, default rules will be applied. </li><li>You may open ports by defining the CIDR, entering port range, selecting protocol and clicking **+**.</li><li>You may delete default or previously added rules using the delete icon.</li><li>If you don't want to use security group, remove the default rules.</li><ul></p> |  
| Existing Security Groups | Allows you to select an existing security group that is already available in the selected provider region. This selection is disabled if no existing security groups are available in your chosen region. |  

5. On the **Security** page, provide the following parameters:

    | Parameter | Description |
|---|---|
| Cluster User | You can log in to the Ambari UI using this username. By default, this is set to `admin`. |
| Password | You can log in to the Ambari UI using this password. |
| Confirm Password | Confirm the password. |