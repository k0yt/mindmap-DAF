### Домен Контроль ИБ артефактов, зависимостей и образов (T-ADI)

```mermaid
%%{init: {'theme':'forest'}}%%
mindmap
  root((T-ADI))
    DEP Контроль использования сторонних компонентов
      0
        Управление зависимостями в исходном коде осуществляется в каком-либо виде
      1
        1 Существуют и формализованы единые правила, определяющие возможность использования тех или иных зависимостей в коде. Например, есть утвержденный документ, и/или страница в базе знаний, описывающие порядок использования зависимостей в коде.
        2 Обновление существующих зависимостей выполняется вручную. Например, если возникла необходимость использовать новую версию библиотеки в коде, то ее вручную выгружают и добавляют в проект
        3 Существует - описан, формализован, план реагирования на события ИБ, связанных с зависимостями.
        4 Выполняется харденинг - безопасная настройка, файлов конфигураций используемых пакетов open source software - OSS - например, nuget.config, .npmrc, pip.conf, pom.xml, etc. 
        5 Зависимости с тэгом "latest" не применяются
      2
        1 Разработчики получают и используют OSS компоненты, применяя только стандартизованные - формализованные и утвержденные методы
        2 Контролируется и регулируется использование новых - моложе 60 дней и старых - неактуальных, заброшенных, старше 365 дней OSS. Например, настроен OSS firewall на предупреждение или запрет использования OSS, выпущенных\актуализированных более 365 дней назад и менее чем 60 дней
      3
        1 Выполняется инвентаризация используемых зависимостей. Например, создан внутренний репозиторий.
        2 При выполнении Pull/Merge request предоставляется список всех уязвимостей используемых зависимостей. Это может быть реализовано с помощью SCA системы.
        3 Выполняется верификация цифровой подписи SBOM перед использованием зависимостей в сборке. Это может быть реализовано с помощью SCA системы.
        4 Выполняется автоматическое обновление используемых зависимостей. Это может быть реализовано с помощью специальных утилит для обновления зависимостей.
      4
        1 Выполняется самостоятельная сборка необходимых зависимостей в доверенной среде
        2 Выполняется создание и проверка цифровой подписи собранных зависимостей. Например, с помощью Cosign
        3 Выполняется создание и проверка цифровой подписи на SBOM для собранных зависимостей. Например, с помощью Cosign
    ART Управление артефактами	
      0
        Управление артефактами разработки присутствует в каком-либо виде
```
### Домен Защита окружения разработки (T-DEV)

```mermaid
%%{init: {'theme':'forest'}}%%
mindmap
  root((T-DEV))
    COMP Защита рабочих мест разработчика
      0
        1 Применяются практики защиты рабочих мест разработчиков
```
