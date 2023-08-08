# Тестовое задание


[Ссылка на сайт](https://maratmustafin.github.io/green-api/)


### Требование
1. ~~Требуется разработать HTML-страницу с вызовом методов GREEN-API:~~ 
    - • getSettings
    - • getStateInstance
    - • sendMessage
    - • sendFileByUrl
2. ~~Требуется разместить на странице параметры подключения к инстансу - idInstance
и ApiTokenInstance~~ 
3. ~~Требуется вывести ответ методов в отдельное поле на странице только для чтения.~~
4. ~~Требуется придерживаться макета – см. рис. ниже.~~


### Запуск
Версия node v16.15.1
```cmd
npm run dev 
```

### Билд

```cmd
npm run build
cd dist
# add . to path before /assets
python -m http.server
open
```


### Видео-презентация


https://github.com/MaratMustafin/green-api/assets/46228366/0cdaacb8-ef8a-4f76-bc33-7e2b0a2fdad6



### ToDo 

- Добавить историю, сохранять запросы
- Добавить кнопки для копирования, удаления
- Добавить поиск по меткам.
