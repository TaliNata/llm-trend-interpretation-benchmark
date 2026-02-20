# Выводы по сравнению моделей

## Общие условия эксперимента

Идентичные system и user prompts (v1)
Фиксированные параметры генерации (temperature = 0.2, max_tokens = 120)
Реальный аналитический сценарий: интерпретация тренд-сигналов на основе числовых метрик
Отсутствие prompt tuning и post-processing

### Baseline — openai/gpt-4o-mini

Поведение модели:
Строго следует инструкциям и ограничениям.
Интерпретация опирается исключительно на переданные метрики.
Тон нейтральный, аналитический, без спекуляций.
Волатильность корректно интерпретируется как признак нестабильного интереса, без попыток прогнозирования.

Роль в эксперименте:
Подходит в качестве стабильного baseline для последующих сравнений благодаря предсказуемому и сдержанному стилю.

### Comparison Case 01 — anthropic/claude-3.5-sonnet

Наблюдаемые отличия от baseline:
Более развернутые формулировки при тех же ограничениях длины.
Склонность к осторожным интерпретациям («возможное зарождение микротренда»), даже при низких абсолютных значениях.
Акцент на неопределённость и недостаточность данных выражен более явно.

Вывод:
Модель демонстрирует более интерпретативный и контекстуализированный стиль. Подходит для аналитических сценариев, где важна аккуратная интерпретация слабых сигналов, но может быть менее строга в избегании оценочных формулировок по сравнению с baseline.

### Comparison Case 02 — deepseek/deepseek-r1

Наблюдаемые отличия от baseline:
Более формальный и «отчётный» стиль изложения.
Явное повторение числовых метрик (growth ratio, velocity) в тексте ответа.
Чёткое разделение фактов и ограничений интерпретации (невозможность оценки долгосрочной значимости).

Вывод:
Модель ориентирована на декларативное подтверждение метрик и ограничений. Хорошо подходит для сценариев, 
где требуется прозрачность рассуждений и явная фиксация неопределённости, но может быть менее компактной по сравнению с baseline.

## Сравнительный итог
openai/gpt-4o-mini — наиболее строгий и лаконичный, оптимален как baseline и для production-сценариев с жёсткими требованиями к нейтральности.
anthropic/claude-3.5-sonnet — более осторожный и интерпретативный, лучше подходит для exploratory-аналитики и работы со слабыми сигналами.
deepseek/deepseek-r1 — формальный и метрико-ориентированный, полезен в сценариях, где важно явно артикулировать ограничения данных.

# Общий вывод проекта

Эксперимент подтверждает, что при идентичных условиях разные LLM демонстрируют устойчиво различающиеся аналитические стили, 
что имеет прямое значение для выбора модели в продакшн-пайплайнах.
Даже при строгих промптах и фиксированных параметрах выбор модели влияет на интерпретацию неопределённости, 
компактность выводов и акценты в анализе.

---

# Model Comparison Conclusions

## Experimental Conditions

Identical system and user prompts (v1)
Fixed generation parameters (temperature = 0.2, max_tokens = 120)
Real-world analytical scenario: trend signal interpretation based on numerical metrics
No prompt tuning or post-processing applied

### Baseline — openai/gpt-4o-mini

Model behavior:
Strict adherence to instructions and constraints
Interpretation relies exclusively on the provided metrics
Neutral, analytical tone without speculation
Volatility is correctly interpreted as a sign of unstable interest, without any attempt at forecasting

Role in the experiment:
Suitable as a stable baseline for subsequent comparisons due to its predictable and restrained analytical style

### Comparison Case 01 — anthropic/claude-3.5-sonnet

Observed differences from the baseline:
More elaborate phrasing under the same length constraints
A tendency toward cautious interpretations (e.g., “possible emergence of a micro-trend”), even with low absolute values
A stronger emphasis on uncertainty and data insufficiency

Conclusion:
The model exhibits a more interpretative and contextualized analytical style.
Well-suited for analytical scenarios where careful interpretation of weak signals is important, 
but it may be less strict in avoiding evaluative language compared to the baseline.

### Comparison Case 02 — deepseek/deepseek-r1

Observed differences from the baseline:
A more formal, report-like writing style
Explicit repetition of numerical metrics (growth ratio, velocity) within the response
Clear separation between stated facts and acknowledged interpretive limitations (e.g., inability to assess long-term significance)

Conclusion:
The model is oriented toward declarative confirmation of metrics and constraints.
Well-suited for scenarios requiring transparent reasoning and explicit articulation of uncertainty, 
though it may be less compact than the baseline.

## Comparative Summary

openai/gpt-4o-mini — the most strict and concise; optimal as a baseline and for production scenarios with stringent neutrality requirements
anthropic/claude-3.5-sonnet — more cautious and interpretative; better suited for exploratory analytics and weak-signal analysis
deepseek/deepseek-r1 — formal and metric-oriented; useful in scenarios where explicit articulation of data limitations is critical

# Overall Project Conclusion

The experiment confirms that, under identical conditions, 
different LLMs exhibit consistently distinct analytical styles, 
which has direct implications for model selection in production pipelines.
Even with strict prompts and fixed parameters, 
the choice of model affects how uncertainty is interpreted, 
how concise conclusions are, and which analytical aspects are emphasized.
