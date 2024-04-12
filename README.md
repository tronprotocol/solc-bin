# tron-solc-bin

This repository contains current and historical builds of the [TRON Solidity Compiler](https://github.com/tronprotocol/solidity).

## Integrity Check

All builds are signed the gpg key:
```
pub: 1254 F859 D2B1 BD9F 66E7 107D F859 BCB4 4A28 290B
uid: build@tron.network
```

### Install GPG

If you have already installed GPG, please skip this step. If not, please refer to the following command to install it on MacOS:

```
$ brew install gpg
```

On Debian, Ubuntu and other Linux distributions:

```
$ sudo apt install gpg
```

### Import public key

If you have imported the public key before, please skip this step, just import the public key once.

Import the public key from the GPG public key server to the local according to the public key Hash, the command is:

```
$ gpg --keyserver hkp://keys.openpgp.org --recv-keys "1254 F859 D2B1 BD9F 66E7 107D F859 BCB4 4A28 290B"
```

If the import was successful, you will see the return result like this:

```
gpg: key 785FB96D2C7C3CA5: public key “build_tron <build@tron.network>” imported
gpg: Total number processed: 1
gpg:        imported: 1
```

### Signature verification

For example, if the executable file of a certain version is `solc-macosx-amd64-v0.8.18+commit.f18bedfe` and the signature file is `solc-macosx-amd64-v0.8.18+commit.f18bedfe.sig`, the signature verification command is:

```
$ gpg --verify solc-macosx-amd64-v0.8.18+commit.f18bedfe.sig solc-macosx-amd64-v0.8.18+commit.f18bedfe
```

If the signature verification is passed, the following will be returned:

```
gpg: Signature made Fri. 21/ 7 17:07:02 2023 CST
gpg:        using RSA key 1254F859D2B1BD9F66E7107DF859BCB44A28290B
gpg: Good signature from “build_tron <build@tron.network>” [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:     There is no indication that the signature belongs to the owner.
Primary key fingerprint: 07B2 3298 AEA4 E006 BD9A  42DE 785F B96D 2C7C 3CA5
Subkey fingerprint: 1254 F859 D2B1 BD9F 66E7 107D F859 BCB4 4A28 290B
```

If the verification fails, it will display the words `gpg: BAD signature from “build_tron <build@tron.network>”`.
