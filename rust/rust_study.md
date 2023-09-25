## 数据类型

> Rust 数据类型分为基本类型和复合类型
> 1. 数值类型：有符号整数（i8, i16, i32, i64, isize）、无符号整数（u8，u6，u32，u64，usize）、浮点数（f32，f64）、以及有理数、复数
> 2. 字符串：字符串字面量和字符串切片 **&str**
> 3. 布尔类型：true 和 false
> 4. 字符类型：表示单个 Unicode 字符，存储为四个字节
> 5. 单元类型：即()，其唯一的值也是()

## 类型推导与标注
Rust 是一门静态类型语言，在编译期知道所有变量类型，Rust 编译器可根据变量值和上下文中的使用方式自动推导变量类型。某些特殊情况下无法推导出变量类型，需要手动给予类型标注。

```rust
// 显示类型标注
let guess: i32 = "42".parse().expect("Not a number!");
let guess = "42".parse()::<i32>().expect("Not a number!");
```
1. reference and borrowing

the scopes of immutable references end where they are last used. after that new reference could be created.
```rust
let mut s = String::from("hello");

let r1 = &s; // no problem
let r2 = &s; // no problem
// let r3 = &mut s; // error
println!("{} and {}", r1, r2);
// variables r1 and r2 will not be used after this point

let r3 = &mut s; // no problem
println!("{}", r3);
```

at any given time, you can have either one mutable reference or any number of immutable references.

references must always be valid.

2. the slice type
   

