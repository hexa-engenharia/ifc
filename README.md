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
| **Arquivo do seu aparelho** | Abra o site e arraste o arquivo para a janela, ou toque em **Abrir arquivos** (`.ifc`, `.ifczip` ou `.zip`). Veja [Usar como programa](#usar-como-programa). |

> **Privacidade:** um arquivo aberto do seu aparelho é lido só no seu navegador e não é enviado para lugar nenhum. Os modelos dos QR codes são lidos, somente para leitura, do Google Drive onde a HEXA os publicou.

---

## Usar como programa (HEXA-IFC)

Aberto sem link (só `https://hexa-engenharia.github.io/ifc/`), o site vira o **HEXA-IFC**: uma tela principal com três cartões e, no topo, a barra **UNIFICAR IFC | VISUALIZADOR | SEPARAR IFC**. Trocar de aba não perde nada (modelo aberto, lista do Unificar, arquivos do Separar). Nada é enviado para a internet nem salvo no Drive, a não ser ao publicar.

- **Unificar IFC**: junta as disciplinas num IFC unificado, salva na pasta do projeto, publica no Drive e gera o QR, em passos que vão aparecendo (1 arquivos › 2 unificar › 3 publicar e QR). O QR de um link qualquer fica no ícone de QR do topo.
- **Visualizador**: o que está descrito abaixo.
- **Separar IFC**: veja [Separar IFC](#separar-ifc).
- No celular aparece só o Visualizador (Unificar e Separar precisam do Chrome/Edge no computador).

- **Arrastar** para a janela: um ou vários `.ifc`, um `.ifczip`/`.zip` (com um ou vários IFCs dentro) ou uma **pasta do projeto** inteira. Vários arquivos são juntados na hora, já separados por disciplina (o nome da disciplina vem da pasta ou do código no nome: `04-FORÇA`, `FOR`, `AUT`…).
- **Pasta do projeto**: entram só os IFCs das disciplinas, na revisão mais nova. Ficam de fora as pastas `OBSOLETO`, `OLD` e `BACKUP`, a pasta do IFC unificado e arquivos `UNIFICADO`.
- **Com um modelo aberto**, arrastar mais arquivos pergunta: **Juntar com o que está aberto** ou **Abrir só estes**. Ao juntar, uma revisão nova troca a velha da mesma disciplina (aparece "FORÇA: R00 → R01").
- **Botões**: **Abrir arquivos**, **Abrir pasta** (Chrome e Edge no computador) e, no topo, o ícone de pasta volta para a tela inicial.
- **Recentes** (Chrome e Edge no computador): os últimos 8 arquivos ou pastas abertos. Ao clicar, o navegador pede permissão para ler de novo; se o arquivo mudou de lugar, ele sai da lista.
- **Instalar**: o botão **Instalar** da tela inicial (ou o ícone na barra de endereço do Chrome/Edge) cria o **HEXA-IFC** no menu Iniciar e na área de trabalho. Depois de instalado ele abre em janela própria, funciona **sem internet** e aparece em **Abrir com** ao clicar com o botão direito num `.ifc` (dá para abrir vários de uma vez).
- **Publicar / gerar QR** (ícone de QR no topo, Chrome e Edge no computador): leva os arquivos abertos (e a pasta, se você abriu uma pasta) para a aba **Unificar IFC**. Lá é só Unificar › Salvar na pasta › Publicar › QR.
- **Abrir de novo é rápido**: a geometria de um arquivo já aberto fica guardada no navegador; reabrir o mesmo arquivo (mesmo nome, tamanho e data) pula a parte demorada. **Limpar cache** na tela principal apaga essa cópia.
- **Minhas vistas** ficam guardadas pelo nome do modelo aberto.
- Num link de QR (`?d=`), arrastar um arquivo do aparelho troca para ele; as vistas do projeto e o QR daquele link saem da tela.

---

## Separar IFC

Deixa IFCs pesados (arquitetura, estrutura, hidráulica…) leves para vincular no Revit. É o `dividir_ifc.py` (o .bat) dentro do HEXA-IFC, com o mesmo resultado. **O arquivo original nunca é alterado.** Chrome ou Edge no computador.

1. Arraste os IFCs no cartão **Separar IFC** (ou na própria aba). Cada arquivo vira uma aba; **+ arquivo** acrescenta outros.
2. **Limpeza (automática)**: mostra o que saiu (mobiliário, louças, perfis de esquadria, montantes de fachada…), o tamanho antes → depois e quantas peças tiveram a malha simplificada. **ajustar ▾** abre as opções (manter grupos ou classes, remover classes ou por nome, tolerância, sem simplificar, com propriedades, pasta de saída).
3. **Como gerar**: **Só limpar** (um arquivo `_LIMPO`), **Um por pavimento** (`_01_TERREO`, `_02_…`) ou **Grupos** (nome livre e cor por grupo, "+ grupo"; cada pavimento escolhe o seu grupo). As caixinhas valem em todos os modos: pavimento desmarcado fica de fora. Pavimentos seguidos desmarcados de nome parecido (TIPO 2 … TIPO 24) aparecem numa linha só, que se abre.
4. **Usar nos outros N arquivos** copia o modo, os grupos e as marcações para os outros arquivos, casando os pavimentos pela cota. O que não casar fica listado em amarelo para escolher à mão.
5. À direita, a **prévia 3D** do modelo já limpo: pavimentos marcados na cor do grupo, os outros apagados. Clicar num elemento marca ou desmarca o pavimento dele. Ao voltar para o Visualizador, o modelo que estava aberto volta como estava.
6. **Gerar arquivos**: na primeira vez o navegador pergunta a pasta (abre ao lado do arquivo); os arquivos vão para **`IFC_DIVIDIDO`** dentro dela, com o `_RELATORIO.txt` (o que saiu, por classe, conferindo que nada sumiu). Se um arquivo de saída estiver aberto no Revit, ele avisa qual e grava os outros.

---

## Modelos grandes (Abrir leve)

Arquivos IFC acima de **100 MB** abrem **leves**: o visualizador deixa de fora, por enquanto, o que pesa e quase nunca importa para instalações — perfis e ferragens de esquadria, montantes de fachada, louças e metais, mobiliário, eletrodomésticos, acabamentos, vegetação, pessoas e veículos (as mesmas regras do *Separar IFC*).

- Um aviso no topo diz o que ficou de fora. Clique numa etiqueta (por exemplo **Louças e metais**) para carregar só aquele grupo, ou em **Mostrar tudo** para carregar o resto. Não precisa reabrir: o que você já ligou, desligou, isolou ou deixou em raio-X continua igual.
- **Nada some do arquivo**: o IFC não é alterado. É só o que vai para a tela.
- Para abrir sempre completo, acrescente `&completo` ao link (ou `?completo` na página do programa).
- Enquanto você gira ou dá zoom num modelo muito pesado, o visualizador desenha só as peças maiores e em resolução um pouco menor; ao parar, tudo volta na hora.
- No computador com placa de vídeo dedicada (NVIDIA/AMD), configure o Windows para usar essa placa no Chrome/Edge: **Configurações › Sistema › Tela › Gráficos** › escolha o navegador › **Alto desempenho**.

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
| **Ver em AR** | No celular: mostra o modelo **em tamanho real pela câmera**, no próprio local. Veja a seção abaixo. |
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

## Ver em AR (realidade aumentada)

Mostra o projeto **em tamanho real, sobreposto à câmera do celular, no próprio local**. Você anda e aponta, e o modelo fica no lugar. Feito para apresentar ao cliente: a precisão é de alguns centímetros.

O botão (cubo com cantos) só aparece em celular com AR:
- **Android:** Chrome, em aparelhos com o "Google Play Services para RA".
- **iPhone:** Safari ou Chrome.

### 1. Preparar (antes de chegar no local, ou lá mesmo)

1. Abra o modelo pelo QR e deixe na tela **só o que quer mostrar** (disciplinas, tipos, ocultos).
2. Se o modelo for grande, use a **caixa de corte** para ficar só com a área da visita. Se passar do limite, aparece: *"A área é grande demais para o AR no celular…"*.
3. Toque em **Ver em AR**. O visualizador vai para a vista de cima.
4. Escolha o **pavimento**. Ele define a altura do piso.
5. Toque no **ponto A** e no **ponto B** da planta. Escolha dois lugares fáceis de achar no local, como um canto de parede, um pilar ou uma porta, a pelo menos 1 m um do outro.
6. Os pontos ficam guardados neste celular para este modelo. Na próxima vez já vêm marcados.
7. Toque em **Continuar**.

### 2a. Android

1. A câmera abre com um **alvo** (anel branco) que segue o chão. Se ele não aparecer, aponte para o chão e mova o celular devagar.
2. Ponha o alvo **exatamente sobre o ponto A** real e toque na tela. Depois faça o mesmo com o **ponto B**.
3. O modelo aparece encaixado. Se a distância A–B no local não bater com a do projeto, aparece um aviso: confira os pontos ou toque em **Refazer pontos**.
4. Ande e aponte. Toque num objeto para ver nome, tipo e bitola.
5. Use **Ajustar** para corrigir com as setas: mover 5 cm (frente, trás e lados, conforme para onde o celular aponta), girar 1° e subir ou descer 2 cm.
6. Toque em **Sair** para voltar ao visualizador como estava.

### 2b. iPhone

1. O visualizador prepara o arquivo ("Preparando o modelo para o AR…"), o que leva alguns segundos, e abre o **AR da Apple**. Se não abrir sozinho, toque em **Abrir no AR**.
2. Aponte para o chão até o modelo aparecer. O **disco vermelho** é o ponto A e o **pino azul** é o ponto B.
3. Arraste com um dedo para levar o disco vermelho ao ponto A real. Depois gire com dois dedos até o pino azul ficar sobre o ponto B. A escala fica travada em tamanho real.
4. Para sair, feche o AR da Apple.

### Dicas

- Funciona melhor com boa luz e com piso ou paredes que tenham textura. Piso liso e brilhante e paredes brancas atrapalham.
- Em áreas grandes o rastreamento pode "escorregar" alguns centímetros. Use **Ajustar** ou refaça os pontos.
- O modelo aparece por cima de tudo, o que permite "ver dentro da parede".
- O AR precisa de um IFC em **metros**. Os modelos publicados pela ferramenta já saem assim.

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

1. Substitua **`index.html`**, **`app.js`**, **`juntar.js`**, **`geometria.js`**, **`separar.js`**, **`sw.js`** e **`manifest.webmanifest`** neste repositório pela versão nova (sempre todos juntos) e a pasta **`app/`** inteira (o Unificar).
   - **Para testar antes de trocar o site**: suba a pasta **`teste/`** (e a pasta `app/`) e abra `https://hexa-engenharia.github.io/ifc/teste/` (mesmo programa, sem instalar, usando o `config.js` do site). Quando estiver bom, troque os arquivos principais.
   - `web-ifc.wasm` só precisa ser trocado quando a versão do web-ifc mudar; a pasta `icons/`, só quando mudar.
   - **Nunca substitua o `config.js`**, que tem a chave de acesso ao Google Drive.
2. Aguarde 1 a 2 minutos para o GitHub Pages publicar.
3. Para conferir, abra o site: a versão aparece no rodapé da tela principal, no formato `AAAA-MM-DD.HHMM`. O `app.js` é carregado com a versão no endereço, então o navegador não reaproveita o app antigo do cache. Quem instalou o programa recebe a versão nova na próxima vez que abrir com internet.

### Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | Página do visualizador (layout e estilos). |
| `app.js` | O visualizador. É gerado pelo build a partir do código-fonte, então não edite este arquivo diretamente. |
| `juntar.js` | Junta vários IFCs no navegador quando o visualizador é usado como programa. Gerado pelo build. |
| `geometria.js` | Gera a geometria em segundo plano, dividida entre os núcleos do processador. Gerado pelo build. |
| `separar.js` | Motor do Separar IFC (limpar, simplificar malhas, dividir por pavimento, relatório). Gerado pelo build. |
| `sw.js` | Faz o programa instalado abrir sem internet. Gerado pelo build. |
| `manifest.webmanifest`, `icons/` | Nome, ícone e tipos de arquivo do programa instalado (HEXA-IFC). |
| `web-ifc.wasm` | Leitor de IFC (WebAssembly). |
| `config.js` | Chave de API do Google Drive, restrita à Drive API e ao domínio deste site. |
| `app/` | Unificar IFC (juntar, publicar no Drive e gerar o QR), usado dentro do HEXA-IFC. Gerado pelo build: não edite à mão. |
| `teste/` | Versão de teste do visualizador (opcional), para conferir uma atualização antes de trocar o site. |

### Parâmetros do link

| Parâmetro | Uso |
|---|---|
| `?d=<ID>` | Abre o arquivo `.ifc`/`.ifczip` com esse ID no Google Drive (compartilhado como "qualquer pessoa com o link"). |
| `?u=<URL>` | Abre um `.ifc`/`.ifczip` de um endereço público (o servidor precisa permitir CORS). |
| `&completo` | Abre o modelo completo mesmo acima de 100 MB (sem o Abrir leve). |
| `&medir` | Mostra no canto o tempo de cada etapa da abertura e quantos triângulos o modelo tem (para diagnóstico). |

### Login do Google (ferramenta e vistas do projeto)

Para a ferramenta (`app/`) e o botão **Editar vistas do projeto** funcionarem, o Client ID OAuth do projeto no Google Cloud precisa de duas coisas:
- `https://hexa-engenharia.github.io` em **Origens JavaScript autorizadas**;
- a tela de consentimento **Em produção**, ou cada pessoa cadastrada como **usuário de teste**.

---

## Compatibilidade

Funciona em navegadores atuais com WebGL:
- **Celular:** Chrome e Safari (Android e iPhone). **Ver em AR**: Chrome no Android com ARCore; Safari ou Chrome no iPhone.
- **Computador:** Chrome, Edge, Firefox e Safari. **Instalar como programa**, **Abrir pasta**, **Recentes** e abrir pelo duplo clique: Chrome e Edge.

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
