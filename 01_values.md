{{meta {docid: values}}}

# Giá trị, Kiểu dữ liệu và Toán tử

{{quote {author: "Master Yuan-Ma", title: "The Book of Programming", chapter: true}

Bên dưới bề mặt của cỗ máy, chương trình di chuyển. Không cần nỗ lực, nó mở rộng và co lại. Trong sự hài hòa tuyệt vời, các electron phân tán và tập hợp lại. Các hình dạng trên màn hình chỉ là những gợn sóng trên mặt nước. Bản chất vẫn là vô hình ở bên dưới.

quote}}

{{index "Yuan-Ma", "Book of Programming"}}

{{figure {url: "img/chapter_picture_1.jpg", alt: "Hình minh họa về một biển các chấm sáng và tối (bit) có các hòn đảo trong đó", chapter: framed}}}

{{index "binary data", data, bit, memory}}

Trong thế giới máy tính, chỉ có dữ liệu. Bạn có thể đọc dữ liệu, sửa đổi dữ liệu, tạo dữ liệu mới—nhưng những thứ không phải là dữ liệu thì không thể đề cập đến. Tất cả dữ liệu này được lưu trữ dưới dạng chuỗi bit dài và do đó về cơ bản là giống nhau.

{{index CD, signal}}

_Bit_ là bất kỳ thứ gì có hai giá trị, thường được mô tả là số không và số một. Bên trong máy tính, chúng có các dạng như điện tích cao hoặc thấp, tín hiệu mạnh hoặc yếu, hoặc một điểm sáng hoặc mờ trên bề mặt đĩa CD. Bất kỳ thông tin rời rạc nào cũng có thể được giảm xuống thành một chuỗi số không và số một và do đó được biểu diễn bằng bit.

{{index "binary number", "decimal number"}}

Ví dụ, chúng ta có thể biểu diễn số 13 theo bit. Cách này hoạt động theo cùng một cách như số thập phân, nhưng thay vì 10 chữ số khác nhau, chúng ta chỉ có 2, và trọng số của mỗi chữ số tăng theo hệ số 2 từ phải sang trái. Sau đây là các bit tạo nên số 13, với trọng số của các chữ số được hiển thị bên dưới:

```{lang: null}
   0   0   0   0   1   1   0   1
 128  64  32  16   8   4   2   1
```

Đó là số nhị phân 00001101. Các chữ số khác không của nó biểu thị cho 8, 4 và 1, và tổng bằng 13.

## Giá trị

{{index [memory, organization], "volatile data storage", "hard drive"}}

Hãy tưởng tượng một biển bit—một đại dương bit. Một máy tính hiện đại thông thường có hơn 100 tỷ bit trong bộ lưu trữ dữ liệu dễ bay hơi (bộ nhớ làm việc). Bộ lưu trữ không dễ bay hơi (ổ cứng hoặc tương đương) có xu hướng có nhiều hơn một vài cấp độ.

Để có thể làm việc với số lượng bit như vậy mà không bị mất đi, chúng ta chia chúng thành các khối biểu diễn các phần thông tin. Trong môi trường JavaScript, các khối đó được gọi là các _((giá trị))_. Mặc dù tất cả các giá trị đều được tạo thành từ bit, chúng đóng các vai trò khác nhau. Mỗi giá trị có một ((kiểu)) xác định vai trò của nó. Một số giá trị là số, một số giá trị là các phần văn bản, một số giá trị là hàm, v.v.

{{index "garbage collection"}}

Để tạo ra một giá trị, bạn chỉ cần gọi tên của nó. Điều này rất tiện lợi. Bạn không cần phải thu thập vật liệu xây dựng cho các giá trị của mình hoặc trả tiền cho chúng. Bạn chỉ cần gọi một giá trị, và _vèo_, bạn đã có nó. Tất nhiên, các giá trị không thực sự được tạo ra từ hư không. Mỗi giá trị phải được lưu trữ ở đâu đó và nếu bạn muốn sử dụng một số lượng lớn cùng một lúc, bạn có thể hết bộ nhớ máy tính. May mắn thay, đây chỉ là vấn đề nếu bạn cần tất cả chúng cùng một lúc. Ngay khi bạn không còn sử dụng một giá trị nữa, nó sẽ biến mất, để lại các bit của nó để được tái chế làm vật liệu xây dựng cho thế hệ giá trị tiếp theo.

Phần còn lại của chương này giới thiệu các thành phần nguyên tử của chương trình JavaScript, tức là các kiểu giá trị đơn giản và các toán tử có thể tác động lên các giá trị đó.

