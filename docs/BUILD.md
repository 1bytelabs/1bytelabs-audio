# Compilar no Windows x64

Pré-requisitos: Git, CMake 3.28+, Visual Studio 2022 com C++ e Windows SDK. A fonte OBS usa o SDK oficial libobs 31.1.1; o teste de integração usa o runtime OBS 32.2.2. Não é necessário instalar o OBS para compilar o VST2.

## VST2

```powershell
cmake -S plugins/vst2 -B build-vst2 -A x64
cmake --build build-vst2 --config Release --parallel
ctest --test-dir build-vst2 -C Release --output-on-failure
```

Os testes usam um runtime NDI simulado que nunca deve ser distribuído. O workflow troca esse fixture pelo runtime real antes do empacotamento.

## Testes portáveis de fila e ganho

```sh
cmake -S plugins/vst2 -B build-portable -DONEBYTE_PORTABLE_TESTS_ONLY=ON
cmake --build build-portable
ctest --test-dir build-portable --output-on-failure
```

Esses testes não significam suporte do plugin ao Linux ou macOS.

## Fonte OBS, NDI real e instalador

O procedimento completo e os comandos fixados estão em `.github/workflows/build-windows.yml`: bootstrap do SDK oficial pelo obs-plugintemplate, build de `plugins/obs`, testes NDI reais e do libobs, empacotamento e Inno Setup 6.

Para configurar `plugins/obs` manualmente, forneça `CMAKE_PREFIX_PATH` com a instalação Development do SDK libobs e suas dependências. Para compilar o instalador, defina `StageDir` e `OutputDir` ao executar `packaging/windows.iss`.

O download contém exatamente três arquivos: instalador, VST2-Manual-x64.zip e OBS-Manual-x64.zip. O workflow verifica os conteúdos e testa a instalação e desinstalação de cada combinação de componentes.
