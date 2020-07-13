# kubeadm infra - GCP

This setup provisions Google Compute Instances that can be used to create [Highly Available clusters with kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/high-availability/).

This setup is not meant to be used in production.

## Requirements

* [Pulumi](https://www.pulumi.com/docs/get-started/install/)
* a GCP account

## Usage

Set the required configuration parameters:

```shell
pulumi config set gcp:project <GCP_PROJECT_ID>
pulumi config set gcp:region <REGION>
pulumi config set gcp:zone <ZONE>
pulumi config set sshPublicKey <SSH PUBLIC KEY>
pulumi config set sshUsername <SSH USERNAME>
pulumi config set prefix <PREFIX TO BE USED FOR ALL RESOURCE NAMES>
```

There are some other optional configurations, see [config.ts](./config.ts) for further details and set them with a similar command as above if needed.

Then provision the infrastructure with Pulumi:

```shell
pulumi up
```