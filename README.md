<h1> TenderDataParser </h1>

<p>Парсинг сайта «РУСАЛ»: <a href="https://tender.rusal.ru/Tenders">https://tender.rusal.ru/Tenders</a> с установленным фильтром: Раздел - ЖД, Авиа, Авто, Контейнерные перевозки.</p>

<h2>Здравствуйте!</h2>

<p>В этом репозитории я представляю свой парсер для сайта «РУСАЛ», разработанный на PHP, MySQL, HTML и CSS. Парсер нацелен на получение данных с указанной страницы с установленным фильтром.</p>

<p>В файле <code>parser.php</code> происходит извлечение и обработка данных, включая номера тендеров, наименование организации и ссылки на процедуры. Также из каждой процедуры извлекаются дата начала подачи заявок, названия файлов документации и ссылки для их скачивания перед отправкой в базу данных.</p>

<p>Файл <code>index.php</code> отвечает за получение данных из базы и отображение их в таблице с пагинацией.</p>

<h3>Обратите внимание</h3>
<p>что в двух файлах необходимо изменить параметры подключения к базе данных (комментарии указаны). Я также приложил дамп базы данных, содержащий 1079 записей на момент создания репозитория.</p>

<h3>Важные моменты:</h3>

<p>У меня возникли сложности с выгрузкой и обработкой данных с сайта, так как нужно было обработать более 1000 записей. Если вы не планируете использовать мой дамп базы данных и хотите заново парсить сайт РУСАЛ, вот что нужно сделать в файле <code>parser.php</code>:</p>

<ol>
    <li>
        В строке 59 измените значение переменной <code>$count</code> на 0, затем на 300, 600, 900 и в конце установите его равным количеству записей в таблице. Соответственно, изменяйте значение переменной <code>$recordsProcess</code>, начиная с 300 и увеличивая до <code>$recordsProcess</code> (количество элементов в массиве):
        <pre><code>for ($i = $count; $i &lt; $recordsToProcess; $i++) {
}</code></pre>
    </li>
    <li>
        В строке 141 выполните аналогичные изменения:
        <pre><code>for ($i = $count; $i &lt; $recordsToProcess; $i++) {
}</code></pre>
    </li>
    <li>
        В первом случае данные с сайта сохраняются и объединяются в массив, а во втором — извлекаются из массива и записываются в таблицу. Важно, чтобы значения в обоих случаях совпадали.
    </li>
</ol>

<p>Проект показался мне интересным, и я не жалею о потраченном времени на его разработку.</p>
