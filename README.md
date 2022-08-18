# Teste desenvolvedor pleno

## Teste 1 - Habilidades de programação

-	Monte uma função que separa letras de números e remove caracteres especiais.


### Exemplos

  Input: ```Rua Jose de Sá brito167, apto005SAO PAULO – SP```
  
  
  Output: ```Rua Jose de Sá Brito 167 Apto 5 SÃO PAULO SP```
  
-	Crie uma WebApi com um método que execute o código da função criada no passo anterior.
-	Em seguida, crie uma aplicação do tipo Console Applicatio e  leia o arquivo CPF.TXT localizado na pasta CANDIDATO e aplique as seguintes regras nos campos:
- - END
- - FONE
- - CPF


- No campo de endereço, aplique a função criada no teste anterior chamando o endpoint criado na webApi do passo anterior.
-	Altere a ordem das colunas de forma que o CPF seja a primeira coluna.
-	O endereço deve ficar separado em duas colunas, endereço e número. 
-	O layout de saída deve ser separado por TAB.
-	Salve o arquivo no diretório Candidato/Processados com o nome {NomeOriginal}_YYYYMMDD_Resultado.TXT.
-	Salve o arquivo original no diretório Candidato/Entrada

## Teste 2 - Habilidades de banco de dados SQLSERVER



## Teste 3 - Habilidades de análise (resolução de problemas)

Imagine que você precise adicionar uma funcionalidade em um WebApp existente. Você agora irá oferecer à seu cliente um serviço em que ele possa realizar uma negativação na Serasa.

*(Negativação é o processo de registro de um CNPJ junto à Serasa, avisando à Serasa que determinado CNPJ não é um bom pagador, pois deixou uma dívida em aberto.)*

Você sabe que:
- Seu cliente possui diversos CNPJ em que ele gostaria de fazer a negativação.
- A negativação é iniciada fazendo uma chamada à uma API da Serasa.
- A API só devolve status 200 ou 404. Sem corpo de resposta.
- A negativação pela Serasa demora até 2 dias para devolver um resultado.
- O retorno com o resultado da negativação é devolvido através de um FTP disponibilizado pela Serasa em um arquivo TXT de layout de tamanho fixo (mainframe).
- A Serasa realiza o processo de negativação, porém, não mantém um histórico do que foi negativado.
- Quando um CNPJ paga sua dívida, ele precisa ser desnegativado. Este processo é feito pelo cliente que fez a negativação.

Descreva como resolveria este problema. Pode ser um vídeo, um Word, um ambiente simulado.

