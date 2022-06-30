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
## configure ipv4 on switch
```sh
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# interface vlan 1
Sw-Floor-1(config-if)# ip address 192.168.1.20 255.255.255.0
Sw-Floor-1(config-if)# no shutdown
Sw-Floor-1(config-if)# exit
Sw-Floor-1(config)# ip default-gateway 192.168.1.1
```

## verifica a condição das interfaces do switch
```sh
ipconfig show ip interface brief
```
## aprimorar o login
```sh
R1# configure terminal
R1(config)# login block-for 15 attempts 5 within 60 
R1(config)# ip access-list standard PERMIT-ADMIN
R1(config-std-nacl)# remark Permit only Administrative hosts     
R1(config-std-nacl)# permit 192.168.10.10
R1(config-std-nacl)# permit 192.168.11.10 
R1(config-std-nacl)# exit 
R1(config)# login quiet-mode access-class PERMIT-ADMIN   
R1(config)# login delay 10  
R1(config)# login on-success log  
R1(config)# login on-failure log
R1(config)# security authentication failure rate threshold-rate log  
R1(config)#exit
R1# show login
R1# show login failures
```
## mudar algoritmo de encriptação

R1(config)# enable algorithm-type ?
R1(config)# enable algorithm-type scrypt secret cisco12345
R1(config)# username Bob algorithm-type scrypt secret cisco54321
 
