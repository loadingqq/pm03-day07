# Проверка CI
## Событие, ветка и SHA
## Красный запуск
URL, job, упавший step, ожидаемый и фактический результат.
## Исправление
## Зелёный запуск на Python 3.11 и 3.12
## Два новых сценария
## Что автоматическая проверка пока не покрывает
## Пара 1

- URL запуска: <(https://github.com/loadingqq/pm03-day07/actions/runs/37929838549)>
- SHA коммита: <efd31912ddb2afeb1af99e0f50c2c4b38c202172>
- Версии Python: 3.11, 3.12
- Число тестовых методов: 6
- Результат: OK

# Пара 2. Диагностический эксперимент
# Красный run
- URL: <(https://github.com/loadingqq/pm03-day07/actions/runs/37937005463)>
- SHA коммита: <13bb4ab4003eae0f9d7b2878b72437f53b9b82bb>
- Ветка: ci/boundary
- Событие: pull_request
- Упавший шаг: Run tests
- Упавший тест: test_at_limit
- Ожидаемое значение: False
- Фактическое значение: True
- Причина: оператор `>=` вместо `>` - на границе функция вернула True вместо False

# Зеленый run
Зелёный run
- URL: <https://github.com/loadingqq/pm03-day07/actions/runs/37937622252>
- SHA коммита: <0eea7afabdc40ada51c1db9f25635fc06ded0ab4>
- Ветка: ci/boundary
- Событие: pull_request (обновление PR)
- Результат: 6 методов, OK, оба job зелёные

# diff
- return elapsed_minutes > LIMITS[priority]
+ return elapsed_minutes >= LIMITS[priority]

# Пара 3. Расширение проверок
# Итоговый run (после merge)
- URL: <https://github.com/loadingqq/pm03-day07/actions/runs/37941913769>
- SHA: <bfbf7165af92e57e2b050ba3bc7e8521818f3f8b>
- Ветка: main
- Версии Python: 3.11, 3.12
- Число методов: 8
- Результат: OK, оба job зелёные