# QuerySet

- 缓存

  使用缓存,sql只执行一次

  ```
  books = Books.objects.filter(pk=92378).first()
  print(books.name)
  print(books.price)  
  ```

  调用属性时不会使用缓存,每次都会访问数据库

  ```
  books = Books.objects.filter(pk__gt=900000)
  print(books.filter(pk=900001))
  print(books.filter(pk=900001))  // 再次执行sql
  ```

  

- 切片

  等价于sql使用`offset 20, limit 10`

  ```
  books = Books.objects.all()
  print(books[20: 30])
  ```

  

