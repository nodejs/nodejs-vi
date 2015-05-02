---
layout: post
title: Cùng nhau học nodeschool
categories: [nodeschool, tutorial]
tags: [nodeschool, tutorial, publish]
description: Bài 2
---

# Nội dung

Nội dung của bài học là hướng dẫn các bạn các bước đi từ đơn giản đến phức tạp để hoàn thành một chương trình Node.js. Và yêu cầu của bài học là viết một chương trình chấp nhận một hoặc nhiều số như những tham số  và in ra tổng của những số đó.

Để bắt đầu, bạn hãy viết một chương trình đơn giản có chứa:

    console.log(process.argv)

Chạy nó với node program.js và với những số như các tham số, ví dụ:

    $ node program.js 1 2 3

Trong trường hợp này, nó sẽ hiển thị ra một mảng trông giống như:

    [ ‘node’, ‘/path/to/your/program.js’, ‘1’, ‘2’, ‘3’ ]

Bạn cần phải suy nghĩ xem làm thế nào tạo một vòng lặp với những số trên để có thể hiển thị ra tổng của những số đó.
Phần tử đầu tiên của mảng process.argv là ‘node’, phần tử số 2 của mảng là đường dẫn đến file progam.js của bạn. Như vậy bạn cần bắt đầu từ phần tử số 3 (index 2),
Thêm mỗi item vào tổng cho đến khi kết thúc mảng. Bạn có thể làm điều này bằng cách đặt trước property với dấu + hoặc dùng Number() đảm bảo kết quả hiển thị ra là số, ví dụ:

    +process.argv[2] or Number(process.argv[2]).

Sau khi hoàn thành, để thử nghiệm chương trình của mình, bạn gọi nó với learnyounode run program.js . Khi bạn dùng run, bạn sẽ gọi môi trường thử nghiệm mà learnyounode thiết lập cho mỗi bài tập.
Để kết thúc, bạn chạy mã:

    $ learnyounode verify program.js

Chương trình của bạn sẽ được kiểm tra và bài học sẽ được đánh dấu ‘completed’ nếu bạn là thành công.

Đáp án bài học số 2:

{% highlight javascript %}
var args = process.argv.slice(2), len = args.length, result = 0;
for(var i = 0; i < len; i++)
    result += parseInt(args[i]);
console.log(result);
{% endhighlight %}
