# Описание проекта

Этот репозиторий содержит эксперимент по сравнению поведения больших языковых моделей (LLM) 
при интерпретации структурированных сигналов трендов в социальных медиа.
Эксперимент фокусируется на LLM-блоке аналитического пайплайна, 
где модель получает строго заданный структурированный вход с числовыми метриками 
(частота упоминаний, рост, скорость, устойчивость) 
и должна только интерпретировать сигнал, не изменяя входные данные и не добавляя новых фактов.

Для обеспечения корректного сравнения все модели и версии тестируются:
на идентичных входных данных,
с одинаковыми системными и пользовательскими промптами,
при фиксированных параметрах вызова.
Эксперименты выполняются в оркестрированном workflow (n8n), 
который используется исключительно как слой исполнения и логирования, 
без влияния на содержимое запросов и ответов.

# Цель проекта

Цель проекта — оценить различия между LLM-моделями и версиями с точки зрения их поведения в аналитическом контексте, а именно:
способность строго следовать инструкциям и ограничениям;
корректность интерпретации числовых сигналов без галлюцинаций;
устойчивость аналитического стиля при одинаковом входе;
склонность к спекулятивным или избыточным формулировкам;
чувствительность к формату и роли, заданным в системном промпте.

Проект ориентирован на сценарии реального использования LLM в продакшн-аналитике, 
где модели выступают не как генераторы контента, 
а как контролируемые аналитические компоненты внутри автоматизированного пайплайна.

---

# Project Description

This repository contains an experiment comparing the behavior of large language models (LLMs) 
when interpreting structured trend signals from social media.

The experiment focuses on the LLM block within an analytical pipeline, where the model receives 
a strictly defined structured input containing numerical metrics (mention frequency, growth, velocity, stability) 
and is required only to interpret the signal, without modifying the input data or introducing new facts.

To ensure a fair and controlled comparison, all models and versions are tested:
on identical input data,
using the same system and user prompts,
with fixed invocation parameters.

The experiments are executed within an orchestrated workflow (n8n), which is used solely as 
an execution and logging layer and does not influence the content of the requests or responses.

# Project Objective

The objective of this project is to evaluate differences between LLM models and versions 
in terms of their behavior in an analytical context, specifically:
the ability to strictly follow instructions and constraints;
the correctness of numerical signal interpretation without hallucinations;
the consistency of analytical style given identical inputs;
the tendency toward speculative or excessive wording;
sensitivity to format and role definitions provided in the system prompt.

The project is designed for real-world LLM production analytics scenarios, 
where models function not as content generators, but as controlled analytical components within automated pipelines.
