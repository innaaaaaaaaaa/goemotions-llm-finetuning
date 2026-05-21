# Fine-tuning LLM для многоклассовой классификации эмоций

Репозиторий содержит код экспериментов по дообучению больших языковых моделей 
на корпусе GoEmotions методами LoRA и QLoRA.

## Описание экспериментов

| Ноутбук | Модель | Метод | Платформа |
|---|---|---|---|
| `mistral-lora-lightning.ipynb` | Mistral 7B v0.1 | LoRA (fp16) | Lightning AI |
| `mistral-qlora-colab.ipynb` | Mistral 7B v0.1 | QLoRA (4bit) | Google Colab |
| `llama-lora-lightning.ipynb` | LLaMA 3.1 8B | LoRA (fp16) | Lightning AI |
| `llama-qlora-colab.ipynb` | LLaMA 3.1 8B | QLoRA (4bit) | Google Colab |

## Данные

Корпус [GoEmotions](https://huggingface.co/datasets/go_emotions) (simplified), 
28 классов эмоций, мультикатегориальная разметка.

## Параметры обучения

- LoRA rank: r=16, alpha=32
- Целевые модули: q_proj, k_proj, v_proj, o_proj, gate_proj, up_proj, down_proj
- Максимальная длина последовательности: 128 токенов
- Эффективный размер батча: 16

## Требования

transformers>=4.40
peft>=0.9
accelerate
datasets
scikit-learn
bitsandbytes>=0.43 (для QLoRA)

## Автор

Сафина Инна Анатольевна  
Выпускная квалификационная работа, СПбПУ, 2025
