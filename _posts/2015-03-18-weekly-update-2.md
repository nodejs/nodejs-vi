---
layout: post
title: weekly update 2015-02-13
categories: [weekly]
tags: [weekly, publish]
description: io.js support added by...
---

## io.js mới được thêm vào hỗ trợ
* [Postmark](http://blog.postmarkapp.com/post/110829734198/its-official-were-getting-cozy-with-node-js)
* [node-serialport](https://github.com/voodootikigod/node-serialport/issues/439)
* [Microsoft Azure](http://azure.microsoft.com/en-us/documentation/articles/web-sites-nodejs-iojs/)

## io.js vượt mức 10.000 sao trên GitHub!
Ngày 13 tháng 2, io.js đạt được 10.000 sao trên Github. Chúng tôi đã không thể làm được điều nà nếu không có sự trợ giúp của cộng đồng đằng sau JavaScript tuyệt vời. Cảm ơn tất cả!

## Ra mắt io.js 1.2.0
* **stream**: Construct stream dễ hơn ([readable-stream/issues#102[(https://github.com/iojs/readable-stream/issues/102))
* **dns**: Phương thức `lookup()` bây giờ hỗ trợ một boolean `'all'`, mặt định là `false` nhưng khi kích hoạt, các thức sẽ trả về một mảng chứa tất cả tên giải được từ một địa chỉ, xem ([iojs/pull#744](https://github.com/iojs/io.js/pull/744))
* **assert**: Loại bỏ so sánh thuộc tính `prototype` trong `deepEqual()` ([iojs/issues#636](https://github.com/iojs/io.js/pull/636)); giới thiệu phương thức `deepStrictEqual()` gióng với `deepEqual()` nhưng vận hành chặt chẽ việc so-sánh-bằng các primitives ([iojs/issues#639](https://github.com/iojs/io.js/pull/639)).
* **tracing**: Thêm [LTTng](http://lttng.org/) (Linux Trace Toolkit Next Generation) khi biên dịch với lựa chọn `--with-lttng`. Truy ra các điểm có sẵn cho DTrace và ETW. ([iojs/issues#702](https://github.com/iojs/io.js/pull/702))
* **docs**: Rất nhiều cập nhật cho tài liệu, xem các commit riêng lẽ; trang Errors mới bàn về các lỗi JavaScript, các chi tiết về V8 và chi tiết các lỗi riêng của io.js.
* **npm** nâng cấp lên 2.5.1
* **libuv** nâng cấp lên 1.4.0, xem libuv [ChangeLog](https://github.com/libuv/libuv/blob/v1.x/ChangeLog)
* Thêm các collaborators:
  * Aleksey Smolenchuk (@lxe)
  * Shigeki Ohtsu (@shigeki)

## Mở cửa cho các cộng đồng toàn cầu
Xem [bài viết](https://medium.com/@mikeal/how-io-js-built-a-146-person-27-language-localization-effort-in-one-day-65e5b1c49a62) trên Medium.
* Đã thêm những người đóng góp tới nhóm ngôn ngữ của họ.
* Các nhóm đăng ký tài khoảng Twitter và các tài khoảng trên các phương tiện truyền thông khác.
* Các nhóm tìm cách hoạt đồng cùng nhau, và trở thành các "người quản lý cộng đồng" hơn chỉ là "những dịch giả".

### Thông số việc nội địa hoá:

* 146 người đã đăng ký giúp việc nội địa hoá ngày đầu tiên (bây giờ đã là 160 người)
* 27 cộng đồng ngôn ngũ được tạo ngày đầu tiên (bây giờ là 29)

### Các cộng đồng ngôn ngữ

* [`iojs-bn`](https://github.com/iojs/iojs-bn) Cộng đồng Bengali 
* [`iojs-cn`](https://github.com/iojs/iojs-cn) Cộng đồng Trung Quốc
* [`iojs-cs`](https://github.com/iojs/iojs-cs) Cộng đồng Czech 
* [`iojs-da`](https://github.com/iojs/iojs-da) Cộng đồng Danish 
* [`iojs-de`](https://github.com/iojs/iojs-de) Cộng đồng Đức 
* [`iojs-el`](https://github.com/iojs/iojs-el) Cộng đồng Hy Lạp
* [`iojs-es`](https://github.com/iojs/iojs-es) Cộng đồng Tây Ban Nha
* [`iojs-fa`](https://github.com/iojs/iojs-fa) Cộng đồng Persian 
* [`iojs-fi`](https://github.com/iojs/iojs-fi) Cộng đồng Finnish 
* [`iojs-fr`](https://github.com/iojs/iojs-fr) Cộng đồng Pháp
* [`iojs-he`](https://github.com/iojs/iojs-he) Cộng đồng Hebrew 
* [`iojs-hi`](https://github.com/iojs/iojs-hi) Cộng đồng Hindi 
* [`iojs-hu`](https://github.com/iojs/iojs-hu) Cộng đồng Hungarian 
* [`iojs-id`](https://github.com/iojs/iojs-id) Cộng đồng Indonesian 
* [`iojs-it`](https://github.com/iojs/iojs-it) Cộng đồng Ý
* [`iojs-ja`](https://github.com/iojs/iojs-ja) Cộng đồng Nhật Bản
* [`iojs-ka`](https://github.com/iojs/iojs-ka) Cộng đồng Georgian 
* [`iojs-kr`](https://github.com/iojs/iojs-kr) Cộng đồng Hàn Quốc
* [`iojs-mk`](https://github.com/iojs/iojs-mk) Cộng đồng Macedonian 
* [`iojs-nl`](https://github.com/iojs/iojs-nl) Cộng đồng Hà Lan
* [`iojs-no`](https://github.com/iojs/iojs-no) Cộng đồng Norwegian 
* [`iojs-pl`](https://github.com/iojs/iojs-pl) Cộng đồng Polish 
* [`iojs-pt`](https://github.com/iojs/iojs-pt) Cộng đồng Bồ Đào Nha
* [`iojs-ro`](https://github.com/iojs/iojs-ro) Cộng đồng Romanian 
* [`iojs-ru`](https://github.com/iojs/iojs-ru) Cộng đồng Nga
* [`iojs-sv`](https://github.com/iojs/iojs-sv) Cộng đồng Swedish 
* [`iojs-tr`](https://github.com/iojs/iojs-tr) Cộng đồng Thổ Nhĩ Kỳ
* [`iojs-tw`](https://github.com/iojs/iojs-tw) Cộng đồng Đài Loan
* [`iojs-uk`](https://github.com/iojs/iojs-uk) Cộng đồng Ukranian 

## io.js và Node.js
Xem [bài viết](https://medium.com/@iojs/io-js-and-a-node-js-foundation-4e14699fb7be) trên Medium.
* Scott Hammond, CEO của Joyent, thể hiện mong muốn của anh: đem io.js về node.js.

#### Trong chỉ vài tháng, io.js đã
* Has grown to 23 active core team members Có tới 23 thành viên cốt lõi
* Has several working groups Có vài nhóm hoạt động
* Has 29 language localization teams, Có 29 nhóm nội địa hoá
* Đã thu hút nhiều người đóng góp dự án hơn lịch sử của Node.js, và
* Đã có thể ra mắt các phần mềm chất lượng với một tốc độ tốt nhờ hỗ trợ từ một cộng đồng phi thường.

> Chúng tôi rất muốn để lại tất cả mọi thứ nhưng chúng tôi không thể hy sinh các cộng sức đã làm được hay các nguyên lý quản trị mở mà đã đưa tất cả đến hiện tại.

### Tương lai
* Các đàm phán với Node.js foundation vẫn còn đang diễn ra.
* Khi foundation có được mô hình quản trị, sẽ có một Issue trên Github của io.js về việc có nên sát nhập.

  * Việc này sẽ được thảo luận và bình chọn trong một cuộc gặp mặt công khai theo với các quy tắc quản trị đã dựng.

> Về cộng đồng, không có gì thay đổi

### Việc cần phải làm bây giờ
* Tiếp tục gửi các Pull Request tới io.js.
* Tham gia một trong các 27 [nhóm nội địa hoá](https://github.com/iojs/website/issues/125)
* Đóng góp vào các nhóm hoạt động ([streams](https://github.com/iojs/readable-stream), [website](https://github.com/iojs/website), [evangelism](https://github.com/iojs/website/labels/evangelism), [tracing](https://github.com/iojs/tracing-wg), [build](https://github.com/iojs/build), [roadmap](https://github.com/iojs/roadmap)) and
* Tiếp tục dùng io.js trong các ứng dụng của bạn.