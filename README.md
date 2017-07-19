# quickcrypt

Simple script to create a gpg encrypted archive that can be decrypted by an intended recipient. The script requires a GPG key, a recipient's UID, and a directory or target to archive and encrypt.

## Encrypt

Create directory containing the files you intend to encrypt.

The script takes a recipients public key, and a target file or folder to encrypt.

## Usage

```
quickcrypt [-v] -r <recipient public key> -f <files to archive>
```

An encrypted archive will be created, as well as a sha256 hash of the archive that can be used to verify the contents after decryption.

## Decrypt

To decrypt the files with the recipient's key, use regular gpg decryption.

```
gpg --output ${ARCHIVE_FILES}.tar --decrypt ${ARCHIVE_FILES}.tar.gpg
```

Now verify the shaw256sum is the same.

```
sha256sum ${ARCHIVE_FILES}.tar
```
