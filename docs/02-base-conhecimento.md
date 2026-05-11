# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `plutus_converted.jsonl` | JSON | base de conhecimento |


> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Estratégia de Integração

### Como os dados são carregados?
```python
import pandas as pd

df = pd.read_json("hf://datasets/0xroyce/Plutus-v2/plutus_converted.jsonl", lines=True)
```

### Como os dados são usados no prompt?
> está sendo passado um dataset contendo um historico de duvidas frequentes juntamente as respostas e outras informações como resposta

```text
usuario:
"role": "user",
"content": 

assistente:
"role": "assistant",
"content":

```

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
{
"role": "user",
"content": "Analyze the following content and extract key concepts related to trading performance and the psychology of a trader's failure. Provide detailed insights based on the information given.\n\nContext: The discussion centers around the psychological aspects of failure in trading, focusing on accountability, rationalization, and performance assessment. It highlights how traders respond to losses and the minimum capital provided to trainees in trading scenarios."
},
{
"role": "assistant",
"content": "The text illustrates that successful trading requires a clear recognition of one’s failures without delusion or rationalization. A trader may initially refrain from accepting personal responsibility for losses, often attributing them to external factors or biases, which inhibits learning and growth. Successful traders, on the other hand, confront their mistakes directly, as their equity acts as an honest measure of performance, fostering a culture of accountability. The content also reveals that trainees typically started with capital ranging from $25,000 to $50,000, with a few instances of significantly higher amounts, up to $250,000. This monetary threshold is critical since the cutout point for these trainees was effectively losing all their invested capital, highlighting the pressure and risks associated with trading. The speaker's use of humor suggests a grim acceptance that many trainees ultimately failed. This underscores that in the trading arena, the inability to learn from one's mistakes can lead to self-destruction rather than the traditional notion of being 'fired,’ emphasizing the unforgiving nature of the trading landscape."
}
...
```
