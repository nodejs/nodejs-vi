---
layout: post
title: weekly update 2015-07-03
categories: [weekly]
tags: [weekly, draft]
description: weekly update 2015-07-03
---

### io.js and Node.js News — July 3rd

### Các tin tức mới về io.js và Node.js - 03/07

Important patches for io.js 1.8 and 2.3 and upcoming events.

Một bản phá lỗi quan trọng cho io.js 1.8 và 2.3 và các sự kiện sắp diễn ra.

### io.js 1.8 and 2.3 Releases

### Phát hành io.js 1.8 và 2.3

This week we have three io.js releases: [v2.3.2](https://iojs.org/dist/v2.3.2/) and two following important security patches [v1.8.3](https://iojs.org/dist/v1.8.3/) and [v2.3.3](https://iojs.org/dist/v2.3.3/), complete changelog from previous releases can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) with the [v1.x changelog here](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md).

Tuần này chúng ta có 3 bản phát hành io.js: [v2.3.2](https://iojs.org/dist/v2.3.2/) và 2 bản phá lỗi bảo mật quan trọng là  [v1.8.3](https://iojs.org/dist/v1.8.3/) và [v2.3.3](https://iojs.org/dist/v2.3.3/), toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md) và với các phiên bản [v1.x  tại đây](https://github.com/nodejs/io.js/blob/v1.x/CHANGELOG.md).

### Notable Changes

### Những thay đổi đáng chú ý

#### 1.8.3

#### 1.8.3

**Maintenance release**

**Phát hành bảo trì**

* **v8**: Fixed an out-of-band write in utf8 decoder. **This is an important security update** as it can be used to cause a denial of service attack.
* **v8**: Sửa 1 lỗi ghi out-of-band trong utf8 decoder. **Đây là 1 bản cập nhật bảo mật quan trọng** bởi lỗi có thể được khai thác sử dụng để tấn công từ chối dịch vụ.

* **openssl**: Upgrade to 1.0.2b and 1.0.2c, introduces DHE man-in-the-middle protection (Logjam) and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the [security advisory](https://www.openssl.org/news/secadv_20150611.txt) for full details. (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
* **openssl**: Cập nhật lên 1.0.2b và 1.0.2c, giới thiệu DHE man-in-the-middle protection (Logjam)và sửa malformed ECParameters gây lên vòng lặp vô hạn (CVE-2015-1788). Xem [tư vấn bảo mật](https://www.openssl.org/news/secadv_20150611.txt) để biết thêm chi tiết. (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)

* **build**:
  * Added support for compiling with Microsoft Visual C++ 2015
  * Thêm hỗ trợ cho biên dịch với Microsoft Visual C++ 2015

  * Started building and distributing headers*only tarballs along with binaries
  * Bắt đầu build và phân phối tarballs headers*only cùng với binaries

#### 2.3.2

* **build**:
  * Added support for compiling with Microsoft Visual C++ 2015
  * Thêm hỗ trợ cho biên dịch với Microsoft Visual C++ 2015

  * Started building and distributing headers*only tarballs along with binaries
  * Bắt đầu build và phân phối tarballs headers*only cùng với binaries

#### 2.3.3

* **deps**: Fixed an out-of-band write in utf8 decoder. **This is an important security update** as it can be used to cause a denial of service attack.
* **deps**: Sửa 1 lỗi ghi out-of-band trong utf8 decoder. **Đây là 1 bản cập nhật bảo mật quan trọng** bởi lỗi có thể được khai thác sử dụng để tấn công từ chối dịch vụ.

### Known Issues

### Các lỗi hiện tại

See https://github.com/nodejs/io.js/labels/confirmed-bug for complete and current list of known issues.

Xem đầy đủ các lỗi được biết đến hiện nay tại
https://github.com/nodejs/io.js/labels/confirmed-bug.

* Some problems with unreferenced timers running during `beforeExit` are still to be resolved. See [#1264](https://github.com/nodejs/io.js/issues/1264).
* Một vài vấn đề với unreferenced timers chạy trong  `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).

* Surrogate pair in REPL can freeze terminal. [#690](https://github.com/nodejs/io.js/issues/690)
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)

* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/nodejs/io.js/issues/760).
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, Xem [#760](https://github.com/iojs/io.js/issues/760) để biết thông tin chi tiết và được sửa đổi trong [#774]
(https://github.com/iojs/io.js/issues/774)

* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion. [#894](https://github.com/nodejs/io.js/issues/894)
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)

* `url.resolve` may transfer the auth portion of the url when resolving between two full hosts, see [#1435](https://github.com/nodejs/io.js/issues/1435).
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Community Updates

### Cập nhật từ cộng đồng

* Yosuke Furukawa will give a talk about the past, present, and future of Node.js in [YAPC Asia 2015](http://yapcasia.org/2015/), the largest conference in Japan's programming community. It will be hosted at Tokyo on August 20th - 22nd and his talk will specifically be on the 22nd. Details of the talk can be found [here](http://yapcasia.org/2015/talk/show/82e93a96-f60e-11e4-907e-8ab37d574c3a).
* Yosuke Furukawa sẽ có 1 bài nói về quá khứ, hiện tại, tương lai của Node.js tại [YAPC Asia 2015](http://yapcasia.org/2015/), một trong những hội nghị lớn nhất cho cộng đồng lập trình tại trình Nhật Bản. Nó sẽ được diễn ra tại Tokyo vào ngày 20 - 22 tháng 8 và bài nói của anh ấy sẽ được diễn ra cụ thể vào ngày 22. Thông tin chi tiết của bài nói có thể được tìn thấy [tại](http://yapcasia.org/2015/talk/show/82e93a96-f60e-11e4-907e-8ab37d574c3a).

* A security issue is found in v8 that can be used for DoS attacks against Node.js applications and servers running 0.12 and all versions of io.js. Critical security upgrades ([Node.js v0.12.6](http://nodejs.org/dist/v0.12.6/), [io.js 2.3.3](https://iojs.org/dist/v2.3.3/) and [io.js 1.8.3](https://iojs.org/dist/v1.8.3/)) have been released. Also, details about the issue can be found [on one of our Medium post](https://medium.com/@iojs/important-security-upgrades-for-node-js-and-io-js-8ac14ece5852). If you're running v1.8.2 or below, or v2.3.2 or below, please update them to io.js versions 1.8.3 and 2.3.3.

* Một lỗi bảo mật đã được tìm ra trong V8 và có thể được sử dụng cho tấn công DoS với các ứng dụng Node.js và servers chạy 0.12 cũng như tất cả các phiên bản của io.js. Bản nâng cấp bảo mật quan trọng là ([Node.js v0.12.6](http://nodejs.org/dist/v0.12.6/), [io.js 2.3.3](https://iojs.org/dist/v2.3.3/) và [io.js 1.8.3](https://iojs.org/dist/v1.8.3/)) đã được phát hành. Cùng với thông tin chi tiết của vấn đề này có thể được tìm thấy  [ triên 1 trong những bài viết Medium của chúng ta ](https://medium.com/@iojs/important-security-upgrades-for-node-js-and-io-js-8ac14ece5852). Nếu bạn đang chạy phiên bản v1.8.2 hay thấp hơn hoăc v2.3.2 hay thấp hơn, hãy nâng cấp chúng nên io.js versions 1.8.3 và 2.3.3.

### Upcoming Events

### Sự kiện sắp diễn ra

* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* [BrazilJS Conf](http://braziljs.com.br/) tickets are on sale, August 21st - 22nd at Shopping Center BarraShoppingSul
* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* [Node.js Italian Conference](http://nodejsconf.it/) tickets are on sale, October 10th at Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), October 16th - 17th at Ruta N, Medellin
