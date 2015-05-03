---
layout: post
title: weekly-update 2015-03-06
categories: [weekly]
tags: [weekly, publish]
description: io.js 1.5.0 Release
---

# Ra mắt io.js 1.5.0

Thứ Sáu, ngày 6 tháng Ba, [@rvagg](https://github.com/rvagg) ra mắt io.js [**v1.5.0**](https://iojs.org/dist/latest/).  Nhật ký thay đổi đầy đủ có thể tìm thấy [trên GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).

### Các thay đổi đáng kể

* **buffer**: Phương thúc mới `Buffer#indexOf()`, mô hình dựa trên [`Array#indexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf). Nhận một Chuỗi, Buffer hay một Số. Chuỗi được xem dưới mã UTF-8. (Trevor Norris) [#561](https://github.com/iojs/io.js/pull/561)
* **fs**: Thuộc tính `options` trong các phương thúc của`'fs'`  ngưng các kiểm tra `hasOwnProperty()`, bằng cách đó cho phép các đối tượnng `options` có các thuộc tính prototype áp dụng được. (Jonathan Ong) [#635](https://github.com/iojs/io.js/pull/635)
* **tls**: Một lỗi tựa như tràn bộ nhớ TLS được báo cáo bởi PayPal. Có thể do một số thay đổi gần đây trong  **stream_wrap**. Bản vá ban đầu trong [#1078](https://github.com/iojs/io.js/pull/1078), bạn có thể xem tiến triển đóng lỗi tràn tại [#1075](https://github.com/iojs/io.js/issues/1075) (Fedor Indutny).
* **npm**: Nâng cấp lên 2.7.0. Xem [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v270-2015-02-26) để biết chi tiết bao gồm tại sao đây lại là semver-minor thay vì semver-major.
* **TC**: Colin Ihrig (@cjihrig) từ chức TC vì mong muốn được lập trình nhiều hơn và gặp mặt ít hơn.

### Các vấn đề đã biết

* Lỗi tràn bộ nhớ có thể, liên quan tới TLS. Chi tiết tại [#1075](https://github.com/iojs/io.js/issues/1075).
* Windows vẫn thông báo một số lỗi nhỏ trong các kiểm tra, chúng tôi đang ưu tiên xem xét các vấn đề này. Xem [#1005](https://github.com/iojs/io.js/issues/1005).
* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)
* Thông thể build io.js thành static library [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` không đồng bộ (synchronous) như tài liệu nói, một sự trở lại từ 1.0.2, xem [#760](https://github.com/iojs/io.js/issues/760) và được sửa trong [#774](https://github.com/iojs/io.js/issues/774)

# Thông báo Cộng đồng

* Bạn có thể an tâm rằng io.js và bản mới nhất của Node.js [**không bị ảnh hưởng**](https://strongloop.com/strongblog/are-node-and-io-js-affected-by-the-freak-attack-openssl-vulnerability/) bới [FREAK Attack](https://freakattack.com/).  Bạn đang chạy io.js hay node.js mới nhất đúng không?

* Walmart đang tài trợ một build machine cho hệ thống io.js Jenkins CI. Nhóm @iojs/build đang làm việc tạo các bản io.js binaries cho SunOS (giống như từ nodé.org). Bản vá V8 ([iojs/io.js#1079](https://github.com/iojs/io.js/pull/1079)) cần tới trước khi các qui trình khác có thể diễn ra. 
* Chúng tôi chân thành cảm ơn các công ty sau trong việc đóng góp phần cứng và các công nghệ / hỗ trợ / kỹ sư liên quan cho các bản build io.js:
  * **Digital Ocean** (đa phần Linux)
  * **Rackspace** (đa phần Windows)
  * **Voxer** (OS X và FreeBSD)
  * **NodeSource** (ARMv6 & ARMv7)
  * **Linaro** (ARMv8)
  * **Walmart** (SmartOS / Solaris)
* Cộng đồng io.js đã làm việc cực khổ để dịch tất cả các nội dung. Đang có hơn 20 ngôn ngữ hoạt động được đăng tải trên [iojs.org](http://iojs.org) và các  trang i18n. Thêm vào đó, các đường dẫn i18n ([iojs/website#258](https://github.com/iojs/website/pull/258)) đã được thêm vào các chân trang cho tiện. Chúng tôi thiếu ngôn ngữ của bạn? [Giúp chúng tôi và thêm nó!](https://github.com/iojs/website/blob/master/TRANSLATION.md)
* Speaking of translations, the [io.js roadmap presentation](http://roadmap.iojs.org/) has been updated to link to other language versions. Tiện việc nhắc đến việc dịch, thuyết trình [io.js roadmap](http://roadmap.iojs.org/) đã được cập nhật tới các ngôn ngữ khác.

* Dường như **PayPal** đang làm một thử nghiệm so sánh [Kappa](https://www.npmjs.com/package/kappa) trên io.js và node.js 0.12  và node.js v0.10. Nhóm PayPal đã xác định được một lỗi rất có thể là tràn bộ nhớ TLS. Bản vá ban đầu đã có trên [#1078](https://github.com/iojs/io.js/pull/1078) và trên đà kết thức trên [#1075](https://github.com/iojs/io.js/issues/1075)

* [**NodeSource**](http://nodesource.com) đang mang đến io.js các gói [binary Linux](https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories) cho Ubuntu/Debian cũng như các phân phối RHEL/Fedora.
* Bản [build Docker](https://registry.hub.docker.com/u/library/iojs/) của io.js là một trong 13 [Docker repositories chính thức](http://blog.docker.com/2015/03/thirteen-new-official-repositories-added-in-january-and-february/) được thêm vào Tháng Giêng và Tháng 2.

* Những thành viên NodeBots và IoT nên ăn mừng việc [**Tessel2**](http://blog.technical.io/post/112787427217/tessel-2-new-hardware-for-the-tessel-ecosystem) mới công bố rằng sẽ chạy trên [io.js như native](http://blog.technical.io/post/112888410737/moving-faster-with-io-js).
* [**@maxbeatty**](https://twitter.com/maxbeatty) đang làm việc trên bản mới cho back-end của [jsperf.com](http://jsperf.com/), chạy trên, nó hoàn toàn [mã nguồn mở](https://github.com/jsperf/jsperf.com).  Chào mừng các đóng góp của các bạn!

* [@eranhammer](https://twitter.com/eranhammer) ghi một bài viết gọi là [The Node Version Dilemma](http://hueniverse.com/2015/03/02/the-node-version-dilemma/), thảo luận về các phiên bản của node.js/ io.js và các đề xuất lúc nào và cái nào để dùng chúng.



# Các hỗ trợ mới cho io.js

* **[scrypt](https://npmjs.com/scrypt)** hỗ trợ io.js. Xem thêm: [GitHub issue](https://github.com/barrysteyn/node-scrypt/issues/39)
* **[proxyquire](https://github.com/thlorenz/proxyquire)** v1.3.2 ra mắt với hỗ trợ cho io.js.