# Relation

### Parent Model
```php
public function childs(){
  return $this->hasMany(Child::class, 'uuid', 'user_id');
}
```

### Child Model
```php
public function parent(){
  return $this->belongsTo(Parent::class, 'user_id', 'uuid');
}
```
