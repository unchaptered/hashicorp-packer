https://developer.hashicorp.com/packer/tutorials/aws-get-started/aws-get-started-build-image

## CLI Scripts

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

## Variables Syntax

### ✅ Input Variable Blocks

```packer
variable "ami_prefix" {
    type = string
    default = "learn-packer-linux-aws-redis"
}
```

### ✅ Local Variables Blocks

```packer
local {
    timestamp = regex_replace(timestamp(), "[- TZ:]", "")
}
```

### ✅ Use Case

```packer
source "amazon-ebs" "ubuntu" {
    ami_name    = "${var.ami_prefix}-${local.timestamp}"
}
```