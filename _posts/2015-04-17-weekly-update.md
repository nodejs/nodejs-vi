---
layout: post
title: weekly update 2015-04-17
categories: [weekly]
tags: [weekly, publish]
description: weekly update 2015-04-17
---

# Phát hành io.js 1.7

Tuần này chúng ta có 2 bản phát hành io.js là [v1.7.0](https://iojs.org/dist/v1.7.0/) và [v1.7.1](https://iojs.org/dist/v1.7.1/), toàn bộ các thay đổi bạn có thể tìm [trên GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).

### Những thay đổi đáng chú ý

* **build**: Lỗi cú pháp ở Makefile cho release builds gây ra bởi 1.7.0 đã phát hiện và không được phát hành. (Rod Vagg) [#1421](https://github.com/iojs/io.js/pull/1421).
* **C++ API**: Fedor Indutny đã đóng góp 1 tính năng đến V8 và cũng đã được thêm vào bản V8 đi kèm trong io.js. `SealHandleScope` cho phép 1 author C++ add-on _seal_ 1 `HandleScope` để ngăn chăn sự phân bổ ngoài ý muốn bên trong nó.
Hiện nay nó chỉ được kích hoạt cho debug builds io.js.
Tính năng này giúp phát hiện leak trong  [#1075](https://github.com/iojs/io.js/issues/1075)
và giờ được kích hoạt tại root `HandleScope` trong io.js. (Fedor Indutny) [#1395](https://github.com/iojs/io.js/pull/1395).
* **ARM**: Bản phát hành này bao gồm các công việc quan trọng để cải thiện việc hỗ trợ hiện tại ARM cho builds và tests.
Bản build io.js CI cluster's ARMv6, ARMv7 và ARMv8 báo cáo đã vượt qua (gần hết) các tests và builds.
  * ARMv8 64-bit (AARCH64) hiện đã hỗ trợ đúng cách, bao gồm việc thêm các sửa đổi trong libuv sự nhầm lẫn trong việc phát hiện sự tồn tại của `epoll_wait()`. (Ben Noordhuis) [#1365](https://github.com/iojs/io.js/pull/1365).
  * ARMv6: [#1376](https://github.com/iojs/io.js/issues/1376) báo cáo 1 vấn đề với `Math.exp()` trên ARMv6 (bao gồm Raspberry Pi). Thủ phạm là sai sót codegen cho ARMv6 khi sử dụng tính năng "fast math" của V8. `--nofast_math` đã được bật cho tất cả biến thể ARMv6 để tránh điều này, fast math có thể được bật lại thông qia  `--fast_math`. (Ben Noordhuis) [#1398](https://github.com/iojs/io.js/pull/1398).
  * Tests: timeouts được điều chỉnh đặc biệt cho các nền tảng chậm hơn, phát hiện tại ARMv6 và ARMv7. (Roman Reiss) [#1366](https://github.com/iojs/io.js/pull/1366).
* **npm**: Cập nhật npm lên 2.7.6. Xem chi tiết tại [release notes](https://github.com/npm/npm/releases/tag/v2.7.6).

### Vấn đề tồn tại

* Một vài vấn đề với unreferenced timers chạy khi `beforeExit`vẫn đang được giải quyết. Tham khảo [#1264](https://github.com/iojs/io.js/issues/1264) để biết thêm chi tiết.
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, Xem [#760](https://github.com/iojs/io.js/issues/760) để biết thông tin chi tiết và được sửa đổi trong [#774]
(https://github.com/iojs/io.js/issues/774)
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* readline: Bộ phận escapes không làm việc một cách chính xác, xem [#1403](https://github.com/iojs/io.js/issues/1403) để biết thêm chi tiết.

### Cập nhật từ cộng đồng

* Sự khác biệt giữa io.js và The Node Foundation [iojs/io.js#1416]
(https://github.com/iojs/io.js/issues/1416).
* NPM ra mắt các module private and npm inc [raises](http://techcrunch.com/2015/04/14/popular-javascript-package-manager-npm-raises-8m-launches-private-modules/).
* Các ý kiến của Node.js Foundation on [Medium](https://medium.com/@programmer/thoughts-on-node-foundation-abcf86c72786).
* io.js v1.8.0 crypto performance trên [io.js wiki](https://github.com/iojs/io.js/wiki/Crypto-Performance-Notes-for-OpenSSL-1.0.2a-on-iojs-v1.8.0).
* io.js được đề cập trên [Oracle's blog](https://blogs.oracle.com/java-platform-group/entry/node_js_and_io_js).
* Trạng thái của io.js Build [April 2015](https://github.com/iojs/build/issues/77)

### Các sự kiện sắp diễn ra

* [JSConf Uruguay](http://jsconf.uy) vé đã được bán, diễn ra tại April 24th & 25th Montevideo, Uruguay
* [NodeConf Adventure](http://nodeconf.com/) vé đã được bán, diễn ra tại June 11th - 14th Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) vé đã được bán, diễn ra tại July 8th - 10th Washington State
* [NodeConf EU](http://nodeconf.eu/) vé đã được bán, diễn ra tại September 6th - 9th Waterford, Ireland
