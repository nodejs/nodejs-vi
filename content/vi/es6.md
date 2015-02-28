# ES6 on io.js

# ES6 trên io.js

io.js is built against modern versions of [V8](https://code.google.com/p/v8/). By keeping up-to-date with the latest releases of this engine we ensure new features from the [JavaScript ECMA-262 specification](http://www.ecma-international.org/publications/standards/Ecma-262.htm) are brought to io.js developers in a timely manner, as well as continued performance and stability improvements.

io.js được xây dựng với các phiên bản mới nhất của [V8](https://code.google.com/p/v8/).Bằng cách cập nhật liên tục các phiên bản mới của engine này, chúng tôi đảm bảo các tính năng mới đến từ [JavaScript ECMA-262 specification](http://www.ecma-international.org/publications/standards/Ecma-262.htm) sẽ được cung cấp đến cho các nhà phát triển io.js một cách kịp thời, cũng như tiếp tục các cải tiến về hiệu suất và tính ổn định.

Version 1.4.1 of io.js ships with V8 4.1.0.21, which includes ES6 features well beyond version 3.28.73 that ship with Node.js™ 0.12.x.

Phiên bản 1.3.0 của io.js được phát hành cùng với V8 4.1.0.14 , bao gồm các tính năng của ES6 vượt xa phiên bản 3.28.73 được phát hành cùng với Node.js™ 0.12.x.

## No more --harmony flag

## Không cần sử dụng --harmony flag

On Node.jsâ¢@0.12.x (V8 3.28+), the `--harmony` runtime flag enables all **completed**, **staged** and **in progress** ES6 features together, in bulk (with the exception of `proxies` which are hidden under `--harmony-proxies`). This means that some really buggy or even broken features like [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) are just as readily available for developers as [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*), which have very little or even no known-issues. As such, most developers tend to enable only certain features by using specific runtime harmony feature flags (e.g. `--harmony-generators`), or simply enable all of them and then use a restricted subset.

Node.js™@0.12.x (V8 3.28+), runtime flag --harmony cho phép các tính năng của ES6 cùng là completed, staged, in progress và với số lượng lớn (với ngoại lệ của các proxy được ẩn dưới các proxy --harmony). Điều này có nghĩa là một số tính năng đã bị lỗi hoăc thậm chí bị hỏng giống như [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) chi có sẵn cho các nhà phát triển như là [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*), mà trong đó có rất ít hoặc thậm chí không biết các vấn đề. Như vậy, hầu hết các nhà phát triển có xu hướng chỉ kích hoạt tính năng nhất định bằng cách sử dụng cụ thể tính năng của runtime flag harmony (ví dụ --harmony-generators), hoặc đơn giản cho phép tất cả và sự dụng một tập hợp con bị hạn chế.

With io.js@1.x (V8 4.1+), all that complexity goes away. All harmony features are now logically split into three groups for **shipping**, **staged** and **in progress** features:

Với [io.js@1.x](mailto:io.js@1.x) (V8 4.1+), tất cả những sự phức tạp đã ra đi. Tất cả các tính năng của harmony đã được chia một cách logic vào 3 nhóm các tính năng là shipping, staged và in progress:

*   All **shipping** features, the ones that V8 has considered stable, like [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*), [templates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings), [new string methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla#Additions_to_the_String_object) and many others are turned **on by default on io.js** and do **NOT** require any kind of runtime flag.
*   Then there are **staged** features which are almost-completed features that haven't been completely tested or updated to the latest spec yet and therefore are not considered stable by the V8 team (e.g. there might be some edge cases left to discover). This is probably the equivalent of the state of [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*) on 3.26. These are the "use at your own risk" type of features that now require a runtime flag: `--es_staging` (or its synonym, `--harmony`).
*   Finally, all **in progress** features can be activated individually by their respective harmony flag (e.g. `--harmony_arrow_functions`), although this is highly discouraged unless for testing purposes.

*	Các tính năng **shipping**, một trong những tính năng mà V8 đã coi là ổn định, như [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*), [templates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings), [new string methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla#Additions_to_the_String_object) và các tính năng khác được bật theo mặc định trên io.js và không đòi hỏi bất kỳ flag runtime nào.
*	Tiếp theo, các tính năng **staged**, đó là các tính năng gần như hoàn thành, chưa được hoàn toàn kiểm tra và cập nhật các thông số mới nhất, do đó chưa được coi là ổn định bởi team V8 (ví dụ, ở đây có thể là một số trường hợp còn lại để khám phá). Có lẽ sẽ tương đương với trạng thái của [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*) trong 3.26 . Đó là kiểu "sử dụng các nguy cơ của riêng bạn" của các tính năng mà hiện tại đã yêu cầu flag runtime: --es_staging (hoặc đồng nghĩa với nó, --harmony).
*	Cuối cùng, các tính năng **in progress** có thể được kích hoạt bằng cách riêng của chúng(ví dụ --harmony_arrow_functions) , mặc dù điều này được khuyến khích trừ khi cho mục đích thử nghiệm .

## Tính năng nào của ES6 được đi kèm với io.js theo mặc định (không yêu cầu runtime flag)


## Which ES6 features ship with io.js by default (no runtime flag required)?
## Các tính năng nào của ES6 được phát hành cùng với io.js theo mặc định(không có flag runtime được yêu cầu)?

*   Block scoping

    *   [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)

    *   [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

    *   `function`-in-blocks

    >As of v8 3.31.74.1, block-scoped declarations are [intentionally implemented with a non-compliant limitation to strict mode code](https://groups.google.com/forum/#!topic/v8-users/3UXNCkAU8Es). Developers should be aware that this will change as v8 continues towards ES6 specification compliance.
    >Trong V8 3.31.74.1, block-scoped được khai báo [cố ý thực hiện với một giới hạn không tuân thủ strict mode code](https://groups.google.com/forum/#!topic/v8-users/3UXNCkAU8Es). Các nhà phát triển cần phải nhận thức rằng điều này sẽ thay đổi khi V8 vẫn tiếp tục tuân thủ các đặc tả của ES6.


*   Collections

    *   [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)

    *   [WeakMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap)

    *   [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

    *   [WeakSet](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet)

*   [Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*)

*   [Binary and Octal literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Numeric_literals)

*   [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

*   [New String methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla#Additions_to_the_String_object)

*   [Symbols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)

*   [Template strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings)

You can view a more detailed list, including a comparison with other engines, on the [compat-table](https://kangax.github.io/compat-table/es6/) project page.

Bạn có thể xem thông tin đầy đủ hơn ở đây, bao gồm việc so sánh với các engines khác, trên 1 dự án [compat-table](https://kangax.github.io/compat-table/es6/).

## Which ES6 features are behind the --es_staging flag?

## Những tính năng nào của ES6 được bật với --es_staging flag ?

*   [Classes](https://github.com/lukehoban/es6features#classes) (strict mode only, behind flag `--harmony_classes` which implies block scoping & object literal extensions)

*   [Object literal extensions](https://github.com/lukehoban/es6features#enhanced-object-literals) (behind flag `--harmony_object_literals`)

*   [`Symbol.toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) (user-definable results for `Object.prototype.toString`, behind flag `--harmony_tostring`)

## Which ES6 features are in progress?

## Những tính năng nào của ES6 đang được phát triển ?

New features are constantly being added to the V8 engine. Generally speaking, expect them to land on a future io.js release, although timing is unknown.

Những tính năng mới đang được liên tục thêm vào trong V8 engine. Nói chung chúng ta sẽ mong đợi chúng ở các phiên bản tiếp theo của io.js, tuy thời gian là không xác định.

You may list all the *in progress* features available on each io.js release by grepping through the `--v8-options` argument. Please note that these are incomplete and possibly broken features of V8, so use them at your own risk:

Bạn có thể liệt kê tất cả các tính năng đang phát triển có sẵn trên mỗi phiên bản của V8 được grepping qua argument --v8-options. Xin lưu ý đây là những tính năng không đầy đủ và có thể bị  của V8, nên sử dụng chúng tại your own risk:

```sh
iojs --v8-options | grep "in progress"
```

## I have my infrastructure set up to leverage the --harmony flag. Should I remove it?

The current behaviour of the `--harmony` flag on io.js is to enable **staged** features only. After all, it is now a synonym of `--es_staging`. As mentioned above, these are completed features that have not been considered stable yet. If you want to play safe, especially on production environments, consider removing this runtime flag until it ships by default on V8 and, consequently, on io.js. If you keep this enabled, you should be prepared for further io.js upgrades to break your code if V8 changes their semantics to more closely follow the standard.

## How do I find which version of V8 ships with a particular version of io.js?

io.js provides a simple way to list all dependencies and respective versions that ship with a specific binary through the `process` global object. In case of the V8 engine, type the following in your terminal to retrieve its version:

```sh
iojs -p process.versions.v8
```
