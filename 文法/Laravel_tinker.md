```php
App\User.phpの場合は、
>> User::all()

App\Models\Book.phpの場合は、
>> App\Models\Book::all()
=> Illuminate\Database\Eloquent\Collection {#3044
     all: [],
   }
```

use Illuminate\Database\Eloquent\Model;がないとtinkerで対話はできない。

これはModelクラスを利用するために必要な名前空間のインポート。use


## リレーションしたコレクションの取得

```php
>>> $book = Book::find(1);
>>> $book->evaluations;
=> Illuminate\Database\Eloquent\Collection {#3076
     all: [
       App\Models\Evaluation {#3077
         id: 1,
         books_id: 1,
         evaluation: 1,
         word: "リレーションしたコレクション",
         created_at: "2023-07-23 15:56:17",
         updated_at: "2023-07-23 15:56:17",
         created_by: null,
         updated_by: null,
         deleted_by: null,
         deleted_at: null,
       },
			...
			],
		}
>>>
```

上記より、クラスメソッドは::

インスタンスメソッドは→


## クラスメソッド(::)
```php
class MyClass {
    public static function myStaticMethod() {
        return "This is a static method.";
    }
}

// クラスメソッドを呼び出す
echo MyClass::myStaticMethod(); // 出力: "This is a static method."
```

## インスタンスメソッド（アロー演算子）
```php
class MyClass {
    public function myInstanceMethod() {
        return "This is an instance method.";
    }
}

// インスタンスを作成
$instance = new MyClass();

// インスタンスメソッドを呼び出す
echo $instance->myInstanceMethod(); // 出力: "This is an instance method."
```


## whereを使った条件付きのデータ抽出
```php
>>> Book::where("price", ">", 300)->get()->toArray();
=> [
     [
       "id" => 1,
       "title" => "1番目の投稿",
       "price" => 450,
       "outline" => "がいよう",
       "image" => "public/books_images/OlNJK7WY9nOefArkiuOHwCSObf3h5N9dFniBaPEJ.jpeg",
       "created_at" => "2023-07-21 00:40:45",
       "updated_at" => "2023-07-25 04:35:15",
       "created_by" => null,
       "updated_by" => null,
       "deleted_by" => null,
       "deleted_at" => null,
     ],
     [
       "id" => 2,
       "title" => "2番目の投稿",
       "price" => 1000,
       "outline" => "2",
       "image" => "public/books_images/Nm8Seb3sPtjtXvl3CcZgf6RC3u9vktV3e4vCVAEZ.jpeg",
       "created_at" => "2023-07-25 04:35:04",
       "updated_at" => "2023-07-25 04:35:04",
       "created_by" => null,
       "updated_by" => null,
       "deleted_by" => null,
       "deleted_at" => null,
     ],
   ]
>>>
```
