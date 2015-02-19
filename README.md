# SSL role 

##  Tasks

This role depends that you use [ansible vault](http://docs.ansible.com/playbooks_vault.html)

1. Creating the ssl directory on server. The path is defined in default variables under defaults/main.yml.
2. Decrypting the pem certificate from all servers defined in ssl_dev and write it into a file named by service on server.
3. Decrypting the key certificate from all servers defined in ssl_dev and write it into a file named by service on server.

## Variables

This is the default variable file you would want to encrypt yours with ansible vault

```
# Where to install the cert
ssl_path                    : "/etc/ssl/YOURORG"
#
# ssl certificates Example you would need to override this in group/hosts vars
#
ssl_cert:
  - hostname  : "www.example.com"
    key       :     |
                    -----BEGIN PRIVATE KEY-----
                    MIIEvwIBADANBgkqhkiG9w0BAQEFAASCBKkwggSlAgEAAoIBAQDqEkvLxnGpnlDt
                    YqFWoOAGzli7Ad8sLNB2W3VZeP/oCDJ/CiD6rD0KjI7T0W41Hf57SWHTzADki245
                    3IBBAWTiPL6oV40/Vu1K5PDBUSX8ogYFSKm5J/bJx/1ayfSIUfPSAjTCRlCH4TO9
                    l8IEEbTIZSHSRBpgbREje1muBplo/Moyl4lq/lYiyBLIweCh7UUzkZi8beo/lJ62
                    ................................................................
                    3IBBAWTiPL6oV40/Vu1K5PDBUSX8ogYFSKm5J/bJx/1ayfSIUfPSAjTCRlCH4TO9
                    uzaY1XuoXboHWPvrxh48TdslSg==
                    -----END PRIVATE KEY-----
    pem       :     |
                    -----BEGIN CERTIFICATE-----
                    MIIC2jCCAcICCQDAvnpKa//EZDANBgkqhkiG9w0BAQUFADAvMS0wKwYDVQQDEyQ3
                    NDg2NWIxMC1kZTg4LWU4OTUtOGYzYS1jNWVkMmJhZDY2NmEwHhcNMTQwOTA1MTM1
                    ................................................................
                    ................................................................
                    ................................................................
                    zCZJYxzkkjlj9DGlgZZzfx4lPW/5r5TlCGdytaRwBLoQKM74SeSjhQhGOJZQHg35
                    ................................................................
                    ................................................................
                    bbwgnk6vLg7FUxKCjHlatqqwTCzotrKMtZg2Xb866VnXMmJawa7ZPUaR8qDI+goo
                    rajsBfV8TWJegATUdp8=
                    -----END CERTIFICATE-----

  - hostname  : "queue.example.com"
    key       :     |
                    -----BEGIN PRIVATE KEY-----
                    MIIEvwIBADANBgkqhkiG9w0BAQEFAASCBKkwggSlAgEAAoIBAQDqEkvLxnGpnlDt
                    YqFWoOAGzli7Ad8sLNB2W3VZeP/oCDJ/CiD6rD0KjI7T0W41Hf57SWHTzADki245
                    3IBBAWTiPL6oV40/Vu1K5PDBUSX8ogYFSKm5J/bJx/1ayfSIUfPSAjTCRlCH4TO9
                    l8IEEbTIZSHSRBpgbREje1muBplo/Moyl4lq/lYiyBLIweCh7UUzkZi8beo/lJ62
                    ................................................................
                    3IBBAWTiPL6oV40/Vu1K5PDBUSX8ogYFSKm5J/bJx/1ayfSIUfPSAjTCRlCH4TO9
                    uzaY1XuoXboHWPvrxh48TdslSg==
                    -----END PRIVATE KEY-----
    pem       :     |
                    -----BEGIN CERTIFICATE-----
                    MIIC2jCCAcICCQDAvnpKa//EZDANBgkqhkiG9w0BAQUFADAvMS0wKwYDVQQDEyQ3
                    NDg2NWIxMC1kZTg4LWU4OTUtOGYzYS1jNWVkMmJhZDY2NmEwHhcNMTQwOTA1MTM1
                    ................................................................
                    ................................................................
                    ................................................................
                    zCZJYxzkkjlj9DGlgZZzfx4lPW/5r5TlCGdytaRwBLoQKM74SeSjhQhGOJZQHg35
                    ................................................................
                    ................................................................
                    bbwgnk6vLg7FUxKCjHlatqqwTCzotrKMtZg2Xb866VnXMmJawa7ZPUaR8qDI+goo
                    rajsBfV8TWJegATUdp8=
                    -----END CERTIFICATE-----
```

## Quick intro to vault

Following command is used to encrypt file.

    ansible-vault encrypt vault-ssl.yml

Following command is used to edit encrypted file.

    ansible-vault edit vault-ssl.yml


