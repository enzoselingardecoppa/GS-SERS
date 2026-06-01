# Mission Control AI — Sistema de Monitoramento de Missão Espacial

Sistema inteligente de monitoramento de cabine espacial desenvolvido com Python e Llama 3.2. Interpreta dados simulados de sensores, classifica níveis de risco e gera análises automáticas com recomendações de ação.

---

## Equipe

| Nome | RM |
|------|----|
| [Enzo Coppa Selingarde ] | [573393] |
| [Gabriel Carlos Barbosa] | [574074] |
| [Gustavo de Souza Abreu] | [574080] |

---

## Descrição

O Mission Control AI monitora continuamente 6 variáveis críticas de uma cabine espacial e utiliza o modelo Llama 3.2 para interpretar os dados, prever falhas e recomendar ações corretivas.


## Variáveis Monitoradas

| Sensor | Seguro | Alerta | Crítico |
|--------|--------|--------|---------|
| Temperatura | 18–30°C | 30–38°C | >38°C |
| Luminosidade | 0–341 | 342–682 | >683 |
| Vibração | Não detectada | — | Detectada |
| Bateria | 51–100% | 30–50% | 0–29% |
| Geração Solar | 667–1000W | 334–666W | 0–333W |
| Comunicação | 67–100% | 34–66% | 0–33% |

---

## Arquitetura do Sistema

**Bloco 0 — Configuração**
Imports, autenticação HuggingFace e carregamento do modelo Llama 3.2.

**Bloco 1 — Simulação de Dados**
Geração aleatória dos 6 sensores via `random` e classificação automática via funções Python.

**Bloco 2 — Análise da IA**
System prompt estruturado com tabela de risco. A IA retorna Status, Risco e Recomendação para cada sensor.

**Bloco 3 — Modo Interativo**
Loop de perguntas onde o usuário interage com a IA com base nas leituras atuais.

---

## Parâmetros do Modelo

| Parâmetro | Valor | Justificativa |
|-----------|-------|---------------|
| `temperature` | 0.4 | Valor baixo garante respostas precisas e focadas, evitando respostas imprecisas em contexto crítico |
| `do_sample` | True | Permite variação natural nas respostas mantendo coerência com a temperature baixa |
| `max_new_tokens` | 1000 | Suficiente para análise completa dos 6 sensores |

---

## Tecnologias

- Python 3.12
- Llama 3.2 3B Instruct (meta-llama/Llama-3.2-3B-Instruct)
- Transformers — Hugging Face
- PyTorch
- Kaggle Notebooks

---

## Como Executar

1. Acesse o notebook no Kaggle
2. Configure seu token HuggingFace em Add-ons → Secrets com o nome `HUGGING_FACE_API_KEY`
3. Aceite os termos do modelo em huggingface.co/meta-llama/Llama-3.2-3B-Instruct
4. Execute todas as células em ordem
5. Interaja com o sistema no Bloco 3

---

## Links

- Repositório GitHub: [(https://github.com/enzoselingardecoppa/GS-SERS/tree/main)]
- Vídeo YouTube: [https://youtu.be/FR3RM7C7N3A]