## Số

{{index [syntax, number], number, [number, notation]}}

Các giá trị của kiểu _số_, không có gì đáng ngạc nhiên, là các giá trị số. Trong một chương trình JavaScript, chúng được viết như sau:

```
13
```

{{index "binary number"}}

Sử dụng nó trong một chương trình sẽ khiến mẫu bit cho số 13 xuất hiện bên trong bộ nhớ của máy tính.

{{index [number, representation], bit}}

JavaScript sử dụng một số bit cố định, 64 bit, để lưu trữ một giá trị số duy nhất. Chỉ có một số mẫu nhất định mà bạn có thể tạo ra với 64 bit, điều này giới hạn số lượng các số khác nhau có thể được biểu diễn. Với _N_ ((chữ số) thập phân, bạn có thể biểu diễn 10^N^ số. Tương tự như vậy, với 64 chữ số nhị phân, bạn có thể biểu diễn 2^64^ số khác nhau, tức là khoảng 18 nghìn tỷ (một số 18 với 18 số không theo sau). Quá lớn.

Bộ nhớ máy tính trước đây nhỏ hơn nhiều, và mọi người có xu hướng sử dụng nhóm 8 hoặc 16 bit để biểu diễn số của họ. Thật dễ dàng để vô tình _((tràn))_ những con số nhỏ như vậy—để kết thúc bằng một con số không vừa với số bit đã cho. Ngày nay, ngay cả những máy tính vừa vặn trong túi của bạn cũng có rất nhiều bộ nhớ, vì vậy bạn có thể thoải mái sử dụng các khối 64 bit, và bạn chỉ cần lo lắng về việc tràn khi xử lý các con số thực sự lớn.

{{index sign, "floating-point number", "sign bit"}}

Tuy nhiên, không phải tất cả các số nguyên nhỏ hơn 18 nghìn tỷ đều phù hợp với số JavaScript. Các bit đó cũng lưu trữ các số âm, vì vậy một bit biểu thị dấu của số. Một vấn đề lớn hơn là biểu diễn các số không nguyên. Để làm điều này, một số bit được sử dụng để lưu trữ vị trí của dấu thập phân. Số nguyên tối đa thực tế có thể được lưu trữ nằm trong phạm vi 9 nghìn tỷ (15 số không)—vẫn là một con số lớn dễ chịu.

{{index [number, notation], "fractional number"}}

Số thập phân được viết bằng dấu chấm:

```
9.81
```

{{index exponent, "scientific notation", [number, notation]}}

Đối với các số rất lớn hoặc rất nhỏ, bạn cũng có thể sử dụng ký hiệu khoa học bằng cách thêm _e_ (cho _số mũ_), theo sau là số mũ của số đó.

```
2.998e8
```

Tức là 2.998 × 10^8^ = 299,800,000.

{{index pi, [number, "precision of"], "floating-point number"}}

Các phép tính với số tự nhiên (còn gọi là _((số nguyên))_) nhỏ hơn 9 nghìn tỷ đã đề cập ở trên được đảm bảo luôn chính xác. Thật không may, các phép tính với số phân số thường không chính xác. Cũng giống như π (pi) không thể được biểu thị chính xác bằng một số hữu hạn các chữ số thập phân, nhiều số mất đi một số độ chính xác khi chỉ có 64 bit để lưu trữ chúng. Đây là điều đáng tiếc, nhưng nó chỉ gây ra các vấn đề thực tế trong những tình huống cụ thể. Điều quan trọng là phải nhận thức được điều đó và coi các số kỹ thuật số phân số là các phép tính gần đúng, không phải là các giá trị chính xác.

### Số học

{{index [syntax, operator], operator, "binary operator", arithmetic, addition, multiplication}}

Điều chủ yếu cần làm với các con số là thực hiện số học. Các phép toán số học như phép cộng hoặc phép nhân lấy hai giá trị số và tạo ra một số mới từ chúng. Đây là những gì chúng trông như thế nào trong JavaScript:

```{meta: "expr"}
100 + 4 * 11
```

{{index [operator, application], asterisk, "plus character", "* operator", "+ operator"}}

Các ký hiệu `+` và `*` được gọi là _toán tử_. Ký hiệu đầu tiên dùng để cộng và ký hiệu thứ hai dùng để nhân. Đặt một toán tử giữa hai giá trị sẽ áp dụng toán tử đó cho các giá trị đó và tạo ra một giá trị mới.

{{index grouping, parentheses, precedence}}

Liệu ví dụ này có nghĩa là "Cộng 4 và 100, rồi nhân kết quả với 11", hay phép nhân được thực hiện trước phép cộng? Như bạn có thể đoán, phép nhân xảy ra trước. Giống như trong toán học, bạn có thể thay đổi điều này bằng cách đặt phép cộng trong dấu ngoặc đơn.

```{meta: "expr"}
(100 + 4) * 11
```

{{index "hyphen character", "slash character", division, subtraction, minus, "- operator", "/ operator"}}

Đối với phép trừ, có toán tử `-`. Phép chia có thể được thực hiện bằng toán tử `/`.

Khi các toán tử xuất hiện cùng nhau mà không có dấu ngoặc đơn, thứ tự áp dụng của chúng được xác định bởi _((thứ tự ưu tiên))_ của các toán tử. Ví dụ cho thấy phép nhân đứng trước phép cộng. Toán tử `/` có cùng thứ tự ưu tiên với `*`. Tương tự như vậy, `+` và `-` có cùng thứ tự ưu tiên. Khi nhiều toán tử có cùng thứ tự ưu tiên xuất hiện cạnh nhau, như trong `1 - 2 + 1`, chúng sẽ được áp dụng từ trái sang phải: `(1 - 2) + 1`.

Đừng lo lắng quá nhiều về các quy tắc ưu tiên này. Nếu còn nghi ngờ, chỉ cần thêm dấu ngoặc đơn.

{{index "modulo operator", division, "remainder operator", "% operator"}}

Có một toán tử số học nữa mà bạn có thể không nhận ra ngay. Ký hiệu `%` được sử dụng để biểu diễn phép toán _phần dư_. `X % Y` là phần dư của phép chia `X` cho `Y`. Ví dụ, `314 % 100` tạo ra `14`, và `144 % 12` tạo ra `0`. Thứ tự ưu tiên của toán tử phần dư giống như phép nhân và phép chia. Bạn cũng thường thấy toán tử này được gọi là _modulo_ (chia lấy dư).

### Special numbers

{{index [number, "special values"], infinity}}

Có ba giá trị đặc biệt trong JavaScript được coi là số nhưng không hoạt động như số bình thường. Hai giá trị đầu tiên là `Infinity` và `-Infinity`, biểu diễn vô cực dương và âm. `Infinity - 1` vẫn là `Infinity`, v.v. Tuy nhiên, đừng quá tin tưởng vào phép tính dựa trên vô cực. Về mặt toán học, nó không hợp lý và sẽ nhanh chóng dẫn đến số đặc biệt tiếp theo: `NaN`.

{{index NaN, "not a number", "division by zero"}}

`NaN` có nghĩa là "không phải là số", mặc dù nó _là_ giá trị của kiểu số. Bạn sẽ nhận được kết quả này khi bạn, ví dụ, cố gắng tính toán `0 / 0` (số không chia cho số không), `Vô cực - Vô cực` hoặc bất kỳ số lượng phép toán số nào khác không tạo ra kết quả có nghĩa.

## Chuỗi

{{indexsee "grave accent", backtick}}

{{index [syntax, string], text, character, [string, notation], "single-quote character", "double-quote character", "quotation mark", backtick}}

Kiểu dữ liệu cơ bản tiếp theo là _((chuỗi)) (string)_. Chuỗi được sử dụng để biểu diễn văn bản. Chúng được viết bằng cách đặt nội dung của chúng trong dấu ngoặc kép.

```
`Down on the sea`
"Lie on the ocean"
'Float on the ocean'
```

Bạn có thể sử dụng dấu ngoặc đơn, dấu ngoặc kép hoặc dấu ngoặc kép ngược để đánh dấu chuỗi, miễn là dấu ngoặc kép ở đầu và cuối chuỗi khớp với nhau.

{{index "line break", "newline character"}}

Bạn có thể đặt hầu như bất kỳ thứ gì giữa các dấu ngoặc kép để JavaScript tạo ra một giá trị chuỗi từ nó. Nhưng một vài ký tự thì khó hơn. Bạn có thể tưởng tượng việc đặt dấu ngoặc kép giữa các dấu ngoặc kép có thể khó như thế nào, vì chúng sẽ trông giống như phần cuối của chuỗi. _Dòng mới_ (các ký tự bạn nhận được khi nhấn [enter]{keyname}) chỉ có thể được bao gồm khi chuỗi được trích dẫn bằng dấu ngoặc kép ngược (`` ` ``).

{{index [escaping, "in strings"], ["backslash character", "in strings"]}}

Đeể có thể đưa các ký tự như vậy vào một chuỗi, ký hiệu sau được sử dụng: một dấu gạch chéo ngược (`\`) bên trong văn bản được trích dẫn chỉ ra rằng ký tự sau nó có một ý nghĩa đặc biệt. Điều này được gọi là _thoát_ ký tự. Một dấu ngoặc kép được đặt trước bởi một dấu gạch chéo ngược sẽ không kết thúc chuỗi mà là một phần của chuỗi. Khi một ký tự `n` xuất hiện sau một dấu gạch chéo ngược, nó được hiểu là một dòng mới. Tương tự, một dấu `t` sau một dấu gạch chéo ngược có nghĩa là một ((ký tự tab)). Lấy ví dụ chuỗi sau:

```
"Đây là dòng đầu tiên\nVà đây là dòng thứ hai"
```

Đây là văn bản thực tế trong chuỗi đó:

```{lang: null}
Đây là dòng đầu tiên
Và đây là dòng thứ hai
```

Tất nhiên, có những trường hợp bạn muốn dấu gạch chéo ngược trong chuỗi chỉ là một dấu gạch chéo, không phải là một mã đặc biệt. Nếu hai dấu gạch chéo ngược đi liền nhau, chúng sẽ triệt tiêu nhau và chỉ còn lại một dấu gạch chéo trong giá trị chuỗi kết quả. Đây là cách chuỗi "_Một ký tự xuống dòng được viết như thế này `"`\n`"`._" có thể được diễn đạt:

```
"Một ký tự xuống dòng được viết như thế này \"\\n\"."
```

{{id unicode}}

{{index [string, representation], Unicode, character}}

Strings, too, have to be modeled as a series of bits to be able to exist inside the computer. The way JavaScript does this is based on the _((Unicode))_ standard. This standard assigns a number to virtually every character you would ever need, including characters from Greek, Arabic, Japanese, Armenian, and so on. If we have a number for every character, a string can be described by a sequence of numbers. And that's what JavaScript does.

{{index "UTF-16", emoji}}

There's a complication though: JavaScript's representation uses 16 bits per string element, which can describe up to 2^16^ different characters. However, Unicode defines more characters than that—about twice as many, at this point. So some characters, such as many emoji, take up two "character positions" in JavaScript strings. We'll come back to this in [Chapter ?](higher_order#code_units).

{{index "+ operator", concatenation}}

Strings cannot be divided, multiplied, or subtracted. The `+` operator _can_ be used on them, not to add, but to _concatenate_—to glue two strings together. The following line will produce the string `"concatenate"`:

```{meta: "expr"}
"con" + "cat" + "e" + "nate"
```

String values have a number of associated functions (_methods_) that can be used to perform other operations on them. I'll say more about these in [Chapter ?](data#methods).

{{index interpolation, backtick}}

Strings written with single or double quotes behave very much the same—the only difference lies in which type of quote you need to escape inside of them. Backtick-quoted strings, usually called _((template literals))_, can do a few more tricks. Apart from being able to span lines, they can also embed other values.

```{meta: "expr"}
`half of 100 is ${100 / 2}`
```

When you write something inside `${}` in a template literal, its result will be computed, converted to a string, and included at that position. This example produces the string `"half of 100 is 50"`.

## Unary operators

{{index operator, "typeof operator", type}}

Not all operators are symbols. Some are written as words. One example is the `typeof` operator, which produces a string value naming the type of the value you give it.

```
console.log(typeof 4.5)
// → number
console.log(typeof "x")
// → string
```

{{index "console.log", output, "JavaScript console"}}

{{id "console.log"}}

We will use `console.log` in example code to indicate that we want to see the result of evaluating something. (More about that in the [next chapter](program_structure).)

{{index negation, "- operator", "binary operator", "unary operator"}}

The other operators shown so far in this chapter all operated on two values, but `typeof` takes only one. Operators that use two values are called _binary_ operators, while those that take one are called _unary_ operators. The minus operator (`-`) can be used both as a binary operator and as a unary operator.

```
console.log(- (10 - 2))
// → -8
```

## Boolean values

{{index Boolean, operator, true, false, bit}}

It is often useful to have a value that distinguishes between only two possibilities, like "yes" and "no" or "on" and "off". For this purpose, JavaScript has a _Boolean_ type, which has just two values, true and false, written as those words.

### Comparison

{{index comparison}}

Here is one way to produce Boolean values:

```
console.log(3 > 2)
// → true
console.log(3 < 2)
// → false
```

{{index [comparison, "of numbers"], "> operator", "< operator", "greater than", "less than"}}

The `>` and `<` signs are the traditional symbols for "is greater than" and "is less than", respectively. They are binary operators. Applying them results in a Boolean value that indicates whether they hold true in this case.

Strings can be compared in the same way.

```
console.log("Aardvark" < "Zoroaster")
// → true
```

{{index [comparison, "of strings"]}}

The way strings are ordered is roughly alphabetic but not really what you'd expect to see in a dictionary: uppercase letters are always "less" than lowercase ones, so `"Z" < "a"`, and nonalphabetic characters (!, -, and so on) are also included in the ordering. When comparing strings, JavaScript goes over the characters from left to right, comparing the ((Unicode)) codes one by one.

{{index equality, ">= operator", "<= operator", "== operator", "!= operator"}}

Other similar operators are `>=` (greater than or equal to), `<=` (less than or equal to), `==` (equal to), and `!=` (not equal to).

```
console.log("Garnet" != "Ruby")
// → true
console.log("Pearl" == "Amethyst")
// → false
```

{{index [comparison, "of NaN"], NaN}}

There is only one value in JavaScript that is not equal to itself, and that is `NaN` ("not a number").

```
console.log(NaN == NaN)
// → false
```

`NaN` is supposed to denote the result of a nonsensical computation, and as such, it isn't equal to the result of any _other_ nonsensical computations.

### Logical operators

{{index reasoning, "logical operators"}}

There are also some operations that can be applied to Boolean values themselves. JavaScript supports three logical operators: _and_, _or_, and _not_. These can be used to "reason" about Booleans.

{{index "&& operator", "logical and"}}

The `&&` operator represents logical _and_. It is a binary operator, and its result is true only if both the values given to it are true.

```
console.log(true && false)
// → false
console.log(true && true)
// → true
```

{{index "|| operator", "logical or"}}

The `||` operator denotes logical _or_. It produces true if either of the values given to it is true.

```
console.log(false || true)
// → true
console.log(false || false)
// → false
```

{{index negation, "! operator"}}

_Not_ is written as an exclamation mark (`!`). It is a unary operator that flips the value given to it—`!true` produces `false` and `!false` gives `true`.

{{index precedence}}

When mixing these Boolean operators with arithmetic and other operators, it is not always obvious when parentheses are needed. In practice, you can usually get by with knowing that of the operators we have seen so far, `||` has the lowest precedence, then comes `&&`, then the comparison operators (`>`, `==`, and so on), and then the rest. This order has been chosen such that, in typical expressions like the following one, as few parentheses as possible are necessary:

```{meta: "expr"}
1 + 1 == 2 && 10 * 10 > 50
```

{{index "conditional execution", "ternary operator", "?: operator", "conditional operator", "colon character", "question mark"}}

The last logical operator we will look at is not unary, not binary, but _ternary_, operating on three values. It is written with a question mark and a colon, like this:

```
console.log(true ? 1 : 2);
// → 1
console.log(false ? 1 : 2);
// → 2
```

This one is called the _conditional_ operator (or sometimes just _the ternary operator_ since it is the only such operator in the language). The operator uses the value to the left of the question mark to decide which of the two other values to "pick". If you write `a ? b : c`, the result will be `b` when `a` is true and `c` otherwise.

## Empty values

{{index undefined, null}}

There are two special values, written `null` and `undefined`, that are used to denote the absence of a _meaningful_ value. They are themselves values, but they carry no information.

Many operations in the language that don't produce a meaningful value yield `undefined` simply because they have to yield _some_ value.

The difference in meaning between `undefined` and `null` is an accident of JavaScript's design, and it doesn't matter most of the time. In cases where you actually have to concern yourself with these values, I recommend treating them as mostly interchangeable.

## Automatic type conversion

{{index NaN, "type coercion"}}

In the [introduction](intro), I mentioned that JavaScript goes out of its way to accept almost any program you give it, even programs that do odd things. This is nicely demonstrated by the following expressions:

```
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```

{{index "+ operator", arithmetic, "* operator", "- operator"}}

When an operator is applied to the "wrong" type of value, JavaScript will quietly convert that value to the type it needs, using a set of rules that often aren't what you want or expect. This is called _((type coercion))_. The `null` in the first expression becomes `0` and the `"5"` in the second expression becomes `5` (from string to number). Yet in the third expression, `+` tries string concatenation before numeric addition, so the `1` is converted to `"1"` (from number to string).

{{index "type coercion", [number, "conversion to"]}}

When something that doesn't map to a number in an obvious way (such as `"five"` or `undefined`) is converted to a number, you get the value `NaN`. Further arithmetic operations on `NaN` keep producing `NaN`, so if you find yourself getting one of those in an unexpected place, look for accidental type conversions.

{{index null, undefined, [comparison, "of undefined values"], "== operator"}}

When comparing values of the same type using the `==` operator, the outcome is easy to predict: you should get true when both values are the same, except in the case of `NaN`. But when the types differ, JavaScript uses a complicated and confusing set of rules to determine what to do. In most cases, it just tries to convert one of the values to the other value's type. However, when `null` or `undefined` occurs on either side of the operator, it produces true only if both sides are one of `null` or `undefined`.

```
console.log(null == undefined);
// → true
console.log(null == 0);
// → false
```

That behavior is often useful. When you want to test whether a value has a real value instead of `null` or `undefined`, you can compare it to `null` with the `==` or `!=` operator.

{{index "type coercion", [Boolean, "conversion to"], "=== operator", "!== operator", comparison}}

What if you want to test whether something refers to the precise value `false`? Expressions like `0 == false` and `"" == false` are also true because of automatic type conversion. When you do _not_ want any type conversions to happen, there are two additional operators: `===` and `!==`. The first tests whether a value is _precisely_ equal to the other, and the second tests whether it is not precisely equal. Thus `"" === false` is false, as expected.

I recommend using the three-character comparison operators defensively to prevent unexpected type conversions from tripping you up. But when you're certain the types on both sides will be the same, there is no problem with using the shorter operators.

### Short-circuiting of logical operators

{{index "type coercion", [Boolean, "conversion to"], operator}}

The logical operators `&&` and `||` handle values of different types in a peculiar way. They will convert the value on their left side to Boolean type in order to decide what to do, but depending on the operator and the result of that conversion, they will return either the _original_ left-hand value or the right-hand value.

{{index "|| operator"}}

The `||` operator, for example, will return the value to its left when that value can be converted to true and will return the value on its right otherwise. This has the expected effect when the values are Boolean and does something analogous for values of other types.

```
console.log(null || "user")
// → user
console.log("Agnes" || "user")
// → Agnes
```

{{index "default value"}}

We can use this functionality as a way to fall back on a default value. If you have a value that might be empty, you can put `||` after it with a replacement value. If the initial value can be converted to false, you'll get the replacement instead. The rules for converting strings and numbers to Boolean values state that `0`, `NaN`, and the empty string (`""`) count as false, while all the other values count as true. That means `0 || -1` produces `-1`, and `"" || "!?"` yields `"!?"`.

{{index "?? operator", null, undefined}}

The `??` operator resembles `||` but returns the value on the right only if the one on the left is `null` or `undefined`, not if it is some other value that can be converted to `false`. Often, this is preferable to the behavior of `||`.

```
console.log(0 || 100);
// → 100
console.log(0 ?? 100);
// → 0
console.log(null ?? 100);
// → 100
```

{{index "&& operator"}}

The `&&` operator works similarly but the other way around. When the value to its left is something that converts to false, it returns that value, and otherwise it returns the value on its right.

Another important property of these two operators is that the part to their right is evaluated only when necessary. In the case of `true || X`, no matter what `X` is—even if it's a piece of program that does something _terrible_—the result will be true, and `X` is never evaluated. The same goes for `false && X`, which is false and will ignore `X`. This is called _((short-circuit evaluation))_.

{{index "ternary operator", "?: operator", "conditional operator"}}

The conditional operator works in a similar way. Of the second and third values, only the one that is selected is evaluated.

## Summary

We looked at four types of JavaScript values in this chapter: numbers, strings, Booleans, and undefined values. Such values are created by typing in their name (`true`, `null`) or value (`13`, `"abc"`).

You can combine and transform values with operators. We saw binary operators for arithmetic (`+`, `-`, `*`, `/`, and `%`), string concatenation (`+`), comparison (`==`, `!=`, `===`, `!==`, `<`, `>`, `<=`, `>=`), and logic (`&&`, `||`, `??`), as well as several unary operators (`-` to negate a number, `!` to negate logically, and `typeof` to find a value's type) and a ternary operator (`?:`) to pick one of two values based on a third value.

This gives you enough information to use JavaScript as a pocket calculator but not much more. The [next chapter](program_structure) will start tying these expressions together into basic programs.