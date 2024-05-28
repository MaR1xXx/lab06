## Homework

После того, как вы настроили взаимодействие с системой непрерывной интеграции,</br>
обеспечив автоматическую сборку и тестирование ваших изменений, стоит задуматься</br>
о создание пакетов для измениний, которые помечаются тэгами (см. вкладку [releases](https://github.com/tp-labs/lab06/releases)).</br>
Пакет должен содержать приложение _solver_ из [предыдущего задания](https://github.com/tp-labs/lab03#задание-1)
Таким образом, каждый новый релиз будет состоять из следующих компонентов:
- архивы с файлами исходного кода (`.tar.gz`, `.zip`)
- пакеты с бинарным файлом _solver_ (`.deb`, `.rpm`, `.msi`, `.dmg`)

Для этого нужно добавить ветвление в конфигурационные файлы для **CI** со следующей логикой:</br>
если **commit** помечен тэгом, то необходимо собрать пакеты (`DEB, RPM, WIX, DragNDrop, ...`) </br>
и разместить их на сервисе **GitHub**.

1. Создаем файл `CMakeLists.txt` для создания пакетов с бинарным файлом solver: https://github.com/aakx000/lab06/blob/72023d5f8d4fed8b5276c12baac7a1dafa76fb44/CMakeLists.txt
 
2. Создаем файл `CPack.cmake` - файл-скрипт, используемый для генерации пакетов из скомпилированной программы: https://github.com/aakx000/lab06/blob/72023d5f8d4fed8b5276c12baac7a1dafa76fb44/CPack.cmake
 
3. Создаем директорию .github/workflows и два файла в нем: `CI.yml` для билдинга в Github Actions при каждом push или pull_request и `CI_release.yml` для билдинга при каждом push нового тэга. 
 
 - Файл `CI.yml`: https://github.com/aakx000/lab06/blob/72023d5f8d4fed8b5276c12baac7a1dafa76fb44/.github/workflows/CI.yml
 - Файл `CI_release.yml`: https://github.com/aakx000/lab06/blob/72023d5f8d4fed8b5276c12baac7a1dafa76fb44/.github/workflows/CI_release.yml
 
 Создание тэгов через терминал в прошлых лабораторных не встречалось, так что стоит привести пример команд:
 
```sh
$ git tag -a v1.0.5 -m "my version v1.0.5"
$ git push origin v1.0.5
```

4. Видим новый релиз во вкладке releases👍🏿

```
Copyright (c) 2015-2021 The ISC Authors
```
