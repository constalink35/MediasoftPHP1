# MediasoftPHP
Академия разработки MediaSoft курс PHP
#Линкевич Константин
##Задание 1. Циклы и функции.
<p>Необходимо проанализировать текст</p>
<ul>
  <li>подсчитать общее количество слов</li>
  <li>подсчитать сколько раз слово используется в тексте</li>
  <li>вывести в консоль общую статистику в формате:</li>
 </ul> 
  (слово) (число вхождений)<br>
  Всего слов (кол-во слов)<br>
  <hr>
  Функция function countWords($content) находиться в файле
  ```
  
  function countWords($content){
      //чистим текст от знаков препинания, двойных пробелов, переводим в нижний регистр
      $content =preg_replace('#([:;!?,./"])+|(-\s+)#',' ',$content);
      $content =mb_strtolower(trim(preg_replace('/\s\s+/',' ',$content)));
  
      if (empty($content)) return $arr_words=[];
  
      $arr_words = array_count_values(explode(' ',$content));
      //сортируем по убыванию количества повторов
      arsort($arr_words);
      return $arr_words;
    }
  ```
   [ms_task1.php]:https://github.com/constalink35/MediasoftPHP/blob/master/ms_task1.php
  
  Работу функции можно посмотреть:
  https://kvltest.000webhostapp.com/ms_task1.php
