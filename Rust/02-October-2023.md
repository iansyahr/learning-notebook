# 02 October 2023

### 5 Better ways to code in Rust

- rust-analyzer <= important
- codelldb <=important
- even better toml <= important
- Error Lens <= important
- Todo Tree

```rust
fn calculate_sum(numbers: &[i32]) -> Result<i32, String> {
    let mut sum = 0;
    for num in numbers.iter().cloned() {
        sum += num
    }

    Ok(sum)
}

fn main() {
    let numbers = vec![1, 2, 3, 4, 5];
    let sum = calculate_sum(&numbers).unwrap();
    println!("Sum:{}", sum);
}
```

```rust
fn calculate_sum(numbers: &[i32]) -> Result<i32, String> {
    let sum = numbers.iter().sum();
    Ok(sum)
}

fn main() {
    let numbers = vec![1, 2, 3, 4, 5];
    match calculate_sum(&numbers) {
        Ok(sum) => println!("Sum: {}", sum),
        Err(err) => eprintln!("Error:{}", err),
    }
}

```

```rust
use rayon::prelude::*;

fn calculate_sum(numbers: &[i32]) -> Result<i32, String> {
    let sum = numbers.par_iter().sum();
    Ok(sum)
}

fn main() {
    let numbers = vec![1, 2, 3, 4, 5];
    match calculate_sum(&numbers) {
        Ok(sum) => println!("Sum: {}", sum),
        Err(err) => eprintln!("Error:{}", err),
    }
}
```

### Apa itu Iterator

Iterator dalam Rust bertanggung jawab untuk membuat urutan nilai dan memungkinkan kita untuk mengulangi setiap item dari urutan tersebut. Iterator ini digunakan terutama untuk perulangan dan kita hanya bisa melakukan perulangan melalui iterator di Rust. Berikut adalah contoh sederhana tentang bagaimana kita bisa melakukan perulangan melalui sebuah array:

```rust
fn main() {
    let numbers = [2, 1, 17, 99, 34, 56];
    // iterator
    let numbers_iterator = numbers.iter();
    for number in numbers_iterator {
        println!("{}", number);
    }
}

```

### tO-dO

- ~~assert_eq!~~
- ~~apa itu type~~
- ~~apa tu struct~~
- ~~apa itu impl~~
- ~~apa itu enum~~
- match Some None -> move to next day
- Result Options -> move to next day
