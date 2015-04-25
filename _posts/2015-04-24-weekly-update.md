---
layout: post
title: weekly update 2015-04-24
categories: [weekly]
tags: [weekly, publish]
description: weekly update 2015-04-24
---

# Phát hành io.js 1.8.1

Tuần này chúng ta có 1 bản phát hành [v1.8.1](https://iojs.org/dist/v1.8.1/). Thông tin đẩy đủ các thay đổi bạn có thể tìm [tại GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).

### Những thay đổi đáng chú ý

* **THÔNG BÁO**: Bỏ qua v1.8.0 do các vấn đề về release tooling.
  Xem chi tiết tại [#1436](https://github.com/iojs/io.js/issues/1436).
* **build**: Hỗ trợ cho build io.js như là 1 bộ thư viện tĩnh (Marat Abdullin) [#1341](https://github.com/iojs/io.js/pull/1341)
* **deps**: Cập nhật openssl lên 1.0.2a (Shigeki Ohtsu) [#1389](https://github.com/iojs/io.js/pull/1389)
  * Người dùng nên thấy hiệu xuất được cải thiện khi sử dụng crypto API.
Xem chi tiết  [tại](https://github.com/iojs/io.js/wiki/Crypto-Performance-Notes-for-OpenSSL-1.0.2a-on-iojs-v1.8.0).
* **npm**: Cập nhật npm lên 2.8.3. Xem chi tiết tại [release notes](https://github.com/npm/npm/releases/tag/v2.8.3). Bao gồm việc cải thiện hỗ trợ git.
* **src**: Cho phép truyền nhiều tham số vào process.nextTick (Trevor Norris) [#1077](https://github.com/iojs/io.js/pull/1077)
* **module**: Sự tương tác của `require('.')` với `NODE_PATH` đã được phục hồi và bị phản đối. Chức năng này sẽ bị xóa bỏ tại (Roman Reiss) [#1363](https://github.com/iojs/io.js/pull/1363)

### Vấn đề tồn tại

* Một vài vấn đề với unreferenced timers chạy khi `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/iojs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, xem [#760](https://github.com/iojs/io.js/issues/760) và được sửa trong [#774](https://github.com/iojs/io.js/issues/774)
* Gọi `dns.setServers()` khi 1 truy vấn DNS  đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).
* readline: tách escapes được sử lý không đúng, xem tại [#1403](https://github.com/iojs/io.js/issues/1403)

### Cập nhật từ cộng đồng

* Fedor Indutny đã mở 1 thảo luận về việc xóa TLS `newSession` và `resumeSession` event. [iojs/io.js#1462](https://github.com/iojs/io.js/issues/1462)
* Đề cử thay đổi C HTTP parser JS HTTP parser [here](https://github.com/iojs/io.js/pull/1457)
* Nhà sáng lập NPM nói về io.js tại [InfoWorld](http://www.infoworld.com/article/2910594/node-js/npm-founder-foresees-merger-node-js-io-js.html)
* Đề cử thêm mikeal, mscdex, shigeki làm thành viên mới của TC members. [iojs/io.js#1483](https://github.com/iojs/io.js/issues/1483#issuecomment-95128140)

### Các sự kiện sắp diễn ra

* [JSConf Uruguay](http://jsconf.uy) vé đã được bán, diễn ra tại April 24th & 25th Montevideo, Uruguay
* [NodeConf Adventure](http://nodeconf.com/) vé đã được bán, diễn ra tại June 11th - 14th Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) vé đã được bán, diễn ra tại July 8th - 10th Washington State
* [NodeConf EU](http://nodeconf.eu/) vé đã được bán, diễn ra tại September 6th - 9th Waterford, Ireland
