# Enumeração de Diretórios com Gobuster

## Objetivo
Identificar diretórios e páginas ocultas em um site.

## Ferramentas
Gobuster.

## Comando utilizado
gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt

## Explicação do comando

- **dir** -> Procurar por diretórios.
- **--url** -> Alvo da busca.
- **-w** -> Indicar a Wordlist usada.

O trecho: "/usr/share/wordlists/dirbuster/directory-list.txt" aponta para um arquivo no sistema Linux que contém uma wordlist.

Essa lista é usada pelo Gobuster para testar possíveis nomes de diretórios no site.

## Funcionamento

O Gobuster utiliza uma lista de palavras para revelar possíveis diretórios ocultos no site, como:

- /admin  
- /login  
- /uploads  

Se retornar 200, o diretório existe. Se retornar 404, não existe.

## Resultados

/login (Status: 200) 

## O que aprendi:

- Como funciona enumeração de diretórios  
- Uso de wordlists  

## Observação Importante

Essa técnica foi utilizada em um ambiente controlado (laboratório do TryHackMe), com fins educacionais.
