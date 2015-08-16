---
layout: post
title: weekly update 2015-07-31
categories: [weekly]
tags: [weekly, draft]
description: Thông tin cập nhật tuần 2015-07-31
---

### io.js and Node.js News — July 31st

### Các tin tức mới về io.js và Node.js - 10/31

io.js v2.5.0 and our call for an LTS build V8 maintainer.

io.js v2.5.0 và lời mời cho 1 vị trí 1 bảo trì V8 cho LTS build.

### io.js 2.5 Release

### Phát hành io.js 2.5

This week we have released io.js [v2.5.0](https://iojs.org/dist/v2.5.0/). The complete changelog for this version and previous releases can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).

Tuần này chúng ta có 1 bản phát hành io.js là [v2.5.0](https://iojs.org/dist/v2.5.0/), toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).

### Notable changes

### Những thay đổi đáng chú ý

* **https**: TLS sessions in Agent are reused (Fedor Indutny) [#2228](https://github.com/nodejs/io.js/pull/2228)

* **https**: Tái sử dụng lại TLS sessions trong Agent (Fedor Indutny) [#2228](https://github.com/nodejs/io.js/pull/2228)

* **src**: base64 decoding is now 50% faster (Ben Noordhuis) [#2193](https://github.com/nodejs/io.js/pull/2193)

* **src**: giải mã base64 nhanh hơn 50% (Ben Noordhuis) [#2193](https://github.com/nodejs/io.js/pull/2193)

* **npm**: Upgraded to v2.13.2, release notes can be found in <https://github.com/npm/npm/releases/tag/v2.13.2> (Kat Marchán) [#2241](https://github.com/nodejs/io.js/pull/2241).

* **npm**: Cập nhật lên v2.13.2, các ghi chú cho bản phát hành có thể tìm thấy tại <https://github.com/npm/npm/releases/tag/v2.13.2> (Kat Marchán) [#2241](https://github.com/nodejs/io.js/pull/2241).

### Known issues

### Các lỗi hiện tại

See https://github.com/nodejs/io.js/labels/confirmed-bug for complete and current list of known issues.

Xem đầy đủ các lỗi được biết đến hiện nay tại
https://github.com/nodejs/io.js/labels/confirmed-bug.

* Some problems with unreferenced timers running during `beforeExit` are still to be resolved. See [#1264](https://github.com/nodejs/io.js/issues/1264).
* Một vài vấn đề với unreferenced timers chạy trong `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).

* Surrogate pair in REPL can freeze terminal. [#690](https://github.com/nodejs/io.js/issues/690)
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)

* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/nodejs/io.js/issues/760).
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, xem [#760](https://github.com/iojs/io.js/issues/760).

* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion. [#894](https://github.com/nodejs/io.js/issues/894)
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)

* `url.resolve` may transfer the auth portion of the url when resolving between two full hosts, see [#1435](https://github.com/nodejs/io.js/issues/1435).
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Community Updates

### Cập nhật từ cộng đồng

* We need a V8 maintainer for our LTS build! Head on over [to GitHub](https://github.com/nodejs/LTS/issues/28) to see if the requirements match your capabilities.

* Chúng ta cần 1 người bào trì V8 cho bản build LTS! Truy cập [GitHub](https://github.com/nodejs/LTS/issues/28)
để xem để xem thông tin chi tiết nếu các yêu cầu phù hợp với khả năng của bạn.

* [Milo Mordaunt](https://twitter.com/bananaoomarang) has written about [extending IFTTT with Webtask.io running Node.js code](https://auth0.com/blog/2015/07/28/if-this-then-node-dot-js-extending-ifttt-with-webtask-dot-io/?utm_source=io.js+and+Node.js+News&utm_medium=article) over on [Auth0](https://auth0.com/blog).

* [Milo Mordaunt](https://twitter.com/bananaoomarang) đã viết 1 bài viết về việc mở rộng [IFTTT với Webtask.io chạy Node.js ](https://auth0.com/blog/2015/07/28/if-this-then-node-dot-js-extending-ifttt-with-webtask-dot-io/?utm_source=io.js+and+Node.js+News&utm_medium=article) trên [Auth0](https://auth0.com/blog).

* [Hemanth.HM](https://twitter.com/gnumanth), an author and contributor of more than 200 modules on npm, has written about [authoring Node modules](http://h3manth.com/new/blog/2015/authoring-node-modules/?utm_source=io.js+and+Node.js+News&utm_medium=article).

* [Hemanth.HM](https://twitter.com/gnumanth), tác giả và người đóng góp cho hơn 200 modules trên npm, đã viết 1 bài viết về [authoring Node modules](http://h3manth.com/new/blog/2015/authoring-node-modules/?utm_source=io.js+and+Node.js+News&utm_medium=article).

If you have spotted or written something about Node.js and io.js, do come over to our [Evangelism team repo](https://github.com/nodejs/evangelism) and suggest it on the [Issues page](https://github.com/nodejs/evangelism/issues), specifically the Weekly Updates issue.

Nếu bạn phát hiện hay viết 1 điều gì đó về Node.js và io.js. Hãy truy cập vào [Evangelism team repo](https://github.com/nodejs/evangelism) và gợi ý bài viết tại trang [Issues](https://github.com/nodejs/evangelism/issues),  gắn thẻ là Weekly Updates.

### Upcoming Events

### Sự kiện sắp diễn ra

* [BrazilJS Conf](http://braziljs.com.br/) tickets are on sale, August 21st - 22nd at Shopping Center BarraShoppingSul
* Vé [BrazilJS Conf](http://braziljs.com.br/) đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul

* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland

* [Node.js Italian Conference](http://nodejsconf.it/) tickets are on sale, October 10th at Desenzano - Brescia, Italy
* Vé [Node.js Italian Conference](http://nodejsconf.it/) đã được bán, diễn ra vào ngày 10 tháng 10 tại Desenzano - Brescia, Italy

* [JSConf CO](http://www.jsconf.co/), October 16th - 17th at Ruta N, Medellin
* [JSConf CO](http://www.jsconf.co/), diễn ra vào ngày 16 - 17 tháng 10 tại Ruta N, Medellin

Have an event about Node.js and io.js coming up? You can put your events here through the [Evangelism team repo](https://github.com/nodejs/evangelism) and announce it in the [Issues page](https://github.com/nodejs/evangelism/issues), specifically the Weekly Updates issue.

Có 1 sự kiện về Node.js và io.js sắp diễn ra? Bạn có thể đặt sự kiện của bạn tại đâu thông qua [Evangelism team repo](https://github.com/nodejs/evangelism) và thông báo tại trang [Issues](https://github.com/nodejs/evangelism/issues),  gắn thẻ là Weekly Updates.
