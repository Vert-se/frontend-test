# Teste Prático

O objetivo do teste é construir um pequeno dashboard contendo 2 componentes gráficos a partir de uma API disponibilizada, e consumir um datastream para atualiza-los periodicamente

# Passos

1 - De um fork neste projeto e clone-o em seu computador.

2 - Construa um módulo que consuma a seguinte API:

  - api: https://api.setters.co/dashboard-sample-payload/

3 - Numa página html, utilize a estrutura do payload para renderizar os componentes gráficos (charts) recebidos da forma que achar mais prudente (partindo de sua própria interpretação sobre os specs listados no payload).

4 - Abasteça os charts com seus respectivos dados consumindo os endpoints `dataSource` de cada gráfico, encontrados no payload da etapa 2.

5 - Atualize periodicamente os charts utilizando os mesmos endpoints     `dataSource`. Você pode utilizar quaisquer das 2 estratégias:

**Pooling**
> Gerencie a atualização periódica pelo seu próprio app, (via `setTimeout` / `setInterval`) solicitando novos dados a cada **5 segundos**

**Socket io**
> Inclua o módulo client do `socket.io` em seu html e conecte-se via websocket para receber os dados do servidor periodicamente, utilizando o mesmo endpoint  `dataSource`, e escutando o channel ```data```, por ex:
```javascript
const socket = io(/* component.dataSource */)
socket.on('data', function(res) {
  // Atualiza componente com os novos dados
})
```
Obs: Em ambas estratégias, é esperado que o app trate a atualização de cada componente de forma independente

# Critérios de avaliação
O objetivo deste teste é avaliar:
 - qualidade e organização do código apresentado
 - conhecimento sobre APIs e programação assíncrona
 - capacidade em interpretar regras de configuração por um documento JSON
 - familiaridade com data vizualizaition e manipulação de componentes gráficos

# Recomendações
Você pode utilizar a biblioteca de sua preferência para a geração dos charts.

Caso o projeto demande etapas adicionais para o deploy da versão final você deve incluir um README com as instruções de deploy na raíz do seu repositório, substituindo este.

 É esperado que você apresente uma aplicação que funcione antes de tudo, por isso deve utilizar o caminho que for mais familiar e seguro dentro do seu campo de conhecimento. Ainda sim, esperamos encontrar em seu projeto um ou mais recursos da seguinte lista:
  - Utilização de um precompilador para automação de devops (gulp, webpack, etc)
  - Recursos do ES6
  - Utilização de um pre-processador de CSS
  - Utilização de uma biblioteca de renderização (React / Vue / Angular)