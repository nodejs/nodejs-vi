---
layout: post
title: weekly update 2015-06-26
categories: [weekly]
tags: [weekly, publish]
description: weekly update 2015-06-26
---

# Các tin tức mới về io.js và Node.js
Tuần này chúng ta có 1 bản phát hành io.js [ v2.3.1](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md#2015-06-23-version-231-rvagg), toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).

### Những thay đổi đáng chú ý
* **module**: Số lần syscalls  được tạo ra trong một `require()` đã được giảm đáng kể 1 lần nữa (xem tại [#1801](https://github.com/nodejs/io.js/pull/1801) của v2.2.0 cho lần sửa đổi trước), dẫn đến một cải thiện về hiệu năng (Pierre Inglebert) [#1920](https://github.com/nodejs/io.js/pull/1920).

* **npm**:
  * Cập nhật lên [v2.11.2](https://github.com/npm/npm/releases/tag/v2.11.2) (Rebecca Turner) [#1956](https://github.com/nodejs/io.js/pull/1956).
  * Cập nhật lên [v2.11.3](https://github.com/npm/npm/releases/tag/v2.11.3) (Forrest L Norvell) [#2018](https://github.com/nodejs/io.js/pull/2018).

* **zlib**: Một lỗi được phát hiện ra, quá trình xử lý có thể bị dừng nếu như phần cuối của 1 kết quả giải nén zlib trong bộ nhớ đệm vượt quá `0x3fffffff` byte (~ 1GiB). Điều này có thể chỉ sảy ra trong quá trình giải nén bộ nhớ đệm (hơn là trong streaming) và đã được sửa đồng thời sẽ ném ra 1  `RangeError` (Michaël Zasso)  [#1811](https://github.com/nodejs/io.js/pull/1811).

### Các lỗi hiện tại

Xem đầy đủ các lỗi được biết đến hiện nay tại
https://github.com/nodejs/io.js/labels/confirmed-bug.

* Một vài vấn đề với unreferenced timers chạy trong  `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, Xem [#760](https://github.com/iojs/io.js/issues/760) để biết thông tin chi tiết và được sửa đổi trong [#774]
(https://github.com/iojs/io.js/issues/774)
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Cập nhật từ cộng đồng

* Slide deck: [Hội thảo online về Bluemix: Triển khai  một ứng dụng Full Stack Node.js lên IBM Bluemix](https://speakerdeck.com/bradleyholt/bluemix-webinar-deploying-a-full-stack-node-dot-js-application-to-ibm-bluemix)
* Bài viết bởi RisingStack: [Làm cách nào để sử dụng Rust với Node.js khi  Performance là vấn đề ](http://blog.risingstack.com/how-to-use-rust-with-node-when-performance-matters/)
* Device Atlas API bắt đầu [hỗ trợ Node.js](https://deviceatlas.com/blog/deviceatlas-api-node-js?utm_source=twitter&utm_medium=update&utm_campaign=node%20js%20support)
* [Bảo trì trên 1 Native Node Module](http://www.voodootikigod.com/on-maintaining-a-native-node-module/) by Chris Williams
* [nodei.co](http://twitter.com/rvagg/status/613688739030679552) đang chạy với io.js
* npm [3.0.0 pre-release](https://github.com/npm/npm/releases/tag/v3.0.0)

### Sự kiện sắp diễn ra

* Vé [CascadiaJS](http://2015.cascadiajs.com/) đã được bán, diễn ra vào ngày 08 - 10 tháng 7 tại Washington State
* Vé [BrazilJS Conf](http://braziljs.com.br/) đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
* Vé [Node.js Italian Conference](http://nodejsconf.it/) đã được bán, diễn ra vào ngày 10 tháng 10 tại Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), diễn ra vào ngày 16 - 17 tháng 10 tại Ruta N, Medellin
