# 1Byte Labs Audio 0.4.1

Plugin VST2 para envio e recepção de áudio NDI em hosts compatíveis, com fonte nativa para OBS Studio. Windows x64.

## Escolha como instalar

- **1ByteLabs-Audio-0.4.1-Setup-x64.exe**: escolha VST2, fonte OBS ou ambos. O instalador tenta localizar o OBS e permite escolher outra instalação, incluindo portable.
- **1ByteLabs-Audio-0.4.1-VST2-Manual-x64.zip**: somente o VST2, runtime NDI e avisos. Extraia na pasta de VST2, por padrão C:\Program Files\VSTPlugins\1Byte Labs.
- **1ByteLabs-Audio-0.4.1-OBS-Manual-x64.zip**: somente os arquivos da fonte OBS. Extraia na raiz do OBS instalado ou portable, mantendo as pastas obs-plugins e data.

Feche os programas que usam o plugin e o OBS antes de atualizar. O runtime NDI já acompanha os componentes.

## Receber diretamente no OBS

Requer OBS 31.1+ x64. Em **Fontes → + → 1Byte Labs Audio**, use **Atualizar fontes**, selecione o transmissor e confirme. Não precisa de microfone ou filtro VST nesse fluxo. O volume aparece nas propriedades da fonte e no mixer do OBS.

## Usar o VST2

Adicione **1Byte Labs Audio** em um programa de 64 bits compatível com plugins VST2 e escolha **Enviar** ou **Receber** na mesma janela.

REAPER e o filtro VST 2.x do OBS são exemplos testados. No OBS, o filtro precisa estar em uma fonte de áudio ativa; para receber sem essa dependência, use a fonte nativa.

Em Enviar, o fader altera somente o sinal NDI. Em Receber, o áudio selecionado substitui a entrada. Desligar a recepção deixa a saída silenciosa; usar o bypass do host volta a passar a entrada local.

O modo, fonte, ganho e estado são armazenados pelo projeto ou pela coleção de cenas do host. Uma fonte ou instância nova começa com as opções padrão. Projetos antigos 0.2.x restauram em Enviar com seu ganho e número de fonte.

## Diagnóstico e informações

O botão **Diagnóstico NDI** do VST2 mostra a conexão e o processamento do host. Na mensagem, Ctrl+C copia o relatório.

O link **1bytelabs.com.br** abre o site no navegador ao ser clicado. No OBS, fica somente nas propriedades da fonte.

Site: https://1bytelabs.com.br

## Código e compilação

- `plugins/vst2`: plugin Enviar/Receber para hosts compatíveis com VST2 de 64 bits.
- `plugins/obs`: fonte nativa do OBS.
- `shared`: backend NDI, filas de áudio, ganho e testes compartilhados.
- `packaging/windows.iss`: instalador com componentes opcionais.
- `third_party/ndi/include`: cabeçalhos do NDI SDK.
- `.github/workflows/build-windows.yml`: compilação, testes e empacotamento.

A aba **Actions** gera o instalador e os dois ZIPs manuais. Consulte [docs/BUILD.md](docs/BUILD.md) para compilar e [docs/ORIGIN.md](docs/ORIGIN.md) para a origem da migração. A implementação atual atende Windows x64; macOS ainda não está implementado.
