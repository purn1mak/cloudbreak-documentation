## Architecture  

**Cloudbreak deployer** installs Cloudbreak components on a VM. Once these components are deployed, you can use **Cloudbreak application** or Cloudbreak CLI to create, manage, and monitor clusters. 

### Cloudbreak deployer architecture

**Cloudbreak deployer** installs Cloudbreak components on a VM. It includes the following components:

| Component | Description |
|---|---|
| **Cloudbreak Application** | Cloudbreak application is built on the foundation of cloud provider APIs and Apache Ambari. | 
| **Uluwatu** | This is Cloudbreak web UI, which can be used to create, manage, and monitor clusters. |
| **Cloudbreak CLI** | This is Cloudbreak's command line tool, which can be used to create, manage, and monitor clusters. | 
| **Identity** | This is Cloudbreak's OAuth identity server implementation, which utilizes UAA. |
| **Sultans** | This is Cloudbreak's user management system. | 
| **Periscope** | This is Cloudbreak's autoscaling application, which is responsible for automatically increasing or decreasing the capacity of the cluster when your pre-defined conditions are met. |
 

### Cloudbreak application architecture 

The Cloudbreak application is a web application which simplifies cluster provisioning in the cloud. Based on your input, Cloudbreak provisions all required cloud infrastructure and then provisions a cluster on your behalf within your cloud provider account.   

<a href="../images/cb_arch.png" target="_blank" title="click to enlarge"><img src="../images/cb_arch.png" width="550" title="Cloudbreak architecture"></a> 

Cloudbreak application is built on the foundation of cloud provider APIs and Apache Ambari:
    
* Cloudbreak uses **cloud provider APIs** to communicate with the cloud providers. 

* Cloudbreak uses the **Cloudbreak credential** to authenticate with your cloud provider account and provision cloud resources required for the clusters. 
    
* Cloudbreak uses Apache Ambari and **Ambari blueprints** to provision, manage, and monitor clusters. Ambari blueprints are a declarative definition of a cluster. With a blueprint, you can specify stack, component layout, and configurations to materialize a cluster instance via Ambari REST API, without having to use the Ambari cluster install wizard.     
  
  
### Core concepts  

Before using Cloudbreak, you should familiarize yourself with the following concepts.     


#### Cloudbreak credential

After launching Cloudbreak, you must create a Cloudbreak credential for each cloud provider on which you would like to provision clusters. Only after you have completed that step you can start creating clusters. 

Cloudbreak credential allows Cloudbreak to authenticate with the cloud provider and create resources on your behalf. The authentication process varies depending on the cloud provider, but is typically done via assigning a specific IAM role to Cloudbreak which allows Cloudbreak to perform certain actions within your cloud provider account. To learn more, refer to [Identity management](security.md#identity-management).  


<a href="../images/cb_arch-cred.png" target="_blank" title="click to enlarge"><img src="../images/cb_arch-cred.png" width="500" title="How Cb uses Cloudbreak Credential"></a> 

**Related links**  
[Identity management](security.md#identity-management)  


#### Ambari blueprints

Ambari blueprints are a declarative definition of a cluster. A blueprint allows you to specify stack, component layout, and configurations to materialize a cluster instance via Ambari REST API, without having to use the Ambari cluster install wizard.  

Ambari blueprints are specified in JSON format. After you provide the blueprint to Cloudbreak, the host groups in the JSON are mapped to a set of instances when starting the cluster, and the specified services and components are installed on the corresponding nodes.

Cloudbreak includes a few default blueprints and allows you to upload your own blueprints.

<a href="../images/cb_arch-blue.png" target="_blank" title="click to enlarge"><img src="../images/cb_arch-blue.png" width="500" title="How Cb uses Ambari blueprints"></a> 

**Related links**  
[Using custom blueprints](blueprints.md)  
[Apache documentation](https://cwiki.apache.org/confluence/display/AMBARI/Blueprints) (External)  


#### Recipes 

Cloudbreak allows you to upload custom scripts, called "recipes". A recipe is a script that runs on all nodes of a selected node group at a specific time. You can use recipes for tasks such as installing additional software or performing advanced cluster configuration. For example, you can use a recipe to put a JAR file on the Hadoop classpath.

Available recipe execution times are:  

* Before Ambari server start    
* After Ambari server start    
* After cluster installation    
* Before cluster termination   

You can upload your recipes to Cloudbreak via the UI or CLI. Then, when creating a cluster, you can optionally attach one or more "recipes" and they will be executed on a specific host group at a specified time. 

**Related links**  
[Using custom scripts (recipes)](recipes.md) 

   
