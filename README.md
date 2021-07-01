## Deploy OpenShift Clusters to vSphere using vRealize Automation
vRA Code Stream Pipeline to deploy OpenShift clusters and register with Tanzu Mission Control. 

### Getting started 
> Blog Post - [Deploying OpenShift Clusters using vRA Code Stream](https://bit.ly/2SEG0Z5)

### Pre-reqs

 * Red Hat Cloud Account
   * With the ability to download and use a Pull Secret for creating OpenShift Clusters
 * vRA access to create Code Stream Pipelines and associated objects inside the pipeline when it runs.
   * Get CSP API access token for vRA Cloud or on-premises edition.
* Tanzu Mission Control access with ability to attach new clusters
  * Get an CSP API access token for TMC
* vRA Code Stream configured with an available Docker Host that can connect to the network you will deploy the OpenShift clusters to.
  * This [Docker container](https://hub.docker.com/r/saintdle/openshift-ci) is used for the pipeline
  * You can find the [Dockerfile here](https://github.com/saintdle/openshift-ci), and alter per your needs, including which versions of OpenShift you want to deploy.
 * SSH Key for a bastion host access to your OpenShift nodes.
 * vCenter account with [appropriate permissions](https://docs.openshift.com/container-platform/4.7/installing/installing_vsphere/installing-vsphere-installer-provisioned.html#installation-vsphere-installer-infra-requirements_installing-vsphere-installer-provisioned) to deploy OpenShift
   * You can use this [PowerCLI script](https://github.com/saintdle/PowerCLI/blob/master/Create%20vCenter%20Roles/Create_vCenter_OpenShift_Install_Role.ps1) to create the role permissions.
 * [DNS records](https://docs.openshift.com/container-platform/4.7/installing/installing_vsphere/installing-vsphere-installer-provisioned.html#installation-vsphere-installer-infra-requirements_installing-vsphere-installer-provisioned) created for the OpenShift cluster deployment
   * api.{cluster_id}.{base_domain}
   * *.apps.{cluster_id}.{base_domain}

### Screenshots
![vRA Deploy Openshift - Code Stream - Create Variable](https://i2.wp.com/veducate.co.uk/wp-content/uploads/2021/06/vRA-Deploy-Openshift-Code-Stream-Import-Pipeline.jpg)
![vRA Deploy Openshift - Code Stream - Preserved Artifacts](https://i1.wp.com/veducate.co.uk/wp-content/uploads/2021/06/vRA-Deploy-Openshift-Code-Stream-Preserved-Artifacts.jpg)
