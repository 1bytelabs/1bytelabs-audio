# Origem da migração

Este repositório foi iniciado com os arquivos do **1Byte Labs Audio 0.4.1**, versão testada originalmente no repositório Transmitter.

- Repositório original: https://github.com/1bytelabs/1bytelabs-transmitter
- Snapshot de origem: https://github.com/1bytelabs/1bytelabs-transmitter/commit/9b515458b8fca7b51a4097809353f14785b13207
- Desenvolvimento original: https://github.com/1bytelabs/1bytelabs-transmitter/pull/8
- Validação original 0.4.1: https://github.com/1bytelabs/1bytelabs-transmitter/actions/runs/39474101707

## Histórico

Os commits anteriores permanecem no repositório original. Este repositório começa com um snapshot dos componentes Audio e registra essa referência; ele não importa nem reescreve os SHAs do histórico antigo. O Transmitter não é removido nem alterado pela migração.

## Compatibilidade

A migração reorganiza caminhos de código e configuração de build. O processamento de áudio, os formatos de estado, o ID VST2 `1bAu`, o ID da fonte OBS `onebyte_ndi_audio`, o AppId do instalador e os nomes dos binários permanecem iguais aos da 0.4.1.

## Runtime NDI

Os headers NDI são copiados sem alteração. O CI continua obtendo o runtime x64 do arquivo histórico `Zosma-Transmitter-v0.3.1-beta-Windows-x64.zip`, no release `v0.3.1-beta` do Transmitter, exatamente como no build validado 0.4.1. Isso é uma origem de distribuição do runtime de terceiro; o código do aplicativo Transmitter não é usado na compilação Audio.

As interfaces do NDI, o runtime e o ABI VST2 mantêm seus próprios avisos e termos. Consulte `THIRD_PARTY_NOTICES.md`, os headers e `plugins/obs/LICENSE`.
