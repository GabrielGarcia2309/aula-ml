# Relatório de Comparação de Modelos (`chamados-r1` vs. `chamados-r2`)

## 1. Alteração Realizada
Na versão `dados-v1` (`chamados-r1`), o chamado `006` (`bloqueio de acesso`) estava rotulado erroneamente como `comum`. Na branch `correcao-rotulo` (`dados-v2`), o rótulo do ID `006` foi corrigido para `urgente`, mantendo `data/split.csv` inalterado.

## 2. Tabela de Métricas (Partição de Teste Fixa)

| Métrica | `chamados-r1` (`dados-v1`) | `chamados-r2` (`dados-v2`) | Variação |
| :--- | :---: | :---: | :---: |
| **Acurácia** | 0.75 (3/4) | 1.00 (4/4) | +0.25 |
| **Recall (`urgente`)** | 0.50 (1/2) | 1.00 (2/2) | +0.50 |
| **Recall (`comum`)** | 1.00 (2/2) | 1.00 (2/2) | 0.00 |
| **Suporte (`urgente` / `comum`)** | 2 / 2 | 2 / 2 | Fixo |

## 3. Hashes Verificados no Clone Limpo (`modelo-r1`)
- **Commit (`HEAD`):** `ad04d604ee51b7ce4f8f58fe9f016445a0f89777`
- **`data/chamados.csv` (`dataset_sha256`):** `bc3fd86a3a5f598841a58839a9726d901fa7e8361ffe79c5b43873ad8a1328ac`
- **`data/split.csv` (`split_sha256`):** `2ef820171c1a4625fe216e6da67c7c8dcf9d97a08288c0239cd23f1a6961d981`
- **`models/model.json` (`artifact_sha256`):** `72a3a67936139a3473838a6dcfa7aae1acb4c23467be1ef1056d51d485b94840`

## 4. Decisão
**ACEITAR** o modelo `chamados-r2` (`modelo-r2`). A correção aumentou o recall de chamados urgentes de 0.50 para 1.00 sem reduzir o recall de chamados comuns (mantido em 1.00), utilizando exatamente a mesma partição de teste.
