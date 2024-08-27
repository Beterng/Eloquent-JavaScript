{{meta {docid: values}}}

# Giá trị, Kiểu dữ liệu và Toán tử

{{quote {author: "Master Yuan-Ma", title: "The Book of Programming", chapter: true}

Bên dưới bề mặt của cỗ máy, chương trình di chuyển. Không cần nỗ lực, nó mở rộng và co lại. Trong sự hài hòa tuyệt vời, các electron phân tán và tập hợp lại. Các hình dạng trên màn hình chỉ là những gợn sóng trên mặt nước. Bản chất vẫn là vô hình ở bên dưới.

quote}}

{{index "Yuan-Ma", "Book of Programming"}}

{{figure {url: "img/chapter_picture_1.jpg", alt: "Hình minh họa về một biển các chấm sáng và tối (bit) có các hòn đảo trong đó", chapter: framed}}}

{{index "binary data", data, bit, memory}}

Trong thế giới máy tính, chỉ có dữ liệu. Bạn có thể đọc dữ liệu, sửa đổi dữ liệu, tạo dữ liệu mới—nhưng những thứ không phải là dữ liệu thì sẽ không được đề cập đến. Tất cả dữ liệu này được lưu trữ dưới dạng chuỗi bit dài và do đó về cơ bản là giống nhau.

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

Hãy tưởng tượng một biển bit—một đại dương bit. Một máy tính hiện đại thông thường có hơn 100 tỷ bit trong bộ lưu trữ dữ liệu dễ bay hơi (bộ nhớ làm việc). Bộ lưu trữ không dễ bay hơi (ổ cứng hoặc tương đương) có xu hướng có nhiều hơn một vài mức độ.

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

JavaScript sử dụng một số bit cố định, 64 bit, để lưu trữ một giá trị số duy nhất. Chỉ có một số mẫu nhất định mà bạn có thể tạo ra với 64 bit, điều này giới hạn số lượng các số khác nhau có thể được biểu diễn. Với _N_ ((chữ số)) thập phân, bạn có thể biểu diễn 10^N^ số. Tương tự như vậy, với 64 chữ số nhị phân, bạn có thể biểu diễn 2^64^ số khác nhau, tức là khoảng 18 nghìn tỷ (một số 18 với 18 số không theo sau). Quá lớn.

Bộ nhớ máy tính trước đây nhỏ hơn nhiều, và mọi người có xu hướng sử dụng các nhóm 8 hoặc 16 bit để biểu diễn số của họ. Thật dễ dàng để vô tình _((tràn))_ những con số nhỏ như vậy—để kết thúc bằng một con số không vừa với số bit đã cho. Ngày nay, ngay cả những máy tính vừa vặn trong túi của bạn cũng có rất nhiều bộ nhớ, vì vậy bạn có thể thoải mái sử dụng các khối 64 bit, và bạn chỉ cần lo lắng về việc tràn khi xử lý các con số thực sự lớn.

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

### Các số đặc biệt

{{index [number, "special values"], infinity}}

Có ba giá trị đặc biệt trong JavaScript được coi là số nhưng không hoạt động như số bình thường. Hai giá trị đầu tiên là `Infinity` và `-Infinity`, biểu diễn vô cực dương và âm. `Infinity - 1` vẫn là `Infinity`, v.v. Tuy nhiên, đừng quá tin tưởng vào phép tính dựa trên vô cực. Về mặt toán học, nó không hợp lý và sẽ nhanh chóng dẫn đến số đặc biệt tiếp theo: `NaN`.

{{index NaN, "not a number", "division by zero"}}

`NaN` có nghĩa là "không phải là số", mặc dù nó _là_ giá trị của kiểu số. Bạn sẽ nhận được kết quả này khi bạn, ví dụ, cố gắng tính toán `0 / 0` (số không chia cho số không), `Vô cực - Vô cực` hoặc bất kỳ số lượng phép toán số nào khác không tạo ra kết quả có nghĩa.

## Chuỗi

{{indexsee "grave accent", backtick}}

{{index [syntax, string], text, character, [string, notation], "single-quote character", "double-quote character", "quotation mark", backtick}}

Kiểu dữ liệu cơ bản tiếp theo là _((chuỗi)) (string)_. Chuỗi được sử dụng để biểu diễn văn bản. Chúng được viết bằng cách đặt nội dung của chúng trong dấu ngoặc kép.

```
`Xuống dưới biển sâu`
"Nằm trên sóng trôi"
'Trôi giữa biển khơi'
```

Bạn có thể sử dụng dấu ngoặc đơn, dấu ngoặc kép hoặc dấu ngoặc kép ngược để đánh dấu chuỗi, miễn là dấu ngoặc kép ở đầu và cuối chuỗi khớp với nhau.

{{index "line break", "newline character"}}

Bạn có thể đặt hầu như bất kỳ thứ gì giữa các dấu ngoặc kép để JavaScript tạo ra một giá trị chuỗi từ nó. Nhưng một vài ký tự thì khó hơn. Bạn có thể tưởng tượng việc đặt dấu ngoặc kép giữa các dấu ngoặc kép có thể khó như thế nào, vì chúng sẽ trông giống như phần cuối của chuỗi. _Dòng mới_ (các ký tự bạn nhận được khi nhấn [enter]{keyname}) chỉ có thể được bao gồm khi chuỗi được trích dẫn bằng dấu ngoặc kép ngược (`` ` ``).

{{index [escaping, "in strings"], ["backslash character", "in strings"]}}

Để có thể đưa các ký tự như vậy vào một chuỗi, ký hiệu sau được sử dụng: một dấu gạch chéo ngược (`\`) bên trong văn bản được trích dẫn chỉ ra rằng ký tự sau nó có một ý nghĩa đặc biệt. Việc này được gọi là _thoát_ ký tự. Một dấu ngoặc kép được đặt trước bởi một dấu gạch chéo ngược sẽ không kết thúc chuỗi mà là một phần của chuỗi. Khi một ký tự `n` xuất hiện sau một dấu gạch chéo ngược, nó được hiểu là một dòng mới. Tương tự, một dấu `t` sau một dấu gạch chéo ngược có nghĩa là một ((ký tự tab)). Lấy ví dụ chuỗi sau:

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

Các chuỗi cũng phải được mô hình hóa thành một chuỗi bit để có thể tồn tại bên trong máy tính. Cách JavaScript thực hiện điều này dựa trên tiêu chuẩn _((Unicode))_. Tiêu chuẩn này gán một con số cho hầu hết mọi ký tự mà bạn cần, bao gồm các ký tự từ tiếng Hy Lạp, tiếng Ả Rập, tiếng Nhật, tiếng Armenia, tiếng Việt, v.v. Nếu chúng ta có một số cho mỗi ký tự thì một chuỗi có thể được mô tả bằng một dãy số. Và đó là những gì JavaScript làm.

{{index "UTF-16", emoji}}

Tuy nhiên, có một điều phức tạp: cách biểu diễn của JavaScript sử dụng 16 bit cho mỗi phần tử chuỗi, tức là có thể mô tả tối đa 2^16^ ký tự khác nhau. Tuy nhiên, Unicode lại định nghĩa nhiều ký tự hơn thế—hiện tại, có nhiều ký tự chiếm khoảng gấp đôi. Vì vậy, một số ký tự, chẳng hạn như nhiều biểu tượng cảm xúc, chiếm hai "vị trí ký tự" trong chuỗi JavaScript. Chúng ta sẽ quay lại vấn đề này trong [Chương ?](higher_order#code_units).

{{index "+ operator", concatenation}}

Chuỗi không thể được đem đi chia, nhân hoặc trừ. Toán tử `+` _có thể_ được sử dụng trên chúng, không phải để cộng thêm mà để _nối_—để gắn hai chuỗi lại với nhau. Dòng sau sẽ tạo ra chuỗi `"nốichuỗi"`:

```{meta: "expr"}
"nối" + "ch" + "u" + "ỗi"
```

Các giá trị chuỗi có đi kèm thêm một số hàm (_phương thức_) có thể được sử dụng để thực hiện các thao tác khác trên chúng. Tôi sẽ nói thêm về những điều này trong [Chương ?](data#methods).

{{index interpolation, backtick}}

Các chuỗi được viết bằng dấu ngoặc đơn hoặc dấu ngoặc kép hoạt động rất giống nhau—sự khác biệt duy nhất nằm ở kiểu dấu ngoặc kép mà bạn cần thoát bên trong chúng. Các chuỗi có dấu ngoặc ngược, thường được gọi là _((chữ mẫu))_, có thể thực hiện thêm một số thủ thuật. Ngoài khả năng kéo dài các dòng, chúng còn có thể nhúng các giá trị khác.

```{meta: "expr"}
`một nửa của 100 là ${100 / 2}`
```

Khi bạn viết nội dung nào đó bên trong `${}` theo dạng chữ mẫu, kết quả của nó sẽ được tính toán, chuyển đổi thành chuỗi và được đưa vào vị trí đó. Ví dụ này tạo ra chuỗi `"một nửa của 100 là 50"`.

## Toán tử một ngôi

{{index operator, "typeof operator", type}}

Không phải tất cả các toán tử đều là ký hiệu. Một số được viết dưới dạng từ. Một ví dụ là toán tử `typeof`, toán tử này tạo ra một giá trị chuỗi là tên được đặt cho kiểu giá trị bạn cung cấp cho nó.

```
console.log(typeof 4.5)
// → number
console.log(typeof "x")
// → string
```

{{index "console.log", output, "JavaScript console"}}

{{id "console.log"}}

Chúng ta sẽ sử dụng `console.log` trong mã ví dụ để cho biết rằng chúng ta muốn xem kết quả của việc tính toán một cái gì đó. (Thêm về điều đó trong [chương tiếp theo](program_structure).)

{{index negation, "- operator", "binary operator", "unary operator"}}

Các toán tử được trình bày trong chương này đều hoạt động trên hai giá trị, nhưng `typeof` chỉ nhận một giá trị. Các toán tử sử dụng hai giá trị được gọi là toán tử _hai ngôi_, trong khi các toán tử lấy một giá trị được gọi là toán tử _một ngôi_. Toán tử trừ (`-`) có thể được sử dụng làm toán tử hai ngôi và toán tử một ngôi.

```
console.log(- (10 - 2))
// → -8
```

## Giá trị Boolean

{{index Boolean, operator, true, false, bit}}

Thông thường sẽ rất hữu ích khi có một giá trị chỉ phân biệt giữa hai khả năng, như "có" và "không" hoặc "bật" và "tắt". Với mục đích này, JavaScript có kiểu _Boolean_ (đúng sai) chỉ có hai giá trị, true (đúng) và false (sai), được viết dưới dạng những từ đó.

### So sánh

{{index comparison}}

Đây là một cách để tạo ra các giá trị Boolean:

```
console.log(3 > 2)
// → true
console.log(3 < 2)
// → false
```

{{index [comparison, "of numbers"], "> operator", "< operator", "greater than", "less than"}}

Các dấu `>` và `<` lần lượt là các ký hiệu truyền thống cho "lớn hơn" và "nhỏ hơn". Chúng là các toán tử nhị phân. Việc áp dụng chúng sẽ tạo ra giá trị Boolean cho biết liệu chúng có đúng trong trường hợp này hay không.

Các chuỗi cũng có thể được so sánh theo cách tương tự.

```
console.log("Angiang" < "Yenbai")
// → true
```

{{index [comparison, "of strings"]}}

Cách sắp xếp các chuỗi gần như theo thứ tự chữ cái nhưng nó không thực sự như những gì bạn thấy trong từ điển: các chữ cái viết hoa luôn "nhỏ hơn" các chữ cái viết thường, vì vậy `"Z" < "a"` và các ký tự không phải chữ cái (!, -, v.v.) cũng được bao gồm trong thứ tự. Khi so sánh các chuỗi, JavaScript sẽ duyệt qua các ký tự từ trái sang phải, so sánh từng mã ((Unicode)) theo từng ký tự một.

{{index equality, ">= operator", "<= operator", "== operator", "!= operator"}}

Các toán tử tương tự khác bao gồm `>=` (lớn hơn hoặc bằng), `<=` (nhỏ hơn hoặc bằng), `==` (bằng) và `!=` (không bằng).

```
console.log("Vangbac" != "Chaubau")
// → true
console.log("Banhchung" == "Banhgiay")
// → false
```

{{index [comparison, "of NaN"], NaN}}

Chỉ có một giá trị trong JavaScript không bằng chính nó và đó là `NaN` ("không phải là số").

```
console.log(NaN == NaN)
// → false
```

`NaN` được coi là biểu thị kết quả của một phép tính vô nghĩa và do đó, nó không bằng kết quả của bất kỳ phép tính vô nghĩa _khác_ nào.

### Toán tử logic

{{index reasoning, "logical operators"}}

Ngoài ra còn có một số thao tác có thể được áp dụng cho chính các giá trị Boolean. JavaScript hỗ trợ ba toán tử logic: _và_, _hoặc_ và _trái_. Chúng có thể được sử dụng để "lý luận" về Booleans.

{{index "&& operator", "logical and"}}

Toán tử `&&` biểu thị logic _và_. Nó là một toán tử hai ngôi và kết quả của nó chỉ đúng nếu cả hai giá trị được cung cấp cho nó đều đúng.

```
console.log(true && false)
// → false
console.log(true && true)
// → true
```

{{index "|| operator", "logical or"}}

Toán tử `||` biểu thị logic _hoặc_. Nó tạo ra true nếu một trong hai giá trị được cung cấp cho nó là true.

```
console.log(false || true)
// → true
console.log(false || false)
// → false
```

{{index negation, "! operator"}}

_Trái_ được viết dưới dạng dấu chấm than (`!`). Nó là một toán tử một ngôi lật giá trị được gán cho nó—`!true` tạo ra `false` và `!false` cho ra `true`.

{{index precedence}}

Khi xen lẫn các toán tử Boolean này với các toán tử số học và các toán tử khác, không phải lúc nào cũng rõ ràng khi cần đến dấu ngoặc đơn. Trong thực tế, bạn thường có thể hiểu được rằng trong số các toán tử mà chúng ta đã thấy cho đến nay, `||` có mức độ ưu tiên thấp nhất, sau đó đến `&&`, sau đó đến các toán tử so sánh (`>`, `==`, và vân vân), và sau đó là phần còn lại. Thứ tự này đã được chọn sao cho, trong các biểu thức điển hình như biểu thức sau đây, càng cần ít dấu ngoặc đơn càng tốt:

```{meta: "expr"}
1 + 1 == 2 && 10 * 10 > 50
```

{{index "conditional execution", "ternary operator", "?: operator", "conditional operator", "colon character", "question mark"}}

Toán tử logic cuối cùng mà chúng ta sẽ xem xét không phải là toán tử một ngôi, không phải hai ngôi, mà là _ba ngôi_, hoạt động trên ba giá trị. Nó được viết bằng dấu chấm hỏi và dấu hai chấm như thế này:

```
console.log(true ? 1 : 2);
// → 1
console.log(false ? 1 : 2);
// → 2
```

Thao tác được gọi là toán tử _điều kiện_ (hoặc đôi khi chỉ là _toán tử ba ngôi_ vì đây là toán tử duy nhất như vậy trong ngôn ngữ). Toán tử sử dụng giá trị ở bên trái dấu chấm hỏi để quyết định "chọn" giá trị nào trong hai giá trị còn lại. Nếu bạn viết `a ? b : c`, kết quả sẽ là `b` khi `a` đúng và `c` ngược lại.

## Giá trị trống rỗng

{{index undefined, null}}

Có hai giá trị đặc biệt, được viết là `null` (vô giá trị) và `undefined` (không xác định), được sử dụng để biểu thị sự vắng mặt của giá trị _có nghĩa_. Bản thân chúng là những giá trị nhưng chúng không mang thông tin.

Nhiều thao tác trong ngôn ngữ không tạo ra giá trị có nghĩa trả về `undefined` đơn giản vì chúng phải trả về giá trị _gì đó_.

Sự khác biệt về ý nghĩa giữa `undefined` và `null` là một tai nạn tình cờ trong thiết kế của JavaScript và hầu như không đáng để bận tâm. Trong trường hợp bạn thực sự phải quan tâm đến những giá trị này, tôi khuyên bạn nên coi chúng hầu như có thể thay thế cho nhau.

## Tự động chuyển đổi kiểu dữ liệu

{{index NaN, "type coercion"}}

Trong phần [giới thiệu](intro), tôi đã đề cập rằng JavaScript không thể chấp nhận hầu hết mọi chương trình bạn cung cấp cho nó, ngay cả những chương trình thực hiện những điều kỳ quặc. Điều này được thể hiện rõ ràng bằng các biểu thức sau:

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

Khi một toán tử được áp dụng cho kiểu dữ liệu "sai", JavaScript sẽ lặng lẽ chuyển đổi giá trị đó thành kiểu nó cần, sử dụng một bộ quy tắc thường không phải là điều bạn muốn hoặc mong đợi. Điều này được gọi là _((ép kiểu))_. `null` trong biểu thức đầu tiên trở thành `0` và `"5"` trong biểu thức thứ hai trở thành `5` (từ chuỗi thành số). Tuy nhiên, trong biểu thức thứ ba, `+` thử nối chuỗi trước khi cộng số, do đó `1` được chuyển đổi thành `"1"` (từ số sang chuỗi).

{{index "type coercion", [number, "conversion to"]}}

Khi một cái gì đó không đối chiếu được tới một số theo cách rõ ràng (chẳng hạn như `"five"` hoặc `undefined`) được chuyển đổi thành một số, bạn sẽ nhận được giá trị `NaN`. Các phép toán số học tiếp theo trên `NaN` tiếp tục tạo ra `NaN`, vì vậy nếu bạn thấy mình nhận được một trong những phép toán đó ở một nơi không mong muốn, hãy tìm tới các chuyển đổi kiểu ngẫu nhiên.

{{index null, undefined, [comparison, "of undefined values"], "== operator"}}

Khi so sánh các giá trị cùng kiểu bằng toán tử `==`, kết quả rất dễ dự đoán: bạn sẽ nhận được giá trị đúng khi cả hai giá trị đều giống nhau, ngoại trừ trường hợp `NaN`. Nhưng khi các kiểu khác nhau, JavaScript sẽ sử dụng một bộ quy tắc phức tạp và khó hiểu để xác định những việc cần làm. Trong hầu hết các trường hợp, nó chỉ cố gắng chuyển đổi một trong các giá trị sang kiểu giá trị khác. Tuy nhiên, khi `null` hoặc `undefined` xảy ra ở một trong hai bên của toán tử, nó chỉ trả về giá trị đúng nếu cả hai bên đều là một trong `null` hoặc `undefined`.

```
console.log(null == undefined);
// → true
console.log(null == 0);
// → false
```

Hành vi đó thường hữu ích. Khi bạn muốn kiểm tra xem một giá trị mang giá trị thực thay vì `null` hoặc `undefined` hay không, bạn có thể so sánh nó với `null` bằng toán tử `==` hoặc `!=`.

{{index "type coercion", [Boolean, "conversion to"], "=== operator", "!== operator", comparison}}

Điều gì sẽ xảy ra nếu bạn muốn kiểm tra xem thứ gì đó có đề cập đến giá trị chính xác `false` hay không? Các biểu thức như `0 == false` và `"" == false` cũng đúng vì chuyển đổi kiểu tự động. Khi bạn _không_ muốn bất kỳ chuyển đổi loại nào xảy ra, có hai toán tử bổ sung: `===` và `!==`. Lần đầu tiên kiểm tra xem một giá trị có _chính xác_ bằng giá trị kia hay không và lần thứ hai kiểm tra xem giá trị đó có bằng chính xác hay không. Do đó `"" === false` là sai, như mong đợi.

Tôi khuyên bạn nên sử dụng toán tử so sánh ba ký tự như một lớp đề phòng tránh việc chuyển đổi kiểu không mong muốn khiến bạn gặp khó khăn. Nhưng khi bạn chắc chắn rằng kiểu ở cả hai bên sẽ giống nhau thì sẽ không có vấn đề gì khi sử dụng các toán tử ngắn hơn.

### Làm ngắn đi mạch toán tử logic

{{index "type coercion", [Boolean, "conversion to"], operator}}

Các toán tử logic `&&` và `||` xử lý các giá trị thuộc các kiểu khác nhau theo một cách đặc biệt. Chúng sẽ chuyển đổi giá trị ở bên trái sang loại Boolean để quyết định phải làm gì, nhưng tùy thuộc vào toán tử và kết quả của chuyển đổi đó, chúng sẽ trả về giá trị _ban đầu_ bên trái hoặc giá trị bên phải.

{{index "|| operator"}}

Ví dụ, toán tử `||` sẽ trả về giá trị ở bên trái khi giá trị đó có thể được chuyển đổi thành true và nếu không sẽ trả về giá trị ở bên phải. Điều này có tác dụng như mong đợi khi các giá trị là Boolean và thực hiện điều gì đó tương tự đối với các giá trị thuộc kiểu khác.

```
console.log(null || "nguoidung")
// → nguoidung
console.log("Phong" || "nguoidung")
// → Phong
```

{{index "default value"}}

Chúng ta có thể sử dụng chức năng này như một cách để quay lại giá trị mặc định. Nếu bạn có một giá trị có thể trống, bạn có thể đặt `||` sau giá trị đó bằng một giá trị thay thế. Nếu giá trị ban đầu có thể được chuyển đổi thành sai, thay vào đó bạn sẽ nhận được giá trị thay thế. Các quy tắc chuyển đổi chuỗi và số thành giá trị Boolean nêu rõ rằng `0`, `NaN` và chuỗi trống (`""`) được tính là sai, trong khi tất cả các giá trị khác được tính là đúng. Điều đó có nghĩa là `0 || -1` tạo ra `-1` và `"" || "!?"` trả về `"!?"`.

{{index "?? operator", null, undefined}}

Toán tử `??` giống như `||` nhưng chỉ trả về giá trị ở bên phải nếu giá trị ở bên trái là `null` hoặc `undefined`, chứ không trả về giá trị nào khác có thể được chuyển đổi thành `false`. Thông thường, điều này tốt hơn hành vi của `||`.

```
console.log(0 || 100);
// → 100
console.log(0 ?? 100);
// → 0
console.log(null ?? 100);
// → 100
```

{{index "&& operator"}}

Toán tử `&&` hoạt động tương tự nhưng ngược lại. Khi giá trị ở bên trái của nó được chuyển thành sai, nó sẽ trả về giá trị đó và nếu không thì nó sẽ trả về giá trị ở bên phải.

Một thuộc tính quan trọng khác của hai toán tử này là phần bên phải của chúng chỉ được xem xét khi cần thiết. Trong trường hợp `true || X`, bất kể `X` là gì—ngay cả khi nó là một phần của chương trình thực hiện điều gì đó _khủng khiếp_—kết quả sẽ đúng và `X` không bao giờ được gọi đến. Điều tương tự cũng xảy ra với `false && X`, là sai và sẽ bỏ qua `X`. Nó được gọi là _((đánh giá ngắn mạch))_.

{{index "ternary operator", "?: operator", "conditional operator"}}

Toán tử điều kiện cũng hoạt động theo cách tương tự. Trong số giá trị thứ hai và thứ ba, chỉ giá trị được chọn mới được đánh giá.

## Tổng kết

Chúng ta đã xem qua bốn kiểu giá trị JavaScript trong chương này: số, chuỗi, Boolean và giá trị không xác định. Các giá trị như vậy được tạo bằng cách nhập tên của chúng (`true`, `null`) hoặc giá trị (`13`, `"abc"`).

Bạn có thể kết hợp và chuyển đổi các giá trị bằng toán tử. Chúng ta đã thấy các toán tử hai ngôi cho số học (`+`, `-`, `*`, `/`, và `%`), nối chuỗi (`+`), so sánh (`==`, `!=`, ` ===`, `!==`, `<`, `>`, `<=`, `>=`), và logic (`&&`, `||`, `??`), đi kèm với một số toán tử một ngôi (`-` để phủ định một số, `!` để phủ định một logic và `typeof` để tìm kiểu giá trị) và toán tử ba ngôi (`?:`) để chọn một trong hai giá trị dựa trên giá trị thứ ba.

Trên đây đã cung cấp cho bạn đủ thông tin để sử dụng JavaScript như một máy tính bỏ túi nhưng không nhiều hơn thế. [Chương tiếp theo](program_structure) sẽ bắt đầu liên kết các biểu thức này lại với nhau thành các chương trình cơ bản.
