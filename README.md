# IOA Datasets

Datasets for Intelligence Orchestration Architecture (IOA) research.

## Large Files (Split)

`llm_embeddings_ioa_pilot.h5` is split into multiple parts due to GitHub file size limits.

### Reassembly Instructions

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

## Dataset Descriptions

| File | Size | Description |
|------|------|-------------|
| `llm_texts_ioa_pilot.parquet` | 0.4 MB | 10,500 persona-conditioned texts (7 personas) |
| `llm_embeddings_ioa_pilot.h5` | 114 MB | DistilBERT-base-uncased embeddings (768-dim) |
| `all_minilm_l6_v2_embeddings.h5` | 14.5 MB | all-MiniLM-L6-v2 embeddings (384-dim) |
| `synonym_attack_results.npz` | 1.1 MB | 400 samples (200 clean, 200 adversarial) |
