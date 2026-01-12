# SamsungSIOPCrypt

Python script to decrypt and encrypt Samsung SIOP policies.

## Background

Starting OneUI 8, Samsung began encrypting their SIOP policies using AES-256-CBC encryption, with a SHA-256 hash of the policy name serving as the decryption key.

This script is based on the actual code Samsung uses in the SamsungDeviceHealthManager APK to decrypt these XML tables.

## Usage

```
$ ./siopcrypt -h
usage: siopcrypt [-h] [-o OUT] (-d | -e) policy_file policy_name

A tool to decrypt/encrypt SIOP policies for OneUI 8 and later.

positional arguments:
  policy_file    input file path
  policy_name    SIOP policy name (Refer to SEC_FLOATING_FEATURE_SYSTEM_CONFIG_SIOP_POLICY_FILENAME)

options:
  -h, --help     show this help message and exit
  -o, --out OUT  output file path (default: <policy_name>.xml / siop_model)
  -d, --decrypt  decrypt the policy (default)
  -e, --encrypt  encrypt the policy

$ ./siopcrypt -d siop_model siop_r0s_exynos2200
```

## Requirements

To use the script, you need python3 as well as the python-cryptography library installed on your system.

The required policy name can be obtained from `etc/floating_feature.xml` in your firmware's system or vendor partition.

## Licensing

This project is licensed under the terms of the MIT License.
