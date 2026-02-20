# LLM Trend Interpretation Benchmark

## Обзор
Бенчмарк-проект по сравнению поведения различных LLM в реальном аналитическом сценарии: интерпретация структурированных сигналов трендов из социальных медиа.

## Сценарий
Модели получают числовые метрики тренда (упоминания, рост, скорость, устойчивость) и должны сформировать краткую нейтральную интерпретацию (2–3 предложения) при строгих ограничениях:
- без добавления новых фактов
- без прогнозов
- без маркетинговых формулировок

## Методология
- Идентичные system и user prompts (v1)
- Фиксированные параметры: temperature = 0.2, max_tokens = 120
- Одинаковые входные сигналы для всех запусков
- Отсутствие prompt tuning и post-processing

## Сравниваемые модели
- openai/gpt-4o-mini (baseline)
- anthropic/claude-3.5-sonnet
- deepseek/deepseek-r1

## Ключевые наблюдения
- При идентичных ограничениях разные модели демонстрируют различающиеся аналитические стили.
- Одни модели делают акцент на неопределённости, другие — на подтверждении метрик.
- Выбор модели влияет на интерпретационное поведение в аналитических пайплайнах.

## Структура репозитория
- `baseline/` — эталонное поведение модели
- `comparison/` — альтернативные модели при идентичных условиях
- `comparison/conclusions.md` — детальные наблюдения и выводы

## Назначение проекта
Проект демонстрирует структурированную оценку LLM и сравнение моделей для аналитически ориентированных сценариев использования.

---

## Overview
Benchmark project comparing the behavior of different LLMs in a real-world analytics scenario: interpretation of structured social media trend signals.

## Scenario
Models receive numerical trend metrics (mentions, growth, velocity, stability) and must produce a short, neutral interpretation (2–3 sentences) under strict constraints:
- no new facts
- no forecasts
- no marketing language

## Methodology
- Identical system and user prompts (v1)
- Fixed parameters: temperature = 0.2, max_tokens = 120
- Same input signals for all runs
- No prompt tuning or post-processing

## Models Compared
- openai/gpt-4o-mini (baseline)
- anthropic/claude-3.5-sonnet
- deepseek/deepseek-r1

## Key Findings
- Different models exhibit distinct analytical styles under identical constraints.
- Some models emphasize uncertainty, others focus on metric confirmation.
- Model choice impacts interpretative behavior in analytics pipelines.

## Structure
- `baseline/` — reference model behavior
- `comparison/` — alternative models under identical conditions
- `comparison/conclusions.md` - detailed observations and conclusions.

## Purpose
Demonstrates structured LLM evaluation and model comparison for analytics-oriented use cases.
