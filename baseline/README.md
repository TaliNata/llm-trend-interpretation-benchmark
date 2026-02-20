# Определение Baseline

Эта папка содержит базовую конфигурацию, используемую в качестве точки отсчёта
для всех последующих сравнений моделей и версий.

Baseline отражает исходное поведение модели при фиксированных условиях.
Все последующие наблюдения оцениваются относительно неё.

## Конфигурация

- Модель: openai/gpt-4o-mini
- Сценарий: интерпретация тренда
- Версия промпта: v1
- Temperature: 0.2
- Максимальное количество токенов: 120
- Среда выполнения: workflow n8n

## Примечания

Никакая настройка промптов или постобработка не применялись.
Выход baseline используется исключительно как поведенческий ориентир,
а не как эталон качества.

---

# Baseline Definition

This folder contains the baseline setup used as a reference point
for all subsequent model and version comparisons.

Baseline represents the initial model behavior under fixed conditions.
All later observations are evaluated relative to this baseline.

## Baseline Configuration

- Model: openai/gpt-4o-mini
- Scenario: Trend interpretation (single structured signal)
- Prompt version: v1
- Temperature: 0.2
- Max tokens: 120
- Execution environment: n8n workflow

## Notes

No prompt tuning or post-processing was applied.
The baseline output is used only as a behavioral reference,
not as a quality benchmark.
