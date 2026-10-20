# 1Byte Labs Audio 0.4.1 — VST2 (instalação manual)

Este pacote contém o plugin de envio e recepção de áudio NDI em formato VST2 de 64 bits e seu runtime NDI, para uso em hosts compatíveis no Windows x64.

1. Feche os programas que usam o plugin.
2. Extraia o conteúdo deste ZIP em C:\Program Files\VSTPlugins\1Byte Labs ou na sua pasta de VST2.
3. Mantenha **1Byte Labs Audio.dll** e **Processing.NDI.Lib.x64.dll** juntas.
4. Abra seu programa compatível com VST2 de 64 bits, atualize a lista de plugins se necessário e adicione **1Byte Labs Audio**.

REAPER e o filtro VST 2.x do OBS são exemplos testados. No OBS, o filtro precisa estar em uma fonte de áudio ativa.

Na mesma janela, escolha **Enviar** ou **Receber**. Em Receber, selecione a fonte NDI da lista. O fader controla o volume do áudio enviado ou recebido.

Para adicionar uma fonte diretamente em **Fontes → +** do OBS, use o instalador ou o pacote **OBS-Manual-x64.zip**. Esses arquivos não fazem parte deste ZIP VST2.

Site: https://1bytelabs.com.br
