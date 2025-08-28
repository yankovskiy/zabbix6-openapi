# Zabbix 6 OpenAPI Project

## Цель проекта

Создание неофициального OpenAPI описания для Zabbix 6.0 API на основе официальной документации:
https://www.zabbix.com/documentation/6.0/en/manual/api/reference

## Структура проекта

Проект организован по методам API, где каждый каталог соответствует префиксу метода (до точки).

### Файлы проекта

- `index.html` - главная страница с интерфейсом для просмотра API документации (использует Redoc)
- Каталоги методов с OpenAPI спецификациями в формате YAML

### Структура каталогов

```
├── action/          # action.create, action.get, action.update, action.delete
├── alert/           # alert.get
├── apiinfo/         # apiinfo.version
├── auditlog/        # auditlog.get
├── authentication/ # authentication.get, authentication.update
├── autoregistration/ # autoregistration.get, autoregistration.update
├── configuration/   # configuration.export, configuration.import, configuration.importcompare
├── correlation/     # correlation.create, correlation.get, correlation.update, correlation.delete
├── dashboard/       # dashboard.create, dashboard.get, dashboard.update, dashboard.delete
├── dcheck/          # dcheck.get
├── dhost/           # dhost.get
├── drule/           # drule.create, drule.get, drule.update, drule.delete
├── dservice/        # dservice.get
├── event/           # event.acknowledge, event.get
├── graph/           # graph.create, graph.get, graph.update, graph.delete
├── graphitem/       # graphitem.get
├── graphprototype/  # graphprototype.create, graphprototype.get, graphprototype.update, graphprototype.delete
├── hanode/          # hanode.get
├── history/         # history.get, history.clear
├── host/            # host.create, host.get, host.update, host.delete, host.massadd, host.massremove, host.massupdate
├── hostgroup/       # hostgroup.create, hostgroup.get, hostgroup.update, hostgroup.delete, hostgroup.massadd, hostgroup.massremove, hostgroup.massupdate
├── hostinterface/   # hostinterface.create, hostinterface.get, hostinterface.update, hostinterface.delete, hostinterface.massadd, hostinterface.massremove, hostinterface.replacehostinterfaces
├── hostprototype/   # hostprototype.create, hostprototype.get, hostprototype.update, hostprototype.delete
├── httptest/        # httptest.create, httptest.get, httptest.update, httptest.delete
├── iconmap/         # iconmap.create, iconmap.get, iconmap.update, iconmap.delete
├── image/           # image.create, image.get, image.update, image.delete
├── item/            # item.create, item.get, item.update, item.delete
├── itemprototype/   # itemprototype.create, itemprototype.get, itemprototype.update, itemprototype.delete
├── ldap/            # ldap.get, ldap.update
├── maintenance/     # maintenance.create, maintenance.get, maintenance.update, maintenance.delete
├── map/             # map.create, map.get, map.update, map.delete
├── mediatype/       # mediatype.create, mediatype.get, mediatype.update, mediatype.delete
├── problem/         # problem.get
├── proxy/           # proxy.create, proxy.get, proxy.update, proxy.delete
├── regexp/          # regexp.create, regexp.get, regexp.update, regexp.delete
├── report/          # report.create, report.get, report.update, report.delete
├── role/            # role.create, role.get, role.update, role.delete
├── script/          # script.create, script.get, script.update, script.delete, script.execute, script.getscriptsbyhosts
├── service/         # service.create, service.get, service.update, service.delete
├── settings/        # settings.get, settings.update
├── sla/             # sla.create, sla.get, sla.update, sla.delete, sla.getsli
├── task/            # task.create, task.get
├── template/        # template.create, template.get, template.update, template.delete
├── templatedashboard/ # templatedashboard.create, templatedashboard.get, templatedashboard.update, templatedashboard.delete
├── token/           # token.create, token.get, token.update, token.delete, token.generate
├── trend/           # trend.get
├── trigger/         # trigger.create, trigger.get, trigger.update, trigger.delete, trigger.adddependencies, trigger.deletedependencies
├── triggerprototype/ # triggerprototype.create, triggerprototype.get, triggerprototype.update, triggerprototype.delete
├── user/            # user.create, user.get, user.update, user.delete
├── usergroup/       # usergroup.create, usergroup.get, usergroup.update, usergroup.delete
├── usermacro/       # usermacro.create, usermacro.get, usermacro.update, usermacro.delete
├── valuemap/        # valuemap.create, valuemap.get, valuemap.update, valuemap.delete
└── webscenario/     # webscenario.create, webscenario.get, webscenario.update, webscenario.delete
```

