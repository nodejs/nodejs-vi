---
layout: post
title: weekly update 2015-07-31
categories: [weekly]
tags: [weekly, publish]
description: Thông tin cập nhật tuần 2015-07-31
---

### Các tin tức mới về io.js và Node.js - 10/31

io.js v2.5.0 và lời mời cho 1 vị trí bảo trì V8 cho LTS build.

### Phát hành io.js 2.5

Tuần này chúng ta có 1 bản phát hành io.js là [v2.5.0](https://iojs.org/dist/v2.5.0/), toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).

### Những thay đổi đáng chú ý

* **https**: Tái sử dụng lại TLS sessions trong Agent (Fedor Indutny) [#2228](https://github.com/nodejs/io.js/pull/2228)
* **src**: giải mã base64 nhanh hơn 50% (Ben Noordhuis) [#2193](https://github.com/nodejs/io.js/pull/2193)
* **npm**: Cập nhật lên v2.13.2, các ghi chú cho bản phát hành có thể tìm thấy tại <https://github.com/npm/npm/releases/tag/v2.13.2> (Kat Marchán) [#2241](https://github.com/nodejs/io.js/pull/2241).

### Các lỗi hiện tại

Xem đầy đủ các lỗi được biết đến hiện nay tại
https://github.com/nodejs/io.js/labels/confirmed-bug.

* Một vài vấn đề với unreferenced timers chạy trong `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, xem [#760](https://github.com/iojs/io.js/issues/760).
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Cập nhật từ cộng đồng

* Chúng ta cần 1 người bào trì V8 cho bản build LTS! Truy cập [GitHub](https://github.com/nodejs/LTS/issues/28)
để xem thông tin chi tiết nếu các yêu cầu phù hợp với khả năng của bạn.
* [Milo Mordaunt](https://twitter.com/bananaoomarang) đã viết 1 bài viết về việc mở rộng [IFTTT với Webtask.io chạy Node.js ](https://auth0.com/blog/2015/07/28/if-this-then-node-dot-js-extending-ifttt-with-webtask-dot-io/?utm_source=io.js+and+Node.js+News&utm_medium=article) trên [Auth0](https://auth0.com/blog).
* [Hemanth.HM](https://twitter.com/gnumanth), tác giả và người đóng góp cho hơn 200 modules trên npm, đã viết 1 bài viết về [authoring Node modules](http://h3manth.com/new/blog/2015/authoring-node-modules/?utm_source=io.js+and+Node.js+News&utm_medium=article).

Nếu bạn phát hiện hay viết 1 điều gì đó về Node.js và io.js. Hãy truy cập vào [Evangelism team repo](https://github.com/nodejs/evangelism) và gợi ý bài viết tại trang [Issues](https://github.com/nodejs/evangelism/issues),  gắn thẻ là Weekly Updates.

### Sự kiện sắp diễn ra

* Vé [BrazilJS Conf](http://braziljs.com.br/) đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
* Vé [Node.js Italian Conference](http://nodejsconf.it/) đã được bán, diễn ra vào ngày 10 tháng 10 tại Desenzano - Brescia, Italy
* [JSConf CO](http://www.jsconf.co/), diễn ra vào ngày 16 - 17 tháng 10 tại Ruta N, Medellin

Có 1 sự kiện về Node.js và io.js sắp diễn ra? Bạn có thể đặt sự kiện của bạn tại đâu thông qua [Evangelism team repo](https://github.com/nodejs/evangelism) và thông báo tại trang [Issues](https://github.com/nodejs/evangelism/issues),  gắn thẻ là Weekly Updates.
