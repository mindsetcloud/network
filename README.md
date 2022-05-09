# network

## nomear dispositivo
```sh
Switch#configure terminal
Switch(config)#hostname Sw-Floor-1
Sw-Floor-1(config)#
```
## proteger o acesso ao modo EXEC do usuário
```sh
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#line console 0
Sw-Floor-1(config-line)#password cisco
Sw-Floor-1(config-line)#login
Sw-Floor-1(config-line)#end
Sw-Floor-1#
```

## proteger o acesso ao modo PRIVILEGIADO
```sh
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#enable secret class
Sw-Floor-1(config)#exit
Sw-Floor-1#
```

## proteger linhas VTY (acesso remoto ssh telnet)
```sh
Sw-Floor-1# configure terminal
Sw-Floor-1(config)#1(config)# line vty 0 15
Sw-Floor-1(config-line)#password cisco 
Sw-Floor-1(config-line)#login 
Sw-Floor-1(config-line)#end
```
## show config
```sh
Sw-Floor-1#show running-config
```
## criptografar todas as senhas de texto simples
```sh
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#service password-encryption
Sw-Floor-1(config)#
```
