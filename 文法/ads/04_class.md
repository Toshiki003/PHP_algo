```php
<?php
class Employee
{
    public function work()
    {
        echo '仕事をしているyo!';
    }
}
$employee = new Employee(); // インスタンス化

$employee->work(); // インスタンス化したクラスのメソッドを呼び出す。アロー演算子を使う。
// 仕事をしているyo!
```
