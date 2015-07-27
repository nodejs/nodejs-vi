---
layout: post
title: weekly update 2015-07-03
categories: [weekly]
tags: [weekly, publish]
description: weekly update 2015-07-03
---

### Các tin tức mới về io.js và Node.js - 03/07

Một bản phá lỗi quan trọng cho io.js 1.8 và 2.3 và các sự kiện sắp diễn ra.

### Phát hành io.js 1.8 và 2.3

Tuần này chúng ta có 3 bản phát hành io.js: [v2.3.2](https://iojs.org/dist/v2.3.2/) và 2 bản phá lỗi bảo mật quan trọng là  [v1.8.3](https://iojs.org/dist/v1.8.3/) và [v2.3.3](https://iojs.org/dist/v2.3.3/), toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) và với các phiên bản [v1.x  tại đây](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md).

### Những thay đổi đáng chú ý

#### 1.8.3

**Phát hành bảo trì**

* **v8**: Sửa 1 lỗi ghi out-of-band trong utf8 decoder. **Đây là 1 bản cập nhật bảo mật quan trọng** bởi lỗi có thể được khai thác sử dụng để tấn công từ chối dịch vụ.
* **openssl**: Cập nhật lên 1.0.2b và 1.0.2c, giới thiệu DHE man-in-the-middle protection (Logjam)và sửa malformed ECParameters gây lên vòng lặp vô hạn (CVE-2015-1788). Xem [tư vấn bảo mật](https://www.openssl.org/news/secadv_20150611.txt) để biết thêm chi tiết. (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
* **build**:
  * Thêm hỗ trợ cho biên dịch với Microsoft Visual C++ 2015
  * Bắt đầu build và phân phối headers*only tarballs cùng với binaries

#### 2.3.2

* **build**:
  * Thêm hỗ trợ cho biên dịch với Microsoft Visual C++ 2015
  * Bắt đầu build và phân phối headers*only tarballs cùng với binaries

#### 2.3.3

* **deps**: Sửa 1 lỗi ghi out-of-band trong utf8 decoder. **Đây là 1 bản cập nhật bảo mật quan trọng** bởi lỗi có thể được khai thác sử dụng để tấn công từ chối dịch vụ.

### Các lỗi hiện tại

Xem đầy đủ các lỗi được biết đến hiện nay tại
https://github.com/nodejs/io.js/labels/confirmed-bug.

* Một vài vấn đề với unreferenced timers chạy trong  `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, Xem [#760](https://github.com/iojs/io.js/issues/760) để biết thông tin chi tiết
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Cập nhật từ cộng đồng

* Yosuke Furukawa sẽ có 1 bài nói về quá khứ, hiện tại, tương lai của Node.js tại [YAPC Asia 2015](http://yapcasia.org/2015/), một trong những hội nghị lớn nhất cho cộng đồng lập trình tại trình Nhật Bản. Nó sẽ được diễn ra tại Tokyo vào ngày 20 - 22 tháng 8 và bài nói của anh ấy sẽ được diễn ra cụ thể vào ngày 22. Thông tin chi tiết của bài nói có thể được tìn thấy [tại](http://yapcasia.org/2015/talk/show/82e93a96-f60e-11e4-907e-8ab37d574c3a).
* Một lỗi bảo mật đã được tìm ra trong V8 và có thể được sử dụng cho tấn công DoS với các ứng dụng Node.js và servers chạy 0.12 cũng như tất cả các phiên bản của io.js. Bản nâng cấp bảo mật quan trọng là ([Node.js v0.12.6](http://nodejs.org/dist/v0.12.6/), [io.js 2.3.3](https://iojs.org/dist/v2.3.3/) và [io.js 1.8.3](https://iojs.org/dist/v1.8.3/)) đã được phát hành. Cùng với thông tin chi tiết của vấn đề này có thể được tìm thấy  [ triên 1 trong những bài viết Medium của chúng ta ](https://medium.com/@iojs/important-security-upgrades-for-node-js-and-io-js-8ac14ece5852). Nếu bạn đang chạy phiên bản v1.8.2 hay thấp hơn hoăc v2.3.2 hay thấp hơn, hãy nâng cấp chúng nên io.js versions 1.8.3 và 2.3.3.

### Sự kiện sắp diễn ra

* Vé [CascadiaJS](http://2015.cascadiajs.com/) đã được bán, diễn ra vào ngày 08 - 10 tháng 7 tại Washington State
* Vé [BrazilJS Conf](http://braziljs.com.br/) đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
* Vé [Node.js Italian Conference](http://nodejsconf.it/) đã được bán, diễn ra vào ngày 10 tháng 10 tại Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), diễn ra vào ngày 16 - 17 tháng 10 tại Ruta N, Medellin