## Как работать с проектом

### Просмотр документации

1. **Веб-интерфейс**: Откройте `index.html` в браузере для интерактивного просмотра API документации
2. **Навигация**: Выберите нужный API метод из списка и нажмите "Загрузить API документацию"
3. **Redoc интеграция**: Документация отображается с помощью Redoc для удобного просмотра

### Создание OpenAPI описания для метода

Для создания OpenAPI спецификации для конкретного метода, используйте команду:

```
Создай OpenAPI описание для метода [method_name]
```

Например:
- `Создай OpenAPI описание для метода host.get`
- `Создай OpenAPI описание для метода action.create`

### Соглашения

1. **Файлы размещаются** в соответствующих каталогах по префиксу метода
2. **Формат файлов**: YAML (.yaml)
3. **Названия файлов**: соответствуют полному имени метода (например, `host.get.yaml`, `action.create.yaml`)
4. **Структура OpenAPI**: используется OpenAPI 3.0.3
5. **Источник данных**: официальная документация Zabbix 6.0

### Инструкции для Claude

При создании OpenAPI описаний:
1. Изучить официальную документацию для указанного метода
2. Создать полную OpenAPI спецификацию включая:
   - Описание метода
   - Параметры запроса
   - Примеры запросов
   - Схемы ответов
   - Коды ошибок
3. Разместить файл в соответствующем каталоге
4. Использовать консистентное форматирование и структуру

### Валидация OpenAPI спецификаций

Для проверки созданных OpenAPI спецификаций используйте команду:

```
/validate-openapi @путь/к/файлу.yaml
```

Например:
- `/validate-openapi @item/item.get.yaml`
- `/validate-openapi @host/host.get.yaml`

**Что проверяется:**
1. YAML синтаксис с помощью pyyaml
2. Дублированные ключи
3. Соответствие OpenAPI 3.0.3 спецификации
4. Структурные ошибки
5. Валидность внутренних ссылок ($ref)

**Что делается:**
- Автоматически исправляются найденные ошибки
- Выводится детальный отчет о проблемах и исправлениях
- Проверяется валидность после исправлений

## Статус проекта

- ✅ Создана структура каталогов
- ✅ Добавлены .keep файлы
- ✅ Создан веб-интерфейс (index.html) с интеграцией Redoc
- ✅ Исправлены проблемы с переключением между API методами в веб-интерфейсе
- ✅ Реализована поддержка host.get метода
- ✅ Реализована поддержка item.get метода
- ✅ Реализована поддержка trigger.get метода
- ✅ Реализована поддержка template.get метода
- ✅ Реализована поддержка hostinterface.get метода
- ✅ Добавлена система валидации OpenAPI спецификаций
- ⏳ OpenAPI спецификации для остальных методов создаются по запросу

## Ссылки

- **GitHub репозиторий**: https://github.com/yankovskiy/zabbix6-openapi
- **Официальная документация Zabbix 6.0 API**: https://www.zabbix.com/documentation/6.0/en/manual/api/reference

## Команды для разработки

В данном проекте пока не определены команды для линтинга или проверки типов. При появлении таких команд они будут добавлены в этот раздел.