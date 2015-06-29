---
layout: post
title: weekly update 2015-05-29
categories: [weekly]
tags: [weekly, publish]
description: weekly update 2015-05-29
---

# Phát hành io.js 2.2

Tuần này chúng ta có 2 bản phát hành io.js [v2.2.0](https://iojs.org/dist/v2.2.0/) và [v2.2.1](https://iojs.org/dist/v2.2.1/),
toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).

### Những thay đổi đáng chú ý

#### v2.2.0

* **node**: Tăng tốc cho `require()` bằng cách thay thế sử dụng của `fs.statSync()` và `fs.readFileSync()` bằng các biến nội bộ như vậy sẽ nhanh hơn trong trường hợp này và không tạo quá nhiều objects cho garbage collector phải dọn dẹp. Hai lợi ích chính là : gia tăng đáng kể được thời gian khởi động cho các ứng dụng phổ biến vả cải thiện thời gian khởi động cho debugger bằng cách bỏ qua tất cả exception events. (Ben Noordhuis) [#1801](https://github.com/nodejs/io.js/pull/1801).
* **node**: Pre-load modules (`-r` or `--require`) giờ hoạt động theo các chuẩn quy tắc của `require()` hơn là giải quyết vấn đề đường dẫn, giờ bạn đã có thể pre-load modules trong node_modules. (Ali Ijaz Sheikh) [#1812](https://github.com/nodejs/io.js/pull/1812).
* **npm**: Cập nhật npm to v2.11.0. Thêm hooks mới cho `preversion`, `version`, và `postversion` lifecycle events, thay đổi 1 vài giấy phép SPDX-related. Xem chi tiết tại [release notes](https://github.com/npm/npm/releases/tag/v2.11.0).

#### v2.2.1

* **http**: phục hồi lại 1 thuộc tính đã được xóa bỏ nhưng không ghi chép đó là `client` trong client connections, thuộc tính này được sử dụng khá phổ biến, nổi bật là [request](https://github.com/request/request) được sử dụng bởi npm. (Michaël Zasso) [#1852](https://github.com/nodejs/io.js/pull/1852).

### Các lỗi hiện tại

Xem đầy đủ các lỗi được biết đến hiện nay tại https://github.com/nodejs/io.js/labels/confirmed-bug

* Một vài vấn đề với unreferenced timers chạy trong  `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, Xem [#760](https://github.com/iojs/io.js/issues/760) để biết thông tin chi tiết và được sửa đổi trong [#774]
(https://github.com/iojs/io.js/issues/774)
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Cập nhật từ cộng đồng

* [Việc tách và hòa hợp ](https://nodesource.com/blog/was-this-trip-really-necessary) trong cộng đồng Node bởi Rod Vagg.
* Làn đầu tiên Node TSC Meeting có mặt trên [SoundCloud](https://soundcloud.com/node-foundation/tsc-meeting-2015-05-27).
* io.js có 1 nhóm mới Benchmarking Working Group [nodejs/benchmarking#1](https://github.com/nodejs/benchmarking/issues/1).
* Bài viết về iojs + node.js dưới tên Node Foundation bởi [nodejs.com](http://blog.nodejs.org/2015/05/15/the-nodejs-foundation-benefits-all/).
* io.js triển khai tag mới là [`good first contribution`](https://github.com/nodejs/io.js/labels/good%20first%20contribution) cho những đóng góp mới.
* Bài viết từ [TheNewStack](http://thenewstack.io/io-js-and-node-js-have-united-and-thats-a-good-thing/) về mới quan hệ mới của iojs và node.js.
* Oliver Zeigermann tạo mới 1 [repo](https://github.com/DJCordhose/ecmascript-2015-iojs) về triển khải ES6 và iojs.

### Sự kiện sắp diễn ra

* Vé [NodeConf Adventure](http://nodeconf.com/) đã được bán, diễn ra vào ngày 11 - 14 tháng 6 tại Walker Creek Ranch, CA
* Vé [CascadiaJS](http://2015.cascadiajs.com/) đã được bán, diễn ra vào ngày 08 - 10 tháng 7 tại Washington State
* Vé [BrazilJS Conf](http://braziljs.com.br/) đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
