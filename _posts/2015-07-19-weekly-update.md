---
layout: post
title: weekly update 2015-07-10
categories: [weekly]
tags: [weekly, publish]
description: weekly update 2015-07-10
---

### Các tin tức mới về io.js và Node.js - 10/07

Một bản phá lỗi quan trọng cho io.js 1.8 và 2.3 và các sự kiện sắp diễn ra.

### io.js 1.8 and 2.3 Releases

Tuần này chúng ta có 2 bản phát hành io.js: [v2.3.4](https://iojs.org/dist/v2.3.4/) và [v1.8.4](https://iojs.org/dist/v1.8.4/), toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) và với các phiên bản [v1.x  tại đây](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md).

### Những thay đổi đáng chú ý

#### 1.8.4

**Phát hành bảo trì**

* **openssl**: Cập nhật lên 1.0.2d, sửa lỗi CVE-2015-1793 (Alternate Chains Certificate Forgery) [#2141](https://github.com/nodejs/io.js/pull/2141).

#### 2.3.4

* **openssl**: Cập nhật lên 1.0.2d, sửa lỗi CVE-2015-1793 (Alternate Chains Certificate Forgery) (Shigeki Ohtsu) [#2141](https://github.com/nodejs/io.js/pull/2141).
* **npm**: Cập nhật lên v2.12.1, các ghi chú cho bản phát hành có thể tìm thấy tại  <https://github.com/npm/npm/releases/tag/v2.12.0> và <https://github.com/npm/npm/releases/tag/v2.12.1> (Kat Marchán) [#2112](https://github.com/nodejs/io.js/pull/2112).

### Các lỗi hiện tại

Xem đầy đủ các lỗi được biết đến hiện nay tại
https://github.com/nodejs/io.js/labels/confirmed-bug.

* Một vài vấn đề với unreferenced timers chạy trong `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, Xem [#760](https://github.com/iojs/io.js/issues/760) để biết thông tin chi tiết
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Cập nhật từ cộng đồng

* OpenSSL thông báo 1 [vấn đề bảo mật quan trọng](https://mta.openssl.org/pipermail/openssl-announce/2015-July/000037.html), io.js và Node.js đã vừa cập nhật OpenSSL và sửa lỗi đó.
* Node.js LTS WG vừa cập nhật bản[ đề xuất kế hoạch của họ về LTS](https://github.com/nodejs/LTS/blob/master/README.md#example). Họ cần 1 vài phải hồi từ người dùng Node.
* ReactNative đã thêm io.js như là [nền tảng test của họ](https://github.com/facebook/react-native/blob/master/.travis.yml#L24).

### Sự kiện sắp diễn ra

* Vé [BrazilJS Conf](http://braziljs.com.br/) đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
* Vé [Node.js Italian Conference](http://nodejsconf.it/) đã được bán, diễn ra vào ngày 10 tháng 10 tại Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), diễn ra vào ngày 16 - 17 tháng 10 tại Ruta N, Medellin
