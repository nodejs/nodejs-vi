---
layout: post
title: weekly update 2015-03-20
categories: [weekly]
tags: [weekly, publish]
description: io.js 1.6 release
---

# Phát hành io.js 1.6

Tuần này chúng ta có 2 bản phát hành của iojs [v1.6.1](https://iojs.org/dist/v1.6.1/) và  [v1.6.0](https://iojs.org/dist/v1.6.0/), bạn có thể tìm thông tin đầy đủ các thay đổi [tại GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).

### Những thay đổi đáng chú ý

#### 1.6.1

* **path**: Thêm kiểm tra kiểu (type-checking) trên `path.resolve()` [#1153](https://github.com/iojs/io.js/pull/1153) do phát hiện 1 số trường hợp lỗi mà điển hình là `path.dirname(undefined)`. Kiểm tra kiểu (Type-checking) được lới lỏng cho `path.dirname()`, `path.basename()`, và `path.extname()` (Colin Ihrig) [#1216](https://github.com/iojs/io.js/pull/1216).

* **querystring**: Tối ưu hóa bên trong `querystring.parse()` và `querystring.stringify()` [#847](https://github.com/iojs/io.js/pull/847) để tránh ngăn chặn các ký tự kiểu `Number` được chuyển đổi thông qua `querystring.escape()`[#1208](https://github.com/iojs/io.js/issues/1208), phơi bày 1 lỗi trong kiểm thử. Lỗi và kiểm thử đã được sửa bởi (Jeremiah Senkpiel) [#1213](https://github.com/iojs/io.js/pull/1213).

#### 1.6.0

* **node**: Một option mới trên command-line là  `-r` hay `--require` có thể được sử dụng để load trước các modules ở thời điểm khởi chạy (Ali Ijaz Sheikh) [#881](https://github.com/iojs/io.js/pull/881).

* **querystring**: `parse()` và `stringify()` được tối ưu nhanh hơn (Brian White) [#847](https://github.com/iojs/io.js/pull/847).

* **http**: Phương thức `http.ClientRequest#flush()` đã bị phản đối và thay thế bởi `http.ClientRequest#flushHeaders()` để phù hợp với sự thay đổi trên Node.js v0.12 [joyent/node#9048](https://github.com/joyent/node/pull/9048) (Yosuke Furukawa) [#1156](https://github.com/iojs/io.js/pull/1156).

* **net**: cho phép `server.listen()` chấp nhận 1 `String` cho `port`, e.g. `{ port: "1234" }`, để phù hợp với tham số tương tự đã được chấp nhận trong `net.connect()` như [joyent/node#9268](https://github.com/joyent/node/pull/9268) (Ben Noordhuis) [#1116](https://github.com/iojs/io.js/pull/1116).

* **tls**: tiếp tục báo cáo về memory leak thông qua sự xuất hiện các leak nhỏ trong các trường hợp sử dụng, theo dõi tiến độ tại [#1075](https://github.com/iojs/io.js/issues/1075).

* **v8**: sửa chữa 1 lỗi tràn 1 số integer khi giá trị được sử dụng`--max_old_space_size` trên `4096` (Ben Noordhuis) [#1166](https://github.com/iojs/io.js/pull/1166).

* **platforms**: Hệ thống io.js Travis CI thông báo đã vượt qua trên **FreeBSD** và **SmartOS** (_Solaris_).

* **npm**: cập nhật npm lên 2.7.1. Xem chi tiết tại [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v271-2015-03-05) .

### Các lỗi hiện tại

* Các vấn đề memory leak còn lại liên quan đến TLS, chi tiết tại [#1075](https://github.com/iojs/io.js/issues/1075).

* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)

* Không thể xây dựng io.js như là 1 static library [#686](https://github.com/iojs/io.js/issues/686)

* `process.send()` là không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) và được sửa trong [#774](https://github.com/iojs/io.js/issues/774)

* Gọi `dns.setServers()` khi 1 truy vấn DNS  đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)

# Cập nhật từ cộng đồng

* browserify hỗ trợ io.js, bạn có thể xem thông báo ở [đây](https://twitter.com/yosuke_furukawa/status/577150547850969088)

* express.js [hỗ trợ](https://github.com/strongloop/express/commit/165660811aa9ba5f3733a7b033894f3d9a9c5e60) thêm io.js

* Trong 2 tuần qua chúng ta đã truy cập vào phần cứng từ Joyent và cập nhật 1 bản phá cho V8 nên chúng ta đã có 1 bản io.js building. Sau đó là việc vượt qua các bài test trên [SmartOS](https://github.com/iojs/build/pull/64) và [FreeBSD](https://github.com/iojs/io.js/pull/1167) 2 ngày trước , cảm ơn sự đóng góp tuyệt vời của build team và [Johan Bergström](https://github.com/jbergstroem)

* [Petka Antonov](https://github.com/petkaantonov) đã đề xuất triển khai workers trên io.js dưới --experimental-workers flag, bạn có thể tham gia thảo luận tại đây [here](https://github.com/iojs/io.js/pull/1159)

* io.js [nâng cấp](https://github.com/iojs/io.js/pull/1206) openssl lên `1.0.1m`

# Sự kiện sắp diễn ra

* Vé [NodeConf](http://nodeconf.com/) đã được bán, diễn ra vào ngày 08-09 tháng 6 tại Oakland, CA và NodeConf Adventure vào ngày June 11 - 14 tháng 6 tại Walker Creek Ranch, CA

* Vé [CascadiaJS](http://2015.cascadiajs.com/) đã được bán, diễn ra vào ngày 08 - 10 tháng 7 tại Washington State

* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
