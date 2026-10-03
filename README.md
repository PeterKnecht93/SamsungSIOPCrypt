# SamsungSIOPCrypt

A Python script to decrypt and encrypt Samsung SIOP policies.

## Background

Starting with One UI 8, Samsung began encrypting their SIOP policies using AES-256-CBC encryption, with a SHA-256 hash of the policy name serving as the encryption key.

This script is based on the code that SamsungDeviceHealthManager uses to decrypt these XML tables.

## Usage

```console
$ ./siopcrypt -h
usage: siopcrypt [-h] [-o OUT] (-d | -e) policy_file policy_name

A tool to decrypt and encrypt Samsung SIOP policies.

positional arguments:
  policy_file    input file path
  policy_name    SIOP policy name (Refer to SEC_FLOATING_FEATURE_SYSTEM_CONFIG_SIOP_POLICY_FILENAME)

options:
  -h, --help     show this help message and exit
  -o, --out OUT  output file path (default: <policy_name>.xml / siop_model)
  -d, --decrypt  decrypt the policy
  -e, --encrypt  encrypt the policy
```

## Requirements

This script requires Python 3 or newer as well as the cryptography library to be installed on your system.

The required policy name can be obtained from `etc/floating_feature.xml` in your firmware's system or vendor partition.

## Licensing

This project is licensed under the terms of the MIT License.
