# LocaliZAZ.js

O LocaliZAZ é feito totalmente em JavaScript, e permite que o programador adquira dados básicos e realmente necessários de Estados, cidades (incluindo seus códigos IBGE), aeroportos (e seus códigos IATA) e CEPs (com detalhes como logradouro, bairro, IAG/ICMS da cidade, entre outros) para uso em formulários HTML.

## ``` ESTE É UM FORK DO PROJETO ORIGINAL!!!```

### Tarefas já realizadas neste fork:
- Reorganização das funções de preenchimento dos elementos de formulário;
- Adição de comentários com explicações mais detalhadas sobre as funções e constantes;
- Criação de função separada para o preenchimento do seletor de aeroportos.

### Tarefas em andamento neste fork:
- Organização dos arrays contendo os dados de estados, cidades, aeroportos, códigos IBGE e códigos IATA em arquivos JSON separados, para maior legibilidade e facilidade de atualização de dados;
- Adequação das funções para uso dos arrays mencionados anteriormente em formato JSON.

```O uso do projeto é livre, peço somente que coloquem os créditos aos autores e colaboradores do mesmo.```

Testado, o mesmo roda em navegadores **IE 8+**. Verifique a compatibilidade do seu navegador executando o arquivo de teste, caso queira dar um feedback ficaremos muito gratos!


## Funcionalidades:
- Listas de:
  - Estados;
  - Cidades por Estado;
  - Aeroportos por Estado;
  - Aeroportos por Cidade;
  - Códigos IBGE de Estados e cidades;
  - Códigos IATA de aeroportos;
- Dados relativos à Códigos Postais (CEP).


## Implementação
Basta abrir o script **localizaz.js**, no diretório **src**, e alterar os valores das constantes globais pelos ID's das entradas de formulário em sua página HTML:

```
const formulario = "form"; /** Valor original: "form" */
const select_estado = "estado"; /** Valor original: "estado" */
const select_cidade = "cidade"; /** Valor original: "cidade" */
const input_cod_estado = "cod_estado"; /** Valor original: "cod_estado" */
const input_cod_cidade = "cod_cidade"; /** Valor original: "cod_cidade" */
const select_aeroporto = "aeroporto"; /** Valor original: "aeroporto" */
const fieldset_cep = "BuscaCEP"; /** Valor original: "BuscaCEP" */
const input_cep = "cep"; /** Valor original: "cep" */
```

```Cabe ao desenvolvedor definir como processar os dados obtidos com este script.```

### RETORNO DOS DADOS DE CEP
Utilizamos a API do [ViaCEP](https://viacep.com.br/) junto dos dados do LocaliZAZ para retornar as informações sobre os códigos postais.
Nesse caso é necessário que o desenvolvedor direcione os dados recebidos pela API para seu sistema ou campos necessários.
Para fazer isso procure pela linha:

```
// _________PROGRAME___AQUI___O___DESTINO___DOS___DADOS___RECEBIDOS_________ //
```

O desenvolvedor pode usar os seguintes objetos JSON para retornar os dados:

```
[-] retorno.logradouro: Endereço do CEP digitado,
[-] retorno.bairro: Bairro do CEP digitado,
[-] retorno.cep: CEP formatado contendo apenas números e traço,
[-] retorno.complemento: Complemento do CEP digitado (Endereço),
[-] retorno.localidade: Cidade do CEP digitado,
[-] retorno.uf: Estado do CEP digitado,
[-] retorno.ibge: Código do IBGE referente a Cidade,
[-] retorno.gia: GIA/ICMS da cidade/região onde se localiza o CEP,
[-] retorno.ddd: DDD da cidade/região onde se localiza o CEP,
[-] retorno.siafi: Código da Cidade S.I.A.F.I (Sistema Integrado de Administração Financeira) da cidade/região onde se localiza o CEP.
```

``` O arquivo``` **.htaccess** ```deve ser incluído na raiz do diretório de armazenamento da página, para que os recursos de API ViaCEP funcionem corretamente.```

Gostou do projeto? Quer nos ajudar a manter o mesmo? Ajude com uma contribuição, fork ou compartilhamento.
