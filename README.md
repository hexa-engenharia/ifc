# Visualizador IFC · HEXA Engenharia

Visualizador 3D de modelos IFC que funciona direto no navegador, no celular ou no computador, sem instalar nada.

**Acesse:** https://hexa-engenharia.github.io/ifc/

Ele foi feito para ser aberto pelo **QR code impresso nas pranchas** da HEXA. Você aponta a câmera do celular para o QR e o modelo 3D do projeto abre na hora, já com as disciplinas separadas.

---

## Como abrir um modelo

| Jeito | Como |
|---|---|
| **Pelo QR code da prancha** | Aponte a câmera do celular para o QR e toque no link. |
| **Por um link** | `https://hexa-engenharia.github.io/ifc/?d=<ID do arquivo no Google Drive>` |
| **Arquivo do seu aparelho** | Abra o site e toque em **Abrir arquivo** (`.ifc`, `.ifczip` ou `.zip`). |

> **Privacidade:** um arquivo aberto do seu aparelho é lido só no seu navegador e não é enviado para lugar nenhum. Os modelos dos QR codes são lidos, somente para leitura, do Google Drive onde a HEXA os publicou.

---

## Navegação

| | Computador | Celular / tablet |
|---|---|---|
| Girar | arrastar com o botão esquerdo | arrastar com um dedo |
| Mover (pan) | arrastar com o botão direito | arrastar com dois dedos |
| Zoom | rodinha do mouse (aproxima onde está o cursor) | pinçar com dois dedos |

**Cubo de vistas (como no Revit),** no canto superior direito:
- **Clique numa face, aresta ou canto** para ver o modelo daquele lado, enquadrando o que está visível.
- **Arraste o cubo** para girar a vista. Ela vai travando nas faces, arestas e cantos.
- **Arraste o anel** em volta do cubo para girar só na horizontal. Funciona também para girar a planta vista de cima.
- **N, S, L, O:** um clique gira até aquele lado, mantendo a inclinação.
- **Setas:** aparecem nas vistas alinhadas e levam para a face vizinha.
- **Casinha:** volta para a vista inicial.
- **Paralela / Perspectiva:** troca o tipo de câmera. A paralela é o padrão.

Com algum objeto selecionado, o giro é feito em volta dele.

---

## Painel (canto inferior esquerdo)

- **Disciplinas:** liga e desliga cada disciplina do modelo unificado (Força, Iluminação, Automação, Arquitetura…).
- **Tipos:** liga e desliga categorias, como eletrodutos, eletrocalhas, quadros e luminárias. Só aparecem os tipos das disciplinas ligadas.
- **Vistas:** salve e reabra pontos de vista (veja mais abaixo).
- **Cores:** por disciplina, por tipo ou as cores originais do modelo.
- **Mostrar tudo:** volta tudo ao normal. Mostra o que estava oculto, sai do isolamento e remove o corte.

---

## Ferramentas

| Ferramenta | O que faz |
|---|---|
| **Selecionar** | Clique ou toque num objeto para ver nome, tipo, dimensões (diâmetro e bitola de eletrodutos, seção de eletrocalhas, comprimento) e propriedades. No cartão do objeto: **Enquadrar**, **Isolar**, **Ocultar** e **Raio-X**. |
| **Seleção múltipla** | Pelo botão, ou com Ctrl+clique no computador. Mostra também o comprimento somado dos trechos selecionados. |
| **Medir** | Abas **Distância**, **Área** e **Volume**, descritas na seção abaixo. |
| **Caixa de corte** | Arraste as alças para recortar o modelo. As faces coloridas mostram onde está cortando. **Ajustar à seleção** cria a caixa em volta dos objetos selecionados. Ao fechar o cartão, a caixa some e o corte continua. |
| **Raio-X** | Deixa transparente **só o que você escolher**: disciplinas, tipos ou objetos. A opacidade é ajustável. |
| **Revelar ocultos** | Mostra os objetos ocultos em destaque, estilo Revit, para escolher quais desocultar. |
| **Quantitativos** | Quantidades por disciplina e tipo, com metros de eletroduto e eletrocalha por bitola. Considera **só o que está na vista**: disciplinas e tipos ligados, sem os ocultos, só os isolados e só o que está dentro do corte. Um trecho cortado entra só com a parte de dentro. Exporta para planilha (CSV). |
| **QR code** | Gera o QR do modelo aberto, para copiar o link ou baixar a imagem. |
| **Tela cheia** | Esconde a barra do navegador. |

### Medir

**Distância**
- Dois cliques no modelo medem a distância entre os pontos.
- Com **Em sequência**, cada clique continua do último ponto.
- A lista mostra o **total**.

**Área**
- O 1º clique define o plano: horizontal no piso ou laje, ou o plano da parede clicada.
- Marque os cantos. A área e o lado aparecem ao vivo enquanto você desenha.
- Para fechar, clique no 1º ponto, dê duplo clique ou aperte **Enter**.
- **Shift** trava o lado em ângulo reto, **Backspace** desfaz o último ponto e **Esc** cancela.

