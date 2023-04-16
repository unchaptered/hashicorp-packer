https://developer.hashicorp.com/packer/tutorials/aws-get-started/aws-get-started-build-image


- Pre Requisites

```sh
aws configure
```

- Script List

```sh
packer init .
packer validate .
packer build sample.pkr.hcl
```