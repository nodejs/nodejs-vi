---
layout: post
title: weekly update 2015-07-17
categories: [weekly]
tags: [weekly, publish]
description: Thông tin cập nhật tuần 2015-07-17
---

### Các tin tức mới về io.js và Node.js - 10/17

Phát hành io.js 2.4.0, Apigee gia nhập vào foundation của chúng ta và bắt đầu Intl WG.

### io.js 2.4 Release

Tuần này chúng ta có 1 bản phát hành io.js là [v2.4.0](https://iojs.org/dist/v2.4.0/), toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).

### Những thay đổi đáng chú ý

#### 2.4.0

* **src**: Thêm 1 flag `--track-heap-objects` mới để theo dõi sự phân bổ các đối tượng heap cho heap snapshots (Bradley Meck) [#2135](https://github.com/nodejs/io.js/pull/2135).
* **readline**: Sửa 1 lỗi có thể làm treo repl nếu 1 keypress event handler được ném ra (Alex Kocharin) [#2107](https://github.com/nodejs/io.js/pull/2107).
* **npm**: Cập nhật lên v2.13.0, các ghi chú cho bản phát hành có thể tìm thấy tại <https://github.com/npm/npm/releases/tag/v2.13.0> (Forrest L Norvell) [#2152](https://github.com/nodejs/io.js/pull/2152).

### Các lỗi hiện tại

Xem đầy đủ các lỗi được biết đến hiện nay tại
https://github.com/nodejs/io.js/labels/confirmed-bug.

* Một vài vấn đề với unreferenced timers chạy trong `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, xem [#760](https://github.com/iojs/io.js/issues/760).
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Cập nhật từ cộng đồng

* NodeSource thông báo về N\|Support trên [blog của họ](https://nodesource.com/blog/nodesource-announces-nsupport). N\|Support là 1 hỗ trợ cao cấp cho những người phát triển Node.js DevOps hay những nhóm hoạt động công nghệ thông tin. Để tìm hiểu thêm về dịch vụ N\|Support tại [đây](https://nodesource.com/products/nsupport).
* [Apigee](https://apigee.com/) [đã được thêm vào Node Foundation](https://github.com/nodejs/nodejs.org/pull/151)
* [joyent/docker-node](https://github.com/joyent/docker-node) đã được sáp nhập với  [nodejs/docker](https://github.com/nodejs/docker-iojs). Và như kết quả, [@chorrell](https://github.com/chorrell) và [@dcrudgington](https://github.com/dcrudgington) đã tham gia [@nodejs/docker](https://github.com/orgs/nodejs/teams/docker) team.
* [Intl](https://github.com/nodejs/intl) WG đã được đề xướng. Chúng được dành riêng cho việc hỗ trợ và cải thiện vấn đề Quốc tế và Bản địa hóa trong Node. Intl WG đang kêu gọi mọi người tham gia tại [issue](https://github.com/nodejs/Intl/issues/5).

### Sự kiện sắp diễn ra

* Vé [BrazilJS Conf](http://braziljs.com.br/) đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
* Vé [Node.js Italian Conference](http://nodejsconf.it/) đã được bán, diễn ra vào ngày 10 tháng 10 tại Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), diễn ra vào ngày 16 - 17 tháng 10 tại Ruta N, Medellin
