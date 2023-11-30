
[Encrypt Your Sensitive Information Before Storing It - Encrypting with Mozilla SOPS and AGE](https://technotim.live/posts/secret-encryption-sops/)

to encrypt

```shell

sops --encrypt --age $(cat $SOPS_AGE_KEY_FILE |grep -oP "public key: \K(.*)") --encrypted-regex '^(data|stringData)$' --in-place ./secret.yaml

```
to decrypt

```shell
sops --decrypt --age $(cat $SOPS_AGE_KEY_FILE |grep -oP "public key: \K(.*)") --encrypted-regex '^(data|stringData)$' --in-place ./secret.yaml
```

