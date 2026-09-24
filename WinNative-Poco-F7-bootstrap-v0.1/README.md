# WinNative POCO F7 — bootstrap v0.1

Primeira etapa compilável do stack F7.

## Gera

- `Box64-F7-0.4.5-51b5f8cfc.wcp`
- `WOWBox64-F7-0.4.5-51b5f8cfc.wcp`
- `FEXCore-F7-2609-arm64ec.wcp`

## Base

- Box64: `51b5f8cfc2234c45238bbb90f6e23ff6f2ca0fd6`
- FEXCore: `FEX-2609` / commit registrado como `395b132f346b1a45def246d10c52245edba1ef02`
- LLVM-MinGW: `20260602`
- Android API: `28`

## Política F7

O build inicial prioriza estabilidade mensurável:

- `ARMv8.2-A`
- `cortex-a720` para tuning
- Box64 Android em `-O2` em vez de elevar direto para `-O3`
- FEXCore em `-O3`, alinhado ao caminho de build utilizado em builds FEX/Proton modernas
- FEX profiler desligado
- FEX telemetry desligada
- LTO desligado no baseline

Essas flags ainda precisam de A/B test no aparelho. O pacote não declara ganho de FPS até ser medido no POCO F7.

## Como disparar

Ao colocar o arquivo `.github/workflows/build-core-f7.yml` na branch `main`, o workflow roda no primeiro push. Depois ele também aparece em **Actions → Build F7 Core Runtimes → Run workflow**.

Os WCP ficam em **Actions → execução concluída → Artifacts**.
