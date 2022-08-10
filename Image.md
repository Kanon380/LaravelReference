# Form

### Send
```bash
php artisan storage:link
```

```php
// そのまま保存
$request->file('image')->store('public/' . $directory_name);

// ファイル名取得
$file_name = $request->file('image')->getClientOriginalName();

// 名前を付けて保存
$request->file('image')->storeAs('public/' . $dir, $file_name);

// pathをDBに保存
Image::create([
  'img_path' => 'storage/' . $directory_name . '/' . $file_name;
]);
```

```php
<img src="{{ asset($image->path) }}">
```
