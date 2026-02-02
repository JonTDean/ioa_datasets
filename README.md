# IOA Datasets

Datasets for Intelligence Orchestration Architecture (IOA) research.

## Large Files (Split)

Due to GitHub's 25MB file size limit, some files are split into parts.

### llm_embeddings_ioa_pilot.h5 (114 MB → 6 parts)

**Linux/macOS:**
```bash
cat llm_embeddings_ioa_pilot.h5.part* > llm_embeddings_ioa_pilot.h5
```

**Windows (PowerShell):**
```powershell
Get-Content llm_embeddings_ioa_pilot.h5.part* -Encoding Byte -ReadCount 0 | Set-Content llm_embeddings_ioa_pilot.h5 -Encoding Byte
```

**Python:**
```python
with open('llm_embeddings_ioa_pilot.h5', 'wb') as outfile:
    for i in range(6):
        with open(f'llm_embeddings_ioa_pilot.h5.part{i:02d}', 'rb') as infile:
            outfile.write(infile.read())
```

### knn_attack_results.pkl (33 MB → 2 parts)

**Python:**
```python
with open('knn_attack_results.pkl', 'wb') as outfile:
    for i in range(2):
        with open(f'knn_attack_results.pkl.part{i:02d}', 'rb') as infile:
            outfile.write(infile.read())
```

## Dataset Descriptions

### Core Embeddings
| File | Size | Description |
|------|------|-------------|
| `llm_texts_ioa_pilot.parquet` | 0.4 MB | 10,500 persona-conditioned texts (7 personas) |
| `llm_embeddings_ioa_pilot.h5` | 114 MB | DistilBERT-base-uncased embeddings (768-dim) |
| `all_minilm_l6_v2_embeddings.h5` | 14.5 MB | all-MiniLM-L6-v2 embeddings (384-dim) |

### Attack Datasets
| File | Size | Description |
|------|------|-------------|
| `synonym_attack_results.npz` | 1.1 MB | 400 synonym-substitution attack samples |
| `paraphrase_embeddings.npy` | 0.6 MB | 200 paraphrase attack embeddings |
| `pgd_attack_results.npz` | 0.25 MB | PGD evasion attack results |
| `knn_attack_results.pkl` | 33 MB | AG News k-NN attack embeddings (3,200 samples) |

### Analysis Results
| File | Size | Description |
|------|------|-------------|
| `bootstrap_shifts_data.npz` | 0.04 MB | Centroid-shift bootstrap distributions |
| `attack_classification_features.npz` | 0.02 MB | k-NN + reconstruction features for attack classification |