**Volume**
- Desenhe a base como na área e feche.
- Depois mova o cursor (no celular, arraste o dedo) para cima e para baixo e clique para fixar a altura.
- A altura pode ser digitada depois na lista.

---

## Vistas e apresentação

Uma vista salva guarda:
- a câmera e o tipo de projeção;
- as disciplinas, os tipos e as cores;
- os objetos ocultos e os isolados;
- o raio-X e a caixa de corte.

Existem dois tipos de vista:
- **Vistas do projeto:** criadas por quem gerou o QR code, que entra com a conta Google em **Editar vistas do projeto**. Ficam salvas junto do modelo, no Google Drive, e aparecem para todo mundo que abrir aquele QR (somente leitura).
- **Minhas vistas:** qualquer pessoa pode salvar as suas. Elas ficam só no próprio aparelho.

**Apresentar** passa pelas vistas em tela cheia. No computador, use as setas ou a barra de espaço para avançar e **Esc** para sair.

---

## Para a equipe HEXA

### Publicar um modelo

Os modelos são publicados pela ferramenta **Juntar IFC + QR**, que fica neste mesmo site:

**https://hexa-engenharia.github.io/ifc/app/**

Não é preciso instalar nada: basta abrir o link no **Chrome** ou no **Edge** do computador, e todos usam sempre a última versão. Se quiser, use o ícone **Instalar** da barra de endereço para ter um atalho na área de trabalho. Também existe a extensão do Chrome, com as mesmas funções, mas ela precisa ser atualizada à mão.


1. Junte os IFCs das disciplinas. O arquivo unificado é salvo na pasta `NN-IFC UNIFICADO` do projeto.
2. Publique no Google Drive e gere o QR code (30 mm, com a logo) para a prancha.
3. Nas revisões, junte de novo e escolha **Atualizar um modelo já publicado**. O modelo vem marcado sozinho pelo nome do projeto; se não vier, cole o link do QR, solte a imagem do QR ou use **Escolher da lista**. **O QR já impresso continua valendo**.

> Dica de exportação no Revit: para o visualizador mostrar bitola e tamanhos reais, exporte o IFC com **"Exportar conjuntos de propriedades do Revit"** e **"Exportar quantidades base"** marcados.

### Atualizar este site

1. Substitua **`index.html`** e **`app.js`** neste repositório pela versão nova. Para atualizar a ferramenta Juntar IFC + QR, substitua a pasta **`app/`** inteira.
   - `web-ifc.wasm` só precisa ser trocado quando a versão do web-ifc mudar.
   - **Nunca substitua o `config.js`**, que tem a chave de acesso ao Google Drive.
2. Aguarde 1 a 2 minutos para o GitHub Pages publicar.
3. Para conferir, abra o site e passe o mouse sobre a logo. A versão aparece no formato `AAAA-MM-DD.HHMM`. O `app.js` é carregado com a versão no endereço, então o navegador não reaproveita o app antigo do cache.

### Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | Página do visualizador (layout e estilos). |
| `app.js` | O visualizador. É gerado pelo build a partir do código-fonte, então não edite este arquivo diretamente. |
| `web-ifc.wasm` | Leitor de IFC (WebAssembly). |
| `config.js` | Chave de API do Google Drive, restrita à Drive API e ao domínio deste site. |
| `app/` | Ferramenta Juntar IFC + QR (juntar, publicar no Drive e gerar o QR). Gerada pelo build: não edite à mão. |

### Parâmetros do link

| Parâmetro | Uso |
|---|---|
| `?d=<ID>` | Abre o arquivo `.ifc`/`.ifczip` com esse ID no Google Drive (compartilhado como "qualquer pessoa com o link"). |
| `?u=<URL>` | Abre um `.ifc`/`.ifczip` de um endereço público (o servidor precisa permitir CORS). |

### Login do Google (ferramenta e vistas do projeto)

Para a ferramenta (`app/`) e o botão **Editar vistas do projeto** funcionarem, o Client ID OAuth do projeto no Google Cloud precisa de duas coisas:
- `https://hexa-engenharia.github.io` em **Origens JavaScript autorizadas**;
- a tela de consentimento **Em produção**, ou cada pessoa cadastrada como **usuário de teste**.

---

## Compatibilidade

Funciona em navegadores atuais com WebGL:
- **Celular:** Chrome e Safari (Android e iPhone).
- **Computador:** Chrome, Edge, Firefox e Safari.

Modelos muito grandes podem demorar mais para abrir em celulares mais simples.

## Tecnologia e licenças

Site estático: não há servidor nem banco de dados, e o modelo é processado no navegador de quem abre.

Bibliotecas de terceiros usadas:
- [three.js](https://threejs.org) — MIT
- [web-ifc](https://github.com/ThatOpen/engine_web-ifc) — MPL-2.0
- [fflate](https://github.com/101arrowz/fflate) — MIT
- [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) — MIT
- [jsQR](https://github.com/cozmo/jsQR) — Apache-2.0

© HEXA Engenharia. Uso interno e dos clientes da HEXA.
