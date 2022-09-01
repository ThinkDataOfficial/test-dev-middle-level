# Teste desenvolvedor pleno

## Teste 1 - Habilidades de programação  

Monte 3 funções

1. Separa letras de números 
2. Remove caracteres especiais e acentos.
3. Remove caracteres em branco duplicados.

#### Exemplo de input/output das 3 funções aplicadas:

  Input: ```Rua Jose de Sá brito167,apto005SÃO@PAULO – SP```
  
  Output: ```Rua Jose de Sa Brito 167 Apto 5 SAOPAULO SP```
  
-	Crie uma WebApi com um endpoint `GET /sanitize/:endereco` que receba uma string, execute as funções criadas no passo anterior nesta string e devolva o resultado UpperCase em um JSON como exemplo:
```
  {
    input: 'Rua Jose de Sá brito167,apto@@@005SÃO PAULO – SP',
    output: 'RUA JOSE DE SA BRITO 167 APTO 5 SAO PAULO SP'
  }
```
-	Em seguida, crie uma aplicação do tipo Console Application e leia o arquivo CLIENTE_XPTO.TXT localizado na pasta /files/input e aplique as seguintes regras definida na sub-seção [Regras](#regras)

## Layouts
### Layout de entrada
<table>
<tr>	<th>Seq</th>	<th>Ini</th>	<th>Tam</th>	<th>Alfa/Numerico</th>	<th>Descrição</th>
<tr>	<td>1</td>	<td>1</td>	<td>1</td>	<td>N</td>	<td>Código do registro</td>
<tr>	<td>2</td>	<td>2</td>	<td>14</td>	<td>N</td>	<td>Número do CNPJ da instituição informante ajustado à direita e preenchido com zeros à esquerda</td>
<tr>	<td>3</td>	<td>16</td>	<td>8</td>	<td>N</td>	<td>Data do movimento (AAAAMMDD) – data de geração do arquivo </td>
<tr>	<td>4</td>	<td>24</td>	<td>4</td>	<td>N</td>	<td>Número de DDD do telefone de contato da instituição informante </td>
<tr>	<td>5</td>	<td>28</td>	<td>8</td>	<td>N</td>	<td>Número do telefone de contato da instituição informante </td>
<tr>	<td>6</td>	<td>36</td>	<td>4</td>	<td>N</td>	<td>Número de ramal do telefone de contato da instituição informante</td>
<tr>	<td>7</td>	<td>40</td>	<td>70</td>	<td>A</td>	<td>Nome/Razao Social da Instituição</td>
<tr>	<td>8</td>	<td>110</td>	<td>200</td>	<td>X</td>	<td>Endereço (Tipo, Logradouro, Numero, Complemento)</td>
<tr>	<td>9</td>	<td>310</td>	<td>50</td>	<td>A</td>	<td>Cidade</td>
<tr>	<td>10</td>	<td>360</td>	<td>2</td>	<td>A</td>	<td>UF</td>
<tr>	<td>11</td>	<td>362</td>	<td>8</td>	<td>N</td>	<td>CEP</td>
<tr>	<td>12</td>	<td>370</td>	<td>3</td>	<td>N</td>	<td>Indentificação do registro</td>
<tr>	<td>13</td>	<td>373</td>	<td>8</td>	<td>X</td>	<td>Informar o LOGON a ser utilizado na contabilização das cartas comunicado e anotações.</td>
<tr>	<td>14</td>	<td>381</td>	<td>101</td>	<td>X</td>	<td>Espaços em Branco</td>
<tr>	<td>15</td>	<td>482</td>	<td>3</td>	<td>X</td>	<td>Código de erros</td>
<tr>	<td>16</td>	<td>485</td>	<td>7</td>	<td>N</td>	<td>Seqüência do registro</td>
</table>					 


### Layout de saída
<table>		
<tr>	<th>Seq</th>	<th>Descrição</th>
<tr>	<td>1</td>	<td>CNPJ</td>
<tr>	<td>2</td>	<td>Logradouro</td>
<tr>	<td>2</td>	<td>Número</td>
<tr>	<td>2</td>	<td>Complemento</td>
<tr>	<td>3</td>	<td>Cidade</td>
<tr>	<td>4</td>	<td>UF</td>
<tr>	<td>5</td>	<td>CEP</td>
<tr>	<td>6</td>	<td>Nome do contato da instituição informante</td>
<tr>	<td>7</td>	<td>Sequencia do Registro</td>
</table>		 

### Regras e Informações
- No campo de endereço, aplique a função criada no teste anterior chamando o endpoint criado na webApi.
-	Altere a ordem e o formato do arquivo, para que o arquivo de saída seja conforme o layout definido [Layout de Saída](#layout-de-saída)
-	O endereço deve ficar separado em três colunas, logradouro, número e complemento
- É considerado complemento, tudo aquilo que vem após o primeiro número do endereço. *Ex.: R MARIA HELENA 405 CS 6 | o complemento é CS 6* 
-	Os campos do layout de saída devem ser separados por TABs (ASCII 9).
-	Salve o arquivo no diretório /files/output com o nome de {NomeOriginal}_YYYYMMDD_Resultado.TXT.
-	Mova o arquivo original para o diretório /files/input/processed

## Teste 2 - Habilidades de análise (resolução de problemas)

Imagine que você precise adicionar uma funcionalidade em um WebApp existente. Você agora irá oferecer à seu cliente um serviço em que ele possa realizar uma negativação na Serasa.

*(Negativação é o processo de registro de um CNPJ junto à Serasa, informando à Serasa que determinado CNPJ não é um bom pagador, pois deixou uma dívida em aberto.)*

Você sabe que:
- Seu cliente possui diversos CNPJ em que ele gostaria de fazer a negativação.
- A negativação é iniciada fazendo uma chamada à uma API da Serasa.
- A comunicação é feita através de uma API da Serasa e ela devolve status 200 quando a requisição foi enviada com sucesso ou status 400 caso a requisição seja enviada de maneira incorreta. Sem corpo de resposta.
- A negativação pela Serasa demora até 2 dias para devolver um resultado.
- O retorno com o resultado da negativação é devolvido através de um FTP disponibilizado pela Serasa em um arquivo TXT de layout com campos de tamanho fixo (estilo mainframe).
- A Serasa realiza o processo de negativação, porém, não mantém um histórico do que foi negativado.
- Quando um CNPJ paga sua dívida, ele precisa ser desnegativado. Este processo deve ser feito pelo cliente que fez a negativação em nossa plataforma.

Descreva como resolveria este problema. Pode ser um vídeo, um Word, um ambiente simulado. O importante é demonstrar uma solução.

# Considerações

Faça um fork desse projeto e suba sua resolução para o git. Pode ser uma PR aqui neste repositório ou um repo próprio. No caso de subir para um repo próprio envie um e-mail para adriano.giopato@thinkdata.com.br informando que o seu teste foi finalizado.
