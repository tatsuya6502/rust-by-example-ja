<!-- Multiple bounds can be applied with a `+`. Like normal, different types are
separated with `,`. -->
`+`を用いて複数のトレイト境界を設けることができます。複数の引数を受け取るときは、通常時と同様、`,`で区切ります。

``` rust,editable
use std::fmt::{Debug, Display};

fn compare_prints<T: Debug + Display>(t: &T) {
    println!("Debug: `{:?}`", t);
    println!("Display: `{}`", t);
}

fn compare_types<T: Debug, U: Debug>(t: &T, u: &U) {
    println!("t: `{:?}", t);
    println!("u: `{:?}", u);
}

fn main() {
    let string = "words";
    let array = [1, 2, 3];
    let vec = vec![1, 2, 3];

    compare_prints(&string);
    //compare_prints(&array);
    // TODO ^ ここをアンコメントしてみましょう。

    compare_types(&array, &vec);
}

```

### See also:

[`std::fmt`][fmt], [トレイト][traits]

[fmt]: ../hello/print.html
[traits]: ../trait.html