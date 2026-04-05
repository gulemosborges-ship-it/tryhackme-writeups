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
Ataques de dicionário funcionam porque muitas pessoas utilizam senhas fracas ou comuns, como "123456", "qwerty" ou "password". Além disso, é frequente a reutilização de senhas em vários serviços diferentes.

O Hydra se aproveita disso testando automaticamente uma lista de senhas prováveis contra um usuário específico. Para cada tentativa, ele analisa a resposta do servidor — se a resposta contiver a mensagem definida em F=, a tentativa foi falha. Quando a resposta for diferente, a senha foi encontrada.

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
