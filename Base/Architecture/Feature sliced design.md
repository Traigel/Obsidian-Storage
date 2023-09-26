2023-04-25 01:25
Tags: #architecture 

---
[Feature sliced design](https://feature-sliced.design/ru/)

# Layers (Слои)
Слоёв строго 7 штук, но некоторые не обязательные. Каждый слой обладает своей зоной ответственности и эти слои уже бизнес ориентированы.
Нельзя использовать выше стоящий слой, что бы получить линейный поток данных.
app -> processes -> pages -> widgets -> features -> entites -> shared
![[feature_sliced_design_layers_abs.jpg]]
Каждый слой содержит внутри себя слайсы (модули).
Используется только ниже лежащие слои что бы получить линейный поток данных.

![[feature_sliced_design_layers_src.jpg]]

---
- ### App
Инициализирующая логика приложения, точка входа в приложение (провайдеры, роутер, глобальная конфигурация, глобальные стили и т.д.)
![[feature_sliced_design_layers_app.jpg]]

---
- ### Processes
Процесс который затрагивает несколько страниц.

---
- ### Pages
Страницы приложения, собираются из widgets и features. Должна быть максимально "тонкой". Минимум бизнес-логики, запросов и прочего.
![[feature_sliced_design_layers_pages.jpg]]

---
- ### Widgets
Mаксимально самостоятельные блоки для страниц, на сколько это возможно и которые комбинируют нижние слои. (header/navbar, sidebar, footer и т.д.)
Состоят из сегментов (api, components, model, ...)

---
- ### Features
Пользовательские сценарии которые несут какую-то бизнес ценность. Одна фича решает одну функциональную задачу. (поставить лайк, оценка товара, подписка на пользователя и т.д.)
![[feature_sliced_design_layers_features.jpg]]

---
- ### Entites (сущности)
Конкретные бизнес сущности. (товар, заказ, пользователь, комментарий, отзыв и т.д.)
	1. Внутри слоя находятся слайсы, конкретные модули.
	2. Внутри каждого из слайсов находятся сегменты (api, components, model, ...)
![[feature_sliced_design_layers_entites_1.jpg]] ![[feature_sliced_design_layers_entites_2.jpg]] ![[feature_sliced_design_layers_entites_3.jpg]]

---
- ### Shared
Mаксимально переиспользуемые модули. (UI компоненты: кнопки, модалки ..., хелперы которые не привязаны к бизнес логике, конфигурация приложения и т.д.)
![[feature_sliced_design_layers_shared_1.jpg]]  ![[feature_sliced_design_layers_shared_2.jpg]]   ![[feature_sliced_design_layers_shared_3.jpg]]

---
# Segments (Сегменты)
Каждый слайс внутри себя содержит сегменты:
- UI - это наши компоненты
- model - это бизнес логика (взаимодействие со state, селекторы, экшэны и т.д.)
- lib - это все хелперы, вспомогательные функции
- config - конфигурация модуля если она требуется
- api - запросы на сервер, которые требуются для модуля
- consts - константы в конкретном модуле

![[feature_sliced_design_segments.jpg]]

---
### Links
[[Architecture]]