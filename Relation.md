# Relation

### Parent Model
```php
public function childs(){
  return $this->hasMany(Cart::class, 'uuid', 'user_id');
}
```

### Child Model
```php
public function user(){
  return $this->belongsTo(User::class, 'user_id', 'uuid');
}
```
