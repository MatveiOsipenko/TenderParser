# TenderParser
Парсинг сайта: «РУСАЛ»: https://tender.rusal.ru/Tenders  С установленным фильтром: Раздел - ЖД, Авиа, Авто, Контейнерные перевозки.
Здравствуйте! 
В данном репозитории я выкладываю свой парсер для сайта «РУСАЛ»: https://tender.rusal.ru/Tenders с установленным фильтром: Раздел - ЖД, Авиа, Авто, Контейнерные перевозки на PHP,MySql,HTML,CSS.
В файле parser.php происходит получение/обработка данных(а именно: номера тендеров, наименование организации, ссылка на процедуру. Со страницы процедуры: дата начала подачи заявок, название файлов документации и ссылка на их скачивание) с сайта перед тем как они отправятся в БД.
В файле index.php идет получение данных из БД в таблицу с пагинацией.
В двух файлах надо изменить подключение к БД(коментарии указаны), также приложил свой дамп БД в котором 1079 записей на момент написания репозитория.
Важные моменты:
  У меня возникли проблемы с выгрузкой и обработкой данных с сайта, так как мне надо было обработать 1000+ записей, поэтому, если вы не используете мой дамп БД, а хотите парсить сайт РУСАЛА заново,то вот что я делал в файле parser.php:
  1) в 59 строке значение $count я менял на 0, потом на 300, 600, 900 и в конце установил $count(количество записей в таблице). Значение $recordsProcess я менял соотвестеноо, сначала 300 и так до $recordsProcess(count массива):
     for ($i = $count; $i < $recordsToProcess; $i++) {
  2) в 141 строке я проделовал все тоже самое:
     for ($i = $count; $i < $recordsToProcess; $i++) {
  3) В первом случае у меня данные с сайта сохраняются и объеденяются в массив, во втором: из массива в таблицу, главное выставлять одинаковые значения в двух случаях.
      
Проект мне показался интересным, не жалею что потратил на него время.
  
