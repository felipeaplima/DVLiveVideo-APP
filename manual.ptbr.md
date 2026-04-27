# 📘 DV Live Video – Manual do Usuário

## O que é este aplicativo?

Este aplicativo foi criado para ajudar usuários do DataVolley 4 a fazer análise de vídeo em tempo real durante as partida. No aplicativo oficial do DV4 você tem acesso apenas aos últimos 5 rallies. Com esta ferramenta, seu arquivo de scout (`.dvw`) e o arquivo de captura de vídeo (`.mp4`) permitem buscar qualquer rali, aplicar filtros e compartilhar a análise com todos na sua rede.

## Como funciona

O aplicativo monitora continuamente o arquivo de scout (atualizado durante a partida) e o associa ao vídeo capturado ou a uma URL de captura de terceiros. Quando usado com a captura (`.mp4`), o aplicativo gera uma nova transmissão HLS ao vivo (HTTP Live Streaming) que pode ser assistida em qualquer navegador na rede, permitindo retroceder (DVR), para que você possa reproduzir qualquer rally desde o início da partida.

> **📌 Dica:** Para acessar o arquivo `.dvw`, é recomendado usar o **backup automático em uma unidade externa** disponível no DV4 (*Opções de Scout → Segurança do Scout*). Se seu notebook tiver um leitor de cartão SD, use-o como disco de backup para melhor desempenho.

## Requisitos mínimos

- **VLC Player** instalado no notebook – o aplicativo desktop usa os plugins do VLC.
- **ffmpeg.exe** colocado na mesma pasta do aplicativo `.exe`.
- Se você quiser capturar a transmissão em outro computador que não seja o mesmo do scout, precisará de um aplicativo para criar uma transmissão secundária iniciando ao mesmo tempo que a captura do DV4, ou do aplicativo **scoutfile-sender da Science Untangled** (fornecido no .rar) que compartilhará seu arquivo de scout na sua rede.
- Algumas opções para usar outra fonte de transmissão na sua rede incluem: 
  [**VolleyStation Streamer**](https://storage.volleystation.com/downloads/software/VolleyStation-Streamer-win-latest.exe), OvenMediaEngine (OME), MediaMTX, entre outros.

## Primeiros passos

Ao receber o `.rar`, descompacte todos os arquivos na mesma pasta em seu disco:

- **Certifique-se de que o VLC está instalado no seu notebook;**
- **Você pode testar o aplicativo com dados de alguma partida já finalizada (`.dvw` e `.mp4`);**
- **Você precisará de espaço livre para arquivos de vídeo temporários; recomenda-se ter até 10GB, pois seu arquivo `.mp4` principal será duplicado duas vezes para torná-lo acessível no cliente web e no aplicativo desktop!!**

---

## Iniciando o aplicativo e escolhendo a fonte de vídeo

> **📌 Atenção:** Na primeira abertura deste aplicativo, pode levar mais de 1 minuto para carregá-lo!!!

Execute o `DVLiveVideo.exe` na pasta descompactada. Depois você pode definir este `.exe` como atalho na barra de tarefas e no menu iniciar.

Você pode iniciar o aplicativo em três modos:

- **Desktop + Servidor Web** – interface desktop completa + player web.
- **Somente desktop** – apenas a janela local PyQt5 (sem servidor web).
- **Somente servidor web** – apenas a interface web (sem janela desktop).

Após escolher o tipo de execução, você precisa escolher uma das duas fontes de vídeo:

### 1. Arquivo de captura do scout do DV (`.mp4`)

Na segunda caixa de diálogo, selecione o arquivo `.mp4` parcial gerado pelo DV4 e o arquivo de scout `.dvw` correspondente. Cada vez que o arquivo de scout é atualizado, o aplicativo copia o vídeo parcial e o associa ao arquivo de scout, permitindo a busca de ralis. Para o servidor web, a cada 2 atualizações de rally o aplicativo regenera a transmissão HLS para todos na rede. Essa frequência de atualização pode ser modificada conforme a qualidade do processador e da rede.

### 2. Uma transmissão existente na mesma rede (playlist `.m3u8`)

Por enquanto, a URL de transmissão nativa do DV4 não pode ser usada porque não permite busca reversa. No entanto, você pode usar qualquer outra transmissão HLS (ex: VS Stream). Importante: mesmo neste modo, o arquivo de scout `.dvw` deve ser associado a uma captura de vídeo para gerar os timestamps. Se a transmissão secundária não estiver perfeitamente sincronizada, use o campo **offset** (em segundos) para alinhá-la com a captura principal.

---

## Escolhendo a fonte do `.dvw`:

### 1. Scout e captura de vídeo no mesmo notebook

Basta selecionar o arquivo de backup que será atualizado automaticamente pelo DV4.

### 2. Arquivo de scout compartilhado pela rede com o aplicativo scoutfile-sender

Obtenha a URL do `.dvw` do notebook onde você fará o scout da partida.

---

## Usando o Aplicativo

### Interface Desktop

- **Play/Pause** – botão ou `Espaço`.
- **Avançar +5s / Retroceder -5s** – botões ou `←` `→` (setas).
- **Avançar +2s / Retroceder -2s** – teclas `-` e `+`.
- **Offset** – ajuste a compensação de tempo (segundos positivos ou negativos) aplicada ao clicar em um rali.
- **Filtros** – filtre ralis por set, rotação de casa/fora e busque com curinga `_` (ex: `a__S_#` encontra saques com avaliação '#').
- **Favoritos** – clique na estrela (ou pressione `F`) para marcar um rali. Use a caixa "Mostrar apenas favoritos".
- **Tela cheia** – botão ou `ESC` para sair.
- **Modo escuro/claro** – botão 🌙/☀️.

### Interface Web (Navegador)

Acesse o player web em `http://[ip-do-servidor]:5000`. Recursos incluem:

- Mesmo player de vídeo com **botões de avanço/retrocesso** (2s, 5s) e controle de offset.
- Filtros, favoritos e busca com curinga idênticos à versão desktop.
- Botão **Forçar atualização HLS** – regenera manualmente os segmentos da transmissão se o player congelar.
- Atalhos de teclado: `Espaço` (play/pause), `←/→` (avançar/retroceder ±2s), `Enter` (ir para o rali selecionado), `F` (favorito).

## Exemplos de busca

Use o sublinhado `_` como curinga para exatamente um caractere. Exemplos:

- `a__S_#` → encontra saques (`S` como 4º caractere) com avaliação `#`.
- `*__SQ#` → encontra saques viagens (`SQ`) com `#`.
- `a05_` → encontra códigos começando com `a05` e qualquer 4º caractere.

## Solução de problemas

- **Sem vídeo no player web** – Verifique se o `ffmpeg.exe` está presente e se o arquivo snapshot existe na pasta `data/stream`. Tente clicar em "Forçar atualização HLS".
- **VLC não encontrado** – Instale o VLC Player (64‑bits) e reinicie o aplicativo.
- **Lista de ralis não atualiza** – Verifique se o arquivo `.dvw` está sendo escrito pelo DV4. Use o botão "Recarregar" na interface web.
- **Porta 5000 já em uso** – Altere a porta no aplicativo, entrando em contato com o Ori.

---

Desenvolvido por Felipe Lima (Ori) 🇧🇷 – © 2026