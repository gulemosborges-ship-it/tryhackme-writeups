## Ataque de Dicionário

## Objetivo
Utilizar Hydra(Ferramenta de automatização de tentativas de login) para descobrir senhas de login em um site.

## Comando utilizado
hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V

## Explicação do Comando
- **-l admin** → define o nome de usuário
- **-P passlist.txt** → lista de senhas que serão testadas
- **http-post-form** → indica que o login é feito via POST
- **^USER^ e ^PASS^** → variáveis substituídas que serão substituídas automaticamente pelo Hydra
- **F=incorrect** → indica que a tentativa falhou quando aparece "incorrect"
- **-V** → Mostrar cada tentativa

## Funcionamento
O Hydra um ataque de dicionário, testando várias senhas automaticamente em um usuário especifico.

No comando, o trecho "F=incorrect" define que, caso a resposta do servidor contenha essa mensagem, a tentativa foi considerada falha.

## Resultado
Após a execução do ataque de dicionário com o Hydra:

- Usuário: admin  
- Senha encontrada: qwerty  

O Hydra identificou a senha correta ao detectar uma resposta diferente da mensagem de erro definida ("incorrect").

## Aprendizados
- Como funciona ataque de dicionário
- Automação de tentativas de login

## Limitações
O Hydra pode se tornar ineficaz caso o sistema possua:

- Respostas de erro diferentes da definida ("incorrect")
- Captchas
- Limites de tentativas
