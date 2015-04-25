---
layout: post
title: weekly update 2015-04-10
categories: [weekly]
tags: [weekly, publish]
description: weekly update 2015-04-10
---

# Phát hành io.js 1.6.4

Tuần này chúng ta 1 có 1 bản phát hành iojs là [v1.6.4](https://iojs.org/dist/v1.6.4/), toàn bộ thay đổi bạn có thể tìm ở [Github](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).

### Thay đổi đáng chú ý
* **npm**: Cập nhật npm lên 2.7.5. Xem chi tiết tại [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v275-2015-03-26). Bao gồm 2 bản sửa lỗi bảo mật quan trọng

* **openssl**: Hoàn thành công việc sơ bộ cho việc nâng cấp lên OpenSSL 1.0.2a [#1325](https://github.com/iojs/io.js/pull/1325) (Shigeki Ohtsu). Tham khảo [#589](https://github.com/iojs/io.js/issues/589) để biết thêm thông tin.

* **timers**: Một leak nhỏ bộ nhớ khi timers là unreferenced đã được sửa chữa, bên cạnh 1 số vấn đề liên quan đến timers [#1330](https://github.com/iojs/io.js/pull/1330) (Fedor Indutny). Báo cáo các leak còn lại được fixed tại đây [#1075](https://github.com/iojs/io.js/issues/1075).

* **android**: Bây giờ có thể biên dịch io.js cho Android và các thiết bị liên quan [#1307](https://github.com/iojs/io.js/pull/1307) (Giovanny Andres Gongora Granada).

### Vấn đề tồn tại
* Một vài vấn đề với unreferenced timers chạy khi `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/iojs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* Không thể xây dựng io.js như là 1 static library [#686](https://github.com/iojs/io.js/issues/686)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, xem [#760](https://github.com/iojs/io.js/issues/760) và được sửa trong [#774](https://github.com/iojs/io.js/issues/774)
* Gọi `dns.setServers()` khi 1 truy vấn DNS  đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)

### Cập nhật từ cộng đồng

* Bản nháp về chính sách Node Foundation dev ở đây [đây](https://github.com/jasnell/dev-policy)
* ARMv8 / ARM64 [hỗ trợ](https://twitter.com/rvagg/status/586050873349939201) io.js
* Tiếp tục công việc cho bản nháp chính sách dev  [node.js/io.js](https://github.com/jasnell/dev-policy)
* Cuộc họp TC [Wednesday](https://www.youtube.com/watch?v=OjlK8k10oyo)

### Các sự kiện sắp diễn ra

* [JSConf Uruguay](http://jsconf.uy) vé đã được bán, diễn ra tại April 24th & 25th Montevideo, Uruguay
* [NodeConf Adventure](http://nodeconf.com/) vé đã được bán, diễn ra tại June 11th - 14th Walker Creek Ranch, CA
* [CascadiaJS](http://2015.cascadiajs.com/) vé đã được bán, diễn ra tại July 8th - 10th Washington State
* [NodeConf EU](http://nodeconf.eu/) vé đã được bán, diễn ra tại September 6th - 9th Waterford, Ireland
* [nodeSchool Tokyo](http://nodejs.connpass.com/event/13182/) sẽ được tổ chức vào ngày April 12th tại Tokyo, Japan
