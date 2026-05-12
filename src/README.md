## Codigo fonta

O código fonte está em src/app.py

## Estrutura

```
src/
├── app.py              # Aplicação principal (Streamlit)
```

## ferramentas utilizadas

```
ollama
gpt-oss
python 3.14
streamlit
huggingface
```

## Como Rodar

```bash
# Instalar dependências
pip install streamlit pandas requests huggingface_hub fsspec

#garantir que o ollama está configurado na porta correta
ollama serve

# Rodar a aplicação
streamlit run .\src\app.py
```
