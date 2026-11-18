# Plano do site: Limpeza pós-obra em Ribeirão Preto

## Escopo e implementação

O produto será um site estático multipágina, em português do Brasil, para captação de contatos locais. A aplicação usará apenas HTML, CSS e JavaScript nativos, sem dependências de execução. Cada conteúdo ficará no seu próprio `index.html`; caminhos públicos começarão por `/`. Três arquivos compartilhados terão funções separadas: `style.css` para o design, `config.js` para dados editáveis do portal e números de contato, e `tracker.js` para atualizar links e registrar cliques no endpoint de Apps Script. O formulário rápido será composto por `select` e o script fornecido montará sua mensagem.

As 13 rotas serão: `/`; três serviços em `/servicos/limpeza-fina-pos-obra/`, `/servicos/limpeza-de-pisos-e-revestimentos/`, `/servicos/limpeza-de-vidros-e-esquadrias/`; seis bairros em `/bairros/centro/`, `/bairros/jardim-botanico/`, `/bairros/nova-alianca/`, `/bairros/vila-tiberio/`, `/bairros/bonfim-paulista/`, `/bairros/campos-eliseos/`; além de `/sobre/`, `/perguntas-frequentes/` e `/politica-de-privacidade/`. O sitemap, robots, llms.txt, favicon e JSON-LD acompanharão as páginas. O JSON-LD será serializado para JSON válido e as respostas de FAQ reproduzirão o texto visível.

O conteúdo será cauteloso: descreverá tarefas comuns de limpeza após reforma sem garantir que qualquer produto, ferramenta ou procedimento seja adequado a toda superfície. O prestador deve confirmar compatibilidade, escopo, valores, prazo e condições. As páginas de bairro variarão exemplos e ordem das orientações sem alegações sobre ruas, edifícios, estabelecimentos ou deslocamentos.

A privacidade descreverá precisamente os metadados de clique informados no prompt, a finalidade de medição, o encaminhamento posterior ao prestador e os direitos previstos pela LGPD, sem coleta de nome, e-mail ou CPF e sem cookies de publicidade.

## Estrutura e publicação

A raiz terá `index.html`, `servicos/`, `bairros/`, `sobre/`, `perguntas-frequentes/`, `politica-de-privacidade/`, `img/`, `style.css`, `tracker.js`, `config.js`, `favicon.svg`, `sitemap.xml`, `robots.txt`, `llms.txt`, `vercel.json`, `package.json`, `build.js`, `apps-script/Code.gs` e `LEIA-ME.txt`. O `package.json` terá zero dependências. O script `build.js` copiará arquivos estáticos para `dist`, e o `vercel.json` usará o comando `npm run build` com saída `dist`. Nenhuma publicação externa ou conexão ao GitHub será iniciada sem autorização específica.

## Direção visual

A referência fornecida define o estilo: layout acolhedor de cantos arredondados, navegação branca em pílula sobreposta, hero amplo com imagem e gradiente escuro, botões em pílula e seções alternando fundo creme e tons suaves da cor principal. A paleta é `#155e63` (principal), `#0f4347` (escura), `#ecf2f3` (suave) e `#d0dfe0` (suave 2), sobre `#fdfbf7` com texto `#23201d`. Os CTAs serão verde `#157a3e` e telefone `#1f2937`. Tipografia Fira Sans com sistema como alternativa; controles com foco visível, contraste legível, alvos de toque mínimos de 44 px e respeito a `prefers-reduced-motion`.

Marca: portal local informativo, de tom simples, calmo e direto. A assinatura visual será um pequeno símbolo geométrico de brilho/limpeza em SVG e uma linha teal discreta. Imagens ilustrativas geradas sob medida serão posicionadas no hero, seção sobre e um cartão por serviço, sem atribuí-las ao prestador.

## Requisitos funcionais

Todos os botões terão os atributos `data-acao` e `data-local`; WhatsApp também terá `data-msg`. `config.js` terá números provisórios `5516900000000`, que poderão ser trocados sem edição das páginas. `tracker.js` seguirá a lógica fornecida para montar `wa.me`, `tel:`, mensagem do pedido rápido, sessão aleatória e GET sem CORS ao endpoint com os campos solicitados. `apps-script/Code.gs` será incluído sem alteração.

## Fluxo de construção

Depois da revisão do plano, serão preparados os 13 HTMLs reais, os arquivos compartilhados, as páginas institucionais, o Apps Script, os recursos SEO e as instruções de uso. Por fim serão feitas verificações estáticas de rotas, metadados, links internos, contagem de páginas, marcação estruturada, atributos dos botões, tamanho do conteúdo e execução do build. As fotografias serão incluídas quando a geração assíncrona estiver concluída; se não puderem ser obtidas como arquivos para distribuição, serão documentadas no `img/PROMPTS.txt` e o site manterá alternativas visuais neutras.
