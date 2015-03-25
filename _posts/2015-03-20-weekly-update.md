---
layout: post
title: weekly update 2015-03-20
categories: [weekly]
tags: [draft, weekly]
description: io.js 1.6 release
---

# Phát hành io.js 1.6

This week we had a two io.js releases [v1.6.1](https://iojs.org/dist/v1.6.1/) and  [v1.6.0](https://iojs.org/dist/v1.6.0/), complete changelog can be found [on GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).

Tuần này chúng ta có 2 bản phát hành của iojs [v1.6.1](https://iojs.org/dist/v1.6.1/) và  [v1.6.0](https://iojs.org/dist/v1.6.0/), bạn có thể tìm thông tin đầy đủ các thay đổi [tại GitHub](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md).

### Những thay đổi đáng chú ý

#### 1.6.1

* **path**: New type-checking on `path.resolve()` [#1153](https://github.com/iojs/io.js/pull/1153) uncovered some edge-cases being relied upon in the wild, most notably `path.dirname(undefined)`. Type-checking has been loosened for `path.dirname()`, `path.basename()`, and `path.extname()` (Colin Ihrig) [#1216](https://github.com/iojs/io.js/pull/1216).

* **path**: Thêm kiểm tra kiểu (type-checking) trên `path.resolve()` [#1153](https://github.com/iojs/io.js/pull/1153) do phát hiên 1 số trường hợp lỗi mà điển hình là `path.dirname(undefined)`. Kiểm tra kiểu (Type-checking) được lới lỏng cho `path.dirname()`, `path.basename()`, và `path.extname()` (Colin Ihrig) [#1216](https://github.com/iojs/io.js/pull/1216).


* **querystring**: Internal optimizations in `querystring.parse()` and `querystring.stringify()` [#847](https://github.com/iojs/io.js/pull/847) prevented `Number` literals from being properly converted via `querystring.escape()` [#1208](https://github.com/iojs/io.js/issues/1208), exposing a blind-spot in the test suite. The bug and the tests have now been fixed (Jeremiah Senkpiel) [#1213](https://github.com/iojs/io.js/pull/1213).

* **querystring**: Tối ưu hóa bên trong `querystring.parse()` và `querystring.stringify()` [#847](https://github.com/iojs/io.js/pull/847) để tránh ngăn chặn các ký tự kiểu `Number` được chuyển đổi thông qua `querystring.escape()`[#1208](https://github.com/iojs/io.js/issues/1208), phơi bày 1 điểm mù trong kiểm thử. Lỗi và kiểm thử đã được sửa bởi (Jeremiah Senkpiel) [#1213](https://github.com/iojs/io.js/pull/1213).

#### 1.6.0

* **node**: a new `-r` or `--require` command-line option can be used to pre-load modules at start-up (Ali Ijaz Sheikh) [#881](https://github.com/iojs/io.js/pull/881).

* **node**: Một option mới trên command-line là  `-r` hay `--require` có thể được sử dụng để load trước các modules ở thời điểm khởi chạy (Ali Ijaz Sheikh) [#881](https://github.com/iojs/io.js/pull/881).

* **querystring**: `parse()` and `stringify()` are now faster (Brian White) [#847](https://github.com/iojs/io.js/pull/847).

* **querystring**: `parse()` và `stringify()` được tối ưu nhanh hơn (Brian White) [#847](https://github.com/iojs/io.js/pull/847).

* **http**: the `http.ClientRequest#flush()` method has been deprecated and replaced with `http.ClientRequest#flushHeaders()` to match the same change now in Node.js v0.12 as per [joyent/node#9048](https://github.com/joyent/node/pull/9048) (Yosuke Furukawa) [#1156](https://github.com/iojs/io.js/pull/1156).

* **http**: Phương thức `http.ClientRequest#flush()` đã bị phản đối và thay thế bởi `http.ClientRequest#flushHeaders()` để phù hợp với sự thay đổi trên Node.js v0.12 [joyent/node#9048](https://github.com/joyent/node/pull/9048) (Yosuke Furukawa) [#1156](https://github.com/iojs/io.js/pull/1156).

* **net**: allow `server.listen()` to accept a `String` option for `port`, e.g. `{ port: "1234" }`, to match the same option being accepted in `net.connect()` as of [joyent/node#9268](https://github.com/joyent/node/pull/9268) (Ben Noordhuis) [#1116](https://github.com/iojs/io.js/pull/1116).

* **net**: cho phép `server.listen()` chấp nhận 1 `String` cho `port`, e.g. `{ port: "1234" }`, để phù hợp với tham số tương tự đã được chấp nhận trong `net.connect()` như [joyent/node#9268](https://github.com/joyent/node/pull/9268) (Ben Noordhuis) [#1116](https://github.com/iojs/io.js/pull/1116).

* **tls**: further work on the reported memory leak although there appears to be a minor leak remaining for the use-case in question, track progress at [#1075](https://github.com/iojs/io.js/issues/1075).

* **tls**: tiếp tục báo cáo về memory leak thông qua sự xuất hiện các leak nhỏ trong các trường hợp sử dụng, theo dõi tiến độ tại [#1075](https://github.com/iojs/io.js/issues/1075).

* **v8**: backport a fix for an integer overflow when `--max_old_space_size` values above `4096` are used (Ben Noordhuis) [#1166](https://github.com/iojs/io.js/pull/1166).

* **v8**: sửa chữa tràn 1 số integer khi giá trị `--max_old_space_size` trên `4096` được sử dụng (Ben Noordhuis) [#1166](https://github.com/iojs/io.js/pull/1166).

* **platforms**: the io.js CI system now reports passes on **FreeBSD** and **SmartOS** (_Solaris_).

* **platforms**: Hệ thống io.js Travis CI thông báo đã vượt qua  trên **FreeBSD** và **SmartOS** (_Solaris_).

* **npm**: cập nhật npm lên 2.7.1. Xem chi tiết tại [npm CHANGELOG.md](https://github.com/npm/npm/blob/master/CHANGELOG.md#v271-2015-03-05) .

### Các lỗi hiện tại

* Possible remaining TLS-related memory leak(s), details at [#1075](https://github.com/iojs/io.js/issues/1075).

* Các vấn đề memory leak còn lại liên quan đến TLS, chi tiết tại [#1075](https://github.com/iojs/io.js/issues/1075).

* Surrogate pair in REPL can freeze terminal [#690](https://github.com/iojs/io.js/issues/690)

* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)

* Not possible to build io.js as a static library [#686](https://github.com/iojs/io.js/issues/686)

* Không thể xây dựng io.js như là 1 static library [#686](https://github.com/iojs/io.js/issues/686)

* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) and fix in [#774](https://github.com/iojs/io.js/issues/774)

* `process.send()` là không đồng bộ như trong tài liệu đề cập, a regression introduced in 1.0.2, see [#760](https://github.com/iojs/io.js/issues/760) và được sửa trong [#774](https://github.com/iojs/io.js/issues/774)

* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion [#894](https://github.com/iojs/io.js/issues/894)

* Gọi `dns.setServers()` khi 1 truy vấn DNS  đang được sử lý trong progress có thể khiến process bị crash trên 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)

# Cập nhật từ cộng đồng

* browserify supports io.js, you can check the announcement [here](https://twitter.com/yosuke_furukawa/status/577150547850969088)
* browserify hỗ trợ io.js, bạn có thể xem thông báo ở [đây](https://twitter.com/yosuke_furukawa/status/577150547850969088)

* express.js added [support](https://github.com/strongloop/express/commit/165660811aa9ba5f3733a7b033894f3d9a9c5e60) to io.js

* express.js [hỗ trợ](https://github.com/strongloop/express/commit/165660811aa9ba5f3733a7b033894f3d9a9c5e60) thêm io.js

* Over the last two weeks we got access to hardware from Joyent and upstreamed a patch to V8 so we got io.js building. After that we worked on passing tests for both [SmartOS](https://github.com/iojs/build/pull/64) and [FreeBSD](https://github.com/iojs/io.js/pull/1167) which as of two days ago now pass, this was thanks to the amazing work of the build team and [Johan Bergström](https://github.com/jbergstroem)

* Trong 2 tuần qua chúng ta đã truy cập vào phần cứng từ Joyent và cập nhật 1 bản phá cho V8 nên chúng ta đã có 1 io.js building. Sau đó là việc vượt qua các bài test trên [SmartOS](https://github.com/iojs/build/pull/64) và [FreeBSD](https://github.com/iojs/io.js/pull/1167) 2 ngày trước , cảm ơn sự đóng góp tuyệt vời của build team và [Johan Bergström](https://github.com/jbergstroem)

* [Petka Antonov](https://github.com/petkaantonov) is proposing a workers implementation in io.js under an experimental flag, you can join the discussion [here](https://github.com/iojs/io.js/pull/1159)

* [Petka Antonov](https://github.com/petkaantonov) đã đề xuất triển khai workers trên io.js dưới --experimental-workers flag, bạn có thể tham gia thảo luận tại đây [here](https://github.com/iojs/io.js/pull/1159)

* io.js [upgraded](https://github.com/iojs/io.js/pull/1206) openssl to `1.0.1m`

* io.js [nâng cấp](https://github.com/iojs/io.js/pull/1206) openssl lên `1.0.1m`

# Sự kiện sắp diễn ra

* [NodeConf](http://nodeconf.com/) tickets are on sale, June 8th and 9th at Oakland, CA and NodeConf Adventure for June 11th - 14th at Walker Creek Ranch, CA

* Vé [NodeConf](http://nodeconf.com/) đã được bán, diễn ra vào ngày 08-09 tháng 6 tại Oakland, CA và NodeConf Adventure vào ngày June 11 - 14 tháng 6 tại Walker Creek Ranch, CA

* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State

* Vé [CascadiaJS](http://2015.cascadiajs.com/) đã được bán, diễn ra vào ngày 08 - 10 tháng 7 tại Washington State

* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland
