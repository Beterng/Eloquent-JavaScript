{{meta {load_files: ["code/intro.js"]}}}

# Giới thiệu

{{quote {author: "Ellen Ullman", title: "Close to the Machine: Technophilia and Its Discontents", chapter: true}

Chúng ta nghĩ rằng chúng ta đang tạo ra hệ thống cho mục đích của riêng mình. Chúng ta tin rằng chúng ta đang tạo ra nó theo hình ảnh của riêng mình... Nhưng máy tính không thực sự giống chúng ta. Nó là sự phản chiếu của một phần rất nhỏ trong chúng ta: phần dành cho logic, trật tự, quy tắc và sự rõ ràng.

quote}}

{{figure {url: "img/chapter_picture_00.jpg", alt: "Hình minh họa một chiếc tua vít bên cạnh một bảng mạch có kích thước tương tự", chapter: "framed"}}}

Cuốn sách này là về việc ra lệnh cho ((máy tính)). Máy tính ngày nay phổ biến không khác gì những tua vít vậy, nhưng chúng có phần phức tạp hơn và việc khiến chúng làm những gì bạn muốn không phải lúc nào cũng dễ.

Nếu nhiệm vụ bạn giao cho máy tính là nhiệm vụ thông thường và dễ hiểu, chẳng hạn như hiển thị email hay hoạt động như một chiếc máy tính cầm tay, bạn có thể mở các ((ứng dụng)) phù hợp hợp và bắt đầu làm việc. Nhưng đối với các nhiệm vụ đặc biệt hoặc không có kết thúc rõ ràng, thì thường không có những ứng dụng như vậy.

Đó là lúc ((lập trình)) xuất hiện. _Lập trình_ là hành động xây dựng _chương trình_—một tập hợp các hướng dẫn cho máy tính biết chính xác phải làm gì. Bởi vì máy tính là những con thú ngu ngốc và cầu kỳ, nên việc lập trình về cơ bản là tẻ nhạt và khó chịu.

{{index [programming, "joy of"], speed}}

May mắn thay, nếu bạn có thể vượt qua được thực tế đó—và thậm chí có thể tận hưởng sự nghiêm túc trong suy nghĩ mà những cỗ máy ngu ngốc có thể xử lý—thì việc lập trình có thể rất bổ ích. Nó cho phép bạn thực hiện mọi việc trong vài giây mà nếu làm bằng tay có thể sẽ mất _mãi mãi_. Đó là cách để làm cho công cụ máy tính của bạn làm những việc mà trước đây nó không thể làm được. Trên hết, nó tạo nên một trò chơi tuyệt vời về giải đố và tư duy trừu tượng.

Hầu hết việc lập trình được thực hiện bằng ((ngôn ngữ lập trình)). _Ngôn ngữ lập trình_ là ngôn ngữ được con người xây dựng dùng để chỉ dẫn máy tính. Điều thú vị là cách hiệu quả nhất mà chúng ta tìm ra để giao tiếp với máy tính lại vay mượn rất nhiều từ cách chúng ta giao tiếp với nhau. Giống như ngôn ngữ của con người, ngôn ngữ máy tính cho phép kết hợp các từ và cụm từ theo những cách mới, giúp có thể diễn đạt các khái niệm mới hơn.

{{index [JavaScript, "availability of"], "casual computing"}}

Có thời điểm, các giao diện dựa trên ngôn ngữ, chẳng hạn như BASIC và DOS của những năm 1980 và 1990, là phương pháp chính để tương tác với máy tính. Đối với việc sử dụng máy tính thông thường, những thứ này phần lớn đã được thay thế bằng các giao diện trực quan, dễ học hơn nhưng mang lại ít sự tự do hơn. Nhưng nếu bạn biết tìm ở đâu thì các ngôn ngữ vẫn còn đó. Một trong số đó, _JavaScript_, được tích hợp trên mọi ((trình duyệt)) web hiện đại—và do đó có sẵn trên hầu hết mọi thiết bị.

{{indexsee "web browser", browser}}

Cuốn sách này sẽ giúp bạn làm quen với ngôn ngữ này đủ để có thể làm những việc hữu ích và thú vị với nó.
## Về việc lập trình

{{index [programming, "difficulty of"]}}

Bên cạnh việc giải thích JavaScript, tôi cũng sẽ giới thiệu thêm về các nguyên tắc cơ bản của lập trình. Việc lập trình, hoá ra lại rất khó. Các quy tắc cơ bản thường đơn giản và rõ ràng, nhưng các chương trình được xây dựng trên các quy tắc này có xu hướng trở nên phức tạp đến mức phải đưa ra các quy tắc và độ phức tạp của riêng chúng. Theo một cách nào đó, bạn đang xây dựng mê cung của riêng mình và bạn có thể dễ dàng bị lạc vào trong đó.

{{index learning}}

Sẽ có những lúc đọc cuốn sách này khiến bạn cảm thấy vô cùng bực bội. Nếu bạn là người mới làm quen với việc lập trình, sẽ có rất nhiều tài liệu mới để tiếp thu. Phần lớn tài liệu này sau đó sẽ được _kết hợp_ theo những cách đòi hỏi bạn phải tạo thêm các sự liên kết.

Bạn phải nỗ lực hết sức. Khi bạn đang vật lộn để theo kịp cuốn sách, đừng vội kết luận về khả năng của mình. Bạn ổn—bạn chỉ cần tiếp tục cố gắng. Hãy nghỉ ngơi, đọc lại một số tài liệu và đảm bảo rằng bạn đã đọc và hiểu các chương trình ví dụ và ((bài tập)). Học tập là công việc khó khăn, nhưng mọi thứ bạn học được đều là của bạn và sẽ giúp việc học tiếp theo dễ dàng hơn.

{{quote {author: "Ursula K. Le Guin", title: "The Left Hand of Darkness"}

{{index "Le Guin, Ursula K."}}

Khi hành động không đem lại kết quả, tìm tòi; khi thông tin không đem lại kết quả, nghỉ ngơi.

quote}}

{{index [program, "nature of"], data}}

Một chương trình là rất nhiều thứ. Nó là một đoạn văn bản do lập trình viên viết ra, nó là tác nhân điều khiển máy tính thực hiện công việc của nó, nó là dữ liệu trong bộ nhớ của máy tính và đồng thời, nó kiểm soát các hành động được thực hiện trên bộ nhớ này. Những sự cố gắng so sánh các chương trình với các đối tượng quen thuộc thường mắc phải sự thiếu sót. Một cách phù hợp hơn về hình thức đó là so sánh một chương trình với một cỗ máy—các bộ phận riêng biệt có xu hướng liên kết với nhau. Và để làm cho tổng thể hoạt động tốt, chúng ta phải xem xét cách thức mà các bộ phận này kết nối với nhau và đóng góp vào hoạt động của tổng thể.

Một ((máy tính)) là một cỗ máy vật lý đóng vai trò là máy chủ cho những cỗ máy phi vật chất này. Bản thân máy tính chỉ có thể làm những việc đơn giản đến ngớ ngẩn. Lý do chúng hữu ích đến vậy là vì chúng làm những việc này với ((tốc độ)) cực kỳ cao. Một chương trình có thể khéo léo kết hợp một số lượng lớn các hành động đơn giản này để thực hiện những việc rất phức tạp.

{{index [programming, "joy of"]}}

Một chương trình là một công trình của ý tưởng. Nó không tốn kém để xây dựng, nó nhẹ tênh và dễ dàng phát triển dưới bàn tay đánh máy của chúng ta. Nhưng khi một chương trình phát triển, thì ((độ phức tạp) của nó cũng tăng theo. Kỹ năng lập trình là kỹ năng xây dựng các chương trình mà không gây nhầm lẫn cho lập trình viên. Các chương trình tốt nhất là những chương trình có thể làm được điều gì đó thú vị nhưng vẫn dễ hiểu.

{{index "programming style", "best practices"}}

Một số lập trình viên tin rằng sự phức tạp này được quản lý tốt nhất bằng cách chỉ sử dụng một tập hợp nhỏ các kỹ thuật được hiểu rõ trong chương trình của họ. Họ đã soạn thảo các quy tắc nghiêm ngặt ("các thực hành tốt nhất"—"best practices") quy định các hình thức mà chương trình nên có và cẩn thận duy trì trong vùng an toàn nhỏ bé của chúng.

{{index experiment}}

Điều này không chỉ nhàm chán—mà lại còn kém hiệu quả. Những vấn đề mới thường đòi hỏi những giải pháp mới. Lĩnh vực lập trình còn non trẻ và vẫn đang phát triển nhanh chóng, đồng thời nó đủ đa dạng để có chỗ cho các cách tiếp cận khác nhau. Có rất nhiều sai lầm khủng khiếp có thể mắc phải trong quá trình thiết kế chương trình, bạn nên tiếp tục và mắc phải chúng ít nhất một lần để hiểu chúng. Cảm giác về một chương trình tốt trông như thế nào được phát triển bằng thực hành chứ không phải học được từ một danh sách các quy tắc.

## Tại sao ngôn ngữ lại quan trọng

{{index "programming language", "machine code", "binary data"}}

Trước đây, vào thời kì sơ khai của máy tính, đã không có một ngôn ngữ lập trình nào cả. Các chương trình ban đầu trông giống như thế này:

```{lang: null}
00110001 00000000 00000000
00110001 00000001 00000001
00110011 00000001 00000010
01010001 00001011 00000010
00100010 00000010 00001000
01000011 00000001 00000000
01000001 00000001 00000001
00010000 00000010 00000000
01100010 00000000 00000000
```

{{index [programming, "history of"], "punch card", complexity}}

Đây là một chương trình cộng các số từ 1 đến 10 lại với nhau và in ra kết quả: `1 + 2 + ... + 10 = 55`. Nó có thể chạy trên một máy tính giả định đơn giản. Để lập trình cho những chiếc máy tính đời đầu, cần phải đặt các dãy công tắc lớn ở đúng vị trí hoặc đục lỗ trên các dải bìa cứng và đưa chúng vào máy tính. Bạn có thể tưởng tượng quy trình này tẻ nhạt và dễ xảy ra lỗi như thế nào. Ngay cả việc viết những chương trình đơn giản cũng đòi hỏi nhiều sự thông minh và kỷ luật. Những chương trình phức tạp thì gần như không thể tưởng tượng được.

{{index bit, "wizard (mighty)"}}

Tất nhiên, việc nhập thủ công các mẫu bit bí ẩn này (số một và số không) đã mang lại cho lập trình viên cảm giác sâu sắc về việc trở thành một phù thủy hùng mạnh. Và điều đó phải có giá trị gì đó xét về sự hài lòng trong công việc.

{{index memory, instruction}}

Mỗi dòng của chương trình trước chứa một lệnh duy nhất. Nó có thể được viết bằng tiếng Việt như thế này:

 1. Lưu số 0 vào vị trí số 0 trong bộ nhớ.
 2. Lưu số 1 vào vị trí số 1 trong bộ nhớ.
 3. Lưu giá trị của vị trí số 1 trong bộ nhớ vào vị trí số 2 trong bộ nhớ.
 4. Trừ đi 11 khỏi giá trị ở vị trí số 2 trong bộ nhớ.
 5. Nếu giá trị ở vị trí số 2 trong bộ nhớ là số 0, hãy tiếp tục với câu lệnh số 9.
 6. Thêm giá trị của vị trí số 1 trong bộ nhớ vào vị trí số 0 trong bộ nhớ.
 7. Thêm số 1 vào giá trị của vị trí số 1 trong bộ nhớ.
 8. Tiếp tục với câu lệnh số 3.
 9. Xuất ra giá trị ở vị trí số 0 trong bộ nhớ.

{{index readability, naming, binding}}

Mặc dù nó đã dễ đọc hơn so với món súp bit, nhưng nó vẫn còn khá mơ hồ. Việc sử dụng tên thay vì số cho các câu lệnh và vị trí trong bộ nhớ sẽ hữu ích.

```{lang: "null"}
  Đặt “tong” thành 0.
  Đặt “sodem” thành 1.
[vonglap]
  Đặt “sosanh” thành “sodem”.
  Trừ 11 khỏi “sosanh”.
  Nếu “sosanh” là 0, tiếp tục tại [ketthuc].
  Thêm “sodem” vào “tong”.
  Thêm 1 vào “sodem”.
  Tiếp tục tại [vonglap].
[ketthuc]
  Xuất ra “tong”.
```

{{index loop, jump, "summing example"}}

Bạn có thể thấy chương trình hoạt động như thế nào vào lúc này? Hai dòng đầu tiên cung cấp cho hai vị trí bộ nhớ các giá trị bắt đầu của chúng: `tong` sẽ được sử dụng để xây dựng kết quả tính toán và `sodem` sẽ theo dõi số mà chúng ta hiện đang xem xét. Các dòng sử dụng `sosanh` có lẽ là những dòng khó hiểu nhất. Chương trình muốn xem liệu `sodem` có bằng 11 để quyết định xem nó có thể ngừng chạy hay không. Bởi vì máy giả định của chúng ta khá nguyên thủy, nó chỉ có thể kiểm tra xem một số có bằng 0 không và đưa ra quyết định dựa trên đó. Do đó, nó sử dụng vị trí bộ nhớ có nhãn `sosanh` để tính giá trị của `sodem - 11` và đưa ra quyết định dựa trên giá trị đó. Hai dòng tiếp theo cộng giá trị của `sodem` vào kết quả và tăng `sodem` lên 1 mỗi khi chương trình quyết định rằng `sodem` chưa phải là 11.

Đây là chương trình tương tự bằng JavaScript:

```
let tong = 0, sodem = 1;
while (sodem <= 10) {
  tong += sodem;
  sodem += 1;
}
console.log(tong);
// → 55
```

{{index "while loop", loop, [braces, block]}}

Phiên bản này cung cấp cho chúng ta thêm một vài cải tiến nữa. Quan trọng nhất, không cần chỉ định cách chúng ta muốn chương trình nhảy qua lại nữa—cấu trúc `while` sẽ đảm nhiệm việc đó. Nó tiếp tục thực hiện khối (được bọc trong dấu ngoặc nhọn) bên dưới nó miễn là điều kiện được đưa ra vẫn được giữ nguyên. Điều kiện đó là `sodem <= 10`, có nghĩa là “số đếm nhỏ hơn hoặc bằng 10”. Chúng ta không còn phải tạo ra một giá trị tạm thời và so sánh giá trị đó với 0 nữa, đó chỉ là một chi tiết không mấy thú vị. Một phần sức mạnh của ngôn ngữ lập trình là chúng có thể xử lý những chi tiết không thú vị đối với chúng ta.

{{index "console.log"}}

Ở cuối chương trình, sau khi cấu trúc `while` kết thúc, thao tác `console.log` được sử dụng để ghi kết quả.

{{index "sum function", "range function", abstraction, function}}

Cuối cùng, đây là tổng quan chương trình trông như thế nào nếu chúng ta có sẵn các phép toán `range` (phạm vi) và `sum` (tổng), tương ứng với việc tạo ra một ((bộ sưu tập)) (collection) các số trong một phạm vi và tính tổng của một tập hợp các số:

```{startCode: true}
console.log(sum(range(1, 10)));
// → 55
```

{{index readability}}

Qua đó ta có thể rút ra được rằng cùng một chương trình có thể được diễn đạt theo cả cách dài và ngắn, không thể đọc được và có thể đọc được. Phiên bản đầu tiên của chương trình cực kỳ khó hiểu, trong khi phiên bản cuối cùng này gần như là tiếng Anh: `log` ra `sum` của `range` của các số từ 1 đến 10. (Chúng ta sẽ xem trong [các chương sau](data) cách xác định các phép toán như `sum` và `range`.)

{{index ["programming language", "power of"], composability}}

Một ngôn ngữ lập trình tốt giúp cho lập trình viên bằng cách cho phép họ trình bày về các hành động mà máy tính phải thực hiện ở mức độ cao hơn. Nó giúp bỏ qua các chi tiết, cung cấp các khối xây dựng thuận tiện (chẳng hạn như `while` và `console.log`), cho phép bạn xác định các khối xây dựng của riêng mình (chẳng hạn như `sum` và `range`), và làm cho các khối đó dễ dàng sắp xếp.

## JavaScript là gì?

{{index history, Netscape, browser, "web application", JavaScript, [JavaScript, "history of"], "World Wide Web"}}

{{indexsee WWW, "World Wide Web"}}

{{indexsee Web, "World Wide Web"}}

JavaScript được giới thiệu vào năm 1995 như một cách để thêm các chương trình vào các trang web trong trình duyệt Netscape Navigator. Ngôn ngữ này đã được áp dụng bởi tất cả các trình duyệt web đồ họa lớn khác. Nó đã làm cho các ứng dụng web hiện đại trở nên khả thi—nghĩa là các ứng dụng mà bạn có thể tương tác trực tiếp mà không cần tải lại trang cho mỗi hành động. JavaScript cũng được sử dụng trong các trang web truyền thống hơn để cung cấp nhiều hình thức tương tác và thông minh khác nhau.

{{index Java, naming}}

Điều quan trọng cần lưu ý là JavaScript hầu như không liên quan gì đến ngôn ngữ lập trình có tên Java. Cái tên tương tự được lấy cảm hứng từ những cân nhắc tiếp thị hơn là sự đánh giá đúng đắn. Khi JavaScript được giới thiệu, ngôn ngữ Java đã được tiếp thị rộng rãi và ngày càng trở nên phổ biến. Có người cho rằng cố gắng tiếp tục thành công này là một ý tưởng hay. Tới giờ chúng ta vẫn đang bị mắc kẹt với cái tên này.

{{index ECMAScript, compatibility}}

Sau khi được áp dụng bên ngoài Netscape, một tài liệu ((tiêu chuẩn)) đã được viết ra để mô tả cách hoạt động của ngôn ngữ JavaScript để các phần mềm tuyên bố hỗ trợ JavaScript khác nhau có thể đảm bảo rằng chúng thực sự cung cấp cùng một ngôn ngữ. Đây được gọi là tiêu chuẩn ECMAScript, theo tên của tổ chức quốc tế ECMA International tiến hành tiêu chuẩn hóa. Trong thực tế, thuật ngữ ECMAScript và JavaScript có thể được sử dụng thay thế cho nhau—chúng là hai tên cho cùng một ngôn ngữ.

{{index [JavaScript, "weaknesses of"], debugging}}

Có những người sẽ nói những điều _tệ hại_ về JavaScript. Nhiều điều trong số này là sự thật. Khi tôi được yêu cầu viết một cái gì đó bằng JavaScript lần đầu tiên, tôi đã nhanh chóng coi thường nó. Nó sẽ chấp nhận hầu hết mọi thứ tôi viết nhưng diễn giải nó theo cách hoàn toàn khác với ý tôi. Tất nhiên, điều này liên quan rất nhiều đến thực tế là tôi không biết mình đang làm gì, nhưng có một vấn đề thực sự ở đây: JavaScript tự do một cách kỳ cục trong những gì nó cho phép. Ý tưởng đằng sau thiết kế này là nó sẽ giúp cho việc lập trình bằng JavaScript trở nên dễ dàng hơn cho người mới bắt đầu. Trên thực tế, điều này chủ yếu khiến cho việc tìm kiếm các vấn đề trong chương trình của bạn trở nên khó khăn hơn vì hệ thống sẽ không chỉ ra chúng cho bạn.

{{index [JavaScript, "flexibility of"], flexibility}}

Mặc dù vậy, tính linh hoạt này cũng có những ưu điểm của nó. Nó nhường chỗ cho các kỹ thuật không thể có trong các ngôn ngữ cứng nhắc hơn và tạo ra một phong cách lập trình thân thiện, dễ chịu. Sau khi ((học)) ngôn ngữ đúng cách và làm việc với nó được một thời gian, tôi đã thực sự _thích_ JavaScript.

{{index future, [JavaScript, "versions of"], ECMAScript, "ECMAScript 6"}}

Đã có một số phiên bản JavaScript. ECMAScript phiên bản 3 là phiên bản được hỗ trợ rộng rãi trong thời kỳ JavaScript vươn lên thống trị, khoảng từ năm 2000 đến năm 2010. Trong thời gian này, công việc đã được tiến hành trên phiên bản 4 đầy tham vọng, trong đó có kế hoạch cho một số cải tiến triệt để và mở rộng ngôn ngữ. Việc thay đổi một ngôn ngữ sống động và được sử dụng rộng rãi theo cách triệt để như vậy hóa ra lại rất khó khăn, và việc phát triển phiên bản 4 đã bị hủy bỏ vào năm 2008. Một phiên bản 5 ít tham vọng hơn nhiều, chỉ thực hiện một số cải tiến không gây tranh cãi, đã ra mắt vào năm 2009. Năm 2015, phiên bản 6 ra đời, một bản cập nhật lớn bao gồm một số ý tưởng được lên kế hoạch cho phiên bản 4. Kể từ đó, chúng ta đã có những bản cập nhật nhỏ, mới hàng năm.

Thực tế là JavaScript đang phát triển có nghĩa là các trình duyệt phải liên tục theo kịp. Nếu bạn đang sử dụng trình duyệt cũ hơn, nó có thể không hỗ trợ mọi tính năng. Các nhà thiết kế ngôn ngữ cẩn thận không thực hiện bất kỳ thay đổi nào có thể phá vỡ các chương trình hiện có, vì vậy các trình duyệt mới vẫn có thể chạy các chương trình cũ. Trong cuốn sách này, tôi đang sử dụng phiên bản JavaScript 2024.

{{index [JavaScript, "uses of"]}}

Trình duyệt web không phải là nền tảng duy nhất mà JavaScript được sử dụng. Một số cơ sở dữ liệu, chẳng hạn như MongoDB và CouchDB, sử dụng JavaScript làm ngôn ngữ kịch bản và truy vấn của chúng. Một số nền tảng cho lập trình máy tính và máy chủ, đáng chú ý nhất là dự án ((Node.js)) (chủ đề của [Chương ?](node)), cung cấp môi trường lập trình JavaScript bên ngoài trình duyệt.

## Mã lệnh, và làm gì với nó

{{index "reading code", "writing code"}}

_Mã lệnh_ (code) là văn bản tạo nên các chương trình. Hầu hết các chương trong cuốn sách này đều chứa khá nhiều mã. Tôi tin rằng việc đọc mã và viết ((mã)) là những phần không thể thiếu của ((việc học)) để lập trình. Cố gắng không chỉ lướt qua các ví dụ—hãy đọc chúng một cách chăm chú và hiểu chúng. Điều này có thể chậm và khó hiểu lúc đầu, nhưng tôi hứa rằng bạn sẽ nhanh chóng hiểu được nó. Điều tương tự cũng áp dụng với ((bài tập)). Đừng cho rằng bạn hiểu chúng cho đến khi bạn thực sự viết một giải pháp hoạt động.

{{index interpretation}}

Tôi khuyên bạn nên thử các giải pháp của mình cho các bài tập trên trình thông dịch JavaScript thực tế. Bằng cách đó, bạn sẽ nhận được phản hồi ngay lập tức về việc liệu những gì bạn đang làm có hiệu quả hay không, và tôi hy vọng, bạn sẽ bị cám dỗ để ((thử nghiệm)) và vượt xa cả các bài tập.

{{if interactive

Khi đọc cuốn sách này trên trình duyệt, bạn có thể chỉnh sửa (và chạy) tất cả các chương trình ví dụ bằng cách nhấp vào chúng.

if}}

{{if book

{{index download, sandbox, "running code"}}

Cách dễ nhất để chạy mã ví dụ trong sách—và thử nghiệm nó—là tra cứu nó trong phiên bản trực tuyến của cuốn sách tại [_https://eloquentjavascript.net_](https://eloquentjavascript.net/). Ở đó, bạn có thể nhấp vào bất kỳ mã ví dụ nào để chỉnh sửa và chạy nó và để xem đầu ra mà nó tạo ra. Để thực hiện các bài tập, hãy truy cập [_https://eloquentjavascript.net/code_](https://eloquentjavascript.net/code), nơi cung cấp mã bắt đầu cho mỗi bài tập viết mã và cho phép bạn xem các lời giải.

if}}

{{index "developer tools", "JavaScript console"}}

Việc chạy các chương trình được xác định trong cuốn sách này bên ngoài trang web của cuốn sách đòi hỏi một số cẩn thận. Nhiều ví dụ đứng riêng và nên hoạt động trong bất kỳ môi trường JavaScript nào. Nhưng mã trong các chương sau thường được viết cho một môi trường cụ thể (trình duyệt hoặc Node.js) và chỉ có thể chạy ở đó. Ngoài ra, nhiều chương xác định các chương trình lớn hơn và các đoạn mã xuất hiện trong chúng phụ thuộc vào nhau hoặc vào các tệp bên ngoài. [Môi trường mở (sandbox)](https://eloquentjavascript.net/code) trên trang web cung cấp các liên kết đến các tệp ZIP chứa tất cả các tập lệnh và tệp dữ liệu cần thiết để chạy mã cho một chương nhất định.

## Tổng quan về cuốn sách này

Cuốn sách này chứa đâu đó khoảng ba phần. 12 chương đầu tiên thảo luận về ngôn ngữ JavaScript. Bảy chương tiếp theo là về ((trình duyệt)) web và cách JavaScript được sử dụng để lập trình chúng. Cuối cùng, hai chương được dành cho ((Node.js)), một môi trường khác để lập trình JavaScript. Có năm _chương dự án_ trong cuốn sách mô tả các chương trình ví dụ lớn hơn để giúp bạn cảm nhận về lập trình thực tế.

Phần ngôn ngữ của cuốn sách bắt đầu với bốn chương giới thiệu cấu trúc cơ bản của ngôn ngữ JavaScript. Chúng thảo luận về [cấu trúc điều khiển](program_structure) (chẳng hạn như từ `while` bạn đã thấy trong phần giới thiệu này), [hàm](functions) (viết các khối xây dựng của riêng bạn) và [cấu trúc dữ liệu](data). Sau đó, bạn sẽ có thể viết các chương trình cơ bản. Tiếp theo, các chương [?](higher_order) và [?](object) giới thiệu các kỹ thuật sử dụng các hàm và đối tượng để viết thêm mã _trừu tượng_ và kiểm soát độ phức tạp.

Sau một [chương dự án đầu tiên](robot) xây dựng một robot giao hàng thô sơ, phần ngôn ngữ của cuốn sách tiếp tục với các chương về [xử lý lỗi và sửa lỗi](error), [biểu thức chính quy](regexp) (một công cụ quan trọng để làm việc với văn bản), [mô-đun](modules) (một biện pháp bảo vệ khác khắc chế sự phức tạp) và [lập trình bất đồng bộ](async) (xử lí các sự kiện tốn thời gian). [Chương dự án thứ hai](language), nơi chúng ta triển khai ngôn ngữ lập trình, kết thúc phần đầu tiên của cuốn sách.

Phần thứ hai của cuốn sách, các chương [?](browser) đến [?](paint), mô tả các công cụ mà trình duyệt JavaScript có quyền truy cập. Bạn sẽ học cách hiển thị mọi thứ trên màn hình (Chương [?](dom) và [?](canvas)), phản hồi đầu vào của người dùng ([Chương ?](event)) và giao tiếp qua mạng ([Chương ?](http)). Một lần nữa có hai chương dự án trong phần này: xây dựng một [trò chơi nền tảng](game) và [chương trình vẽ tranh pixel](paint).

[Chương ?](node) mô tả Node.js, và [Chương ?](skillsharing) xây dựng một trang web nhỏ bằng công cụ đó.

{{if commercial

Cuối cùng, [Chương ?](fast) mô tả một số vấn đề cần cân nhắc khi tối ưu hóa tốc độ của các chương trình JavaScript.

if}}

## Quy ước kiểu chữ

{{index "factorial function"}}

Trong cuốn sách này, văn bản được viết bằng phông chữ `đơn cách (monospaced)` sẽ đại diện cho các phần tử của chương trình. Đôi khi đây là những đoạn tự cung cấp, và đôi khi chúng chỉ đề cập đến một phần của chương trình gần đó. Các chương trình (mà bạn đã thấy một vài) được viết như sau:

```
function giaithua(n) {
  if (n == 0) {
    return 1;
  } else {
    return giaithua(n - 1) * n;
  }
}
```

{{index "console.log"}}

Đôi khi, để hiển thị đầu ra mà một chương trình tạo ra, đầu ra mong đợi sẽ được viết sau nó, với hai dấu gạch chéo và một mũi tên ở phía trước.

```
console.log(giaithua(8));
// → 40320
```

Chúc may mắn!
