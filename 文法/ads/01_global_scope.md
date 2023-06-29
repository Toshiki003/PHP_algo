
```PHP
<?php
$value = 'globalScope';

function test1(){
  $value01 = 'localScope';
  echo $value01; // これはローカルスコープの変数として扱われる
}
test1(); // localScope


function test2(){
  global $value;
  echo $value;
}
test2(); // globalScope

// 基本的にはローカルスコープの変数を使うべき
```
