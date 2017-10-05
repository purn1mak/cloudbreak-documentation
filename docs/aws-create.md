## Create a Cluster on AWS 

### Optional Prerequisites

If you are just getting started with Cloudbreak, follow the steps below to create a cluster using the default blueprints and infrastructure templates. 

If you are already familiar with Cloudbreak, review the [Blueprints](blueprints.md) and [Templates](templates-aws.md) documentation to customize your blueprints and infrastructure templates.

### Basic Options   

{!docs/common/cluster-basic-conf1.md!}
{!docs/common/cluster-basic-conf2.md!}

{!docs/common/cluster-basic-net&blue.md!}
{!docs/common/cluster-basic-review.md!}


### Advanced Options

{!docs/common/cluster-adv-1.md!}
| **Use dedicated instances** | Select this to use dedicated instances (i.e. EC2 instances that run in a virtual private cloud (VPC) on hardware that's dedicated to a single customer). For more information about dedicated instances, refer to [AWS documentation](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-instance.html). |
{!docs/common/cluster-adv-2.md!}



{!docs/common/cluster-adv-3.md!} 
| **Instance Profile** | This option allows you to optionally create or reuse an existing instance profile for your cluster VMs. An instance profile is a container for an IAM role that you can use to pass role information to an EC2 instance when the instance starts. You can use this option to allow access to AWS resources such as Amazon S3 object storage. The following choices are available:<ul><li>Disable Instance Profile attaching by default</li><li>Create Instance Profile and attach to the instance</li><li>Define existing Instance Profile and attach to the instances</li></ul> For more information about instance profile, refer to [AWS documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2_instance-profiles.html). |

{!docs/common/cluster-adv-4.md!}

<div class="next">
<a href="../aws-data/index.html">Next: Access Cloud Data</a>
</div>