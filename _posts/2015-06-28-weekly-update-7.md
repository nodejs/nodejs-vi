---
layout: post
title: weekly update 2015-06-12
categories: [weekly]
tags: [weekly, draft]
description: weekly update 2015-06-12
---

# io.js 2.3 releases
# Phát hành io.js 2.3


This week we had one io.js release [v2.3.0](https://iojs.org/dist/v2.3.0/), complete changelog can be found [on GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).
Tuần này chúng ta có 1 bản phát hành io.js [v2.3.0](https://iojs.org/dist/v2.3.0/),
toàn bộ các thay đổi có thể tìm thấy [trên GitHub](https://github.com/nodejs/io.js/blob/master/CHANGELOG.md).


### Notable changes
### Những thay đổi đáng chú ý

* **libuv**: Upgraded to 1.6.0 and 1.6.1, see [full ChangeLog](https://github.com/libuv/libuv/blob/60e515d9e6f3d86c0eedad583805201f32ea3aed/ChangeLog#L1-L36) for details. (Saúl Ibarra Corretgé) [#1905](https://github.com/nodejs/io.js/pull/1905) [#1889](https://github.com/nodejs/io.js/pull/1889). Highlights include:
  - Fix TTY becoming blocked on OS X
  - Fix UDP send callbacks to not to be synchronous
  - Add `uv_os_homedir()` (exposed as `os.homedir()`, see below)

* **libuv**: Cập nhật lên 1.6.0 và 1.6.1, xem chi tiết tại [ ChangeLog](https://github.com/libuv/libuv/blob/60e515d9e6f3d86c0eedad583805201f32ea3aed/ChangeLog#L1-L36). (Saúl Ibarra Corretgé) [#1905](https://github.com/nodejs/io.js/pull/1905) [#1889](https://github.com/nodejs/io.js/pull/1889).
Điểm nổi bật bao gồm:
- Sửa TTY trở thành blocked trên OS X
- Fix UDP send callbacks to not to be synchronous
- Add `uv_os_homedir()` (exposed as `os.homedir()`, see below)


* **npm**: See full [release notes](https://github.com/npm/npm/releases/tag/v2.11.1) for details. (Kat Marchán) [#1899](https://github.com/nodejs/io.js/pull/1899). Highlight:
  - Use GIT_SSH_COMMAND (available as of Git 2.3)


* **npm**: Xem chi tiết bản [phát hành](https://github.com/npm/npm/releases/tag/v2.11.1). (Kat Marchán) [#1899](https://github.com/nodejs/io.js/pull/1899). Điểm nổi bật::
    - Sử dụng GIT_SSH_COMMAND (hiện có tại bản Git 2.3)


* **openssl**:
  - Upgrade to 1.0.2b and 1.0.2c, introduces DHE man-in-the-middle protection (Logjam) and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the [security advisory](https://www.openssl.org/news/secadv_20150611.txt) for full details. (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
  - Support [FIPS](https://en.wikipedia.org/wiki/Federal_Information_Processing_Standards) mode of OpenSSL, see [README](https://github.com/nodejs/io.js#building-iojs-with-fips-compliant-openssl) for instructions. (Fedor Indutny) [#1890](https://github.com/nodejs/io.js/pull/1890)

* **openssl**:
    - Cập nhật lên 1.0.2b và 1.0.2c, giới thiệu DHE man-in-the-middle protection (Logjam)
    và sửa malformed ECParameters gây lên vòng lặp vô hạn
    and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the [security advisory](https://www.openssl.org/news/secadv_20150611.txt) for full details. (Shigeki Ohtsu) [#1950](https://github.com/nodejs/io.js/pull/1950) [#1958](https://github.com/nodejs/io.js/pull/1958)
    - Support [FIPS](https://en.wikipedia.org/wiki/Federal_Information_Processing_Standards) mode of OpenSSL, see [README](https://github.com/nodejs/io.js#building-iojs-with-fips-compliant-openssl) for instructions. (Fedor Indutny) [#1890](https://github.com/nodejs/io.js/pull/1890)



* **os**: Add `os.homedir()` method. (Colin Ihrig) [#1791](https://github.com/nodejs/io.js/pull/1791)


* **os**: Thêm phương thức `os.homedir()`. (Colin Ihrig) [#1791](https://github.com/nodejs/io.js/pull/1791)



* **smalloc**: Deprecate whole module. (Vladimir Kurchatkin) [#1822](https://github.com/nodejs/io.js/pull/1822)

* **smalloc**: Phản đối toàn bộ module. (Vladimir Kurchatkin) [#1822](https://github.com/nodejs/io.js/pull/1822)



* Add new collaborators:

* Thêm cộng tác viên mới:


  - Alex Kocharin ([@rlidwka](https://github.com/rlidwka))
  - Christopher Monsanto ([@monsanto](https://github.com/monsanto))
  - Ali Ijaz Sheikh ([@ofrobots](https://github.com/ofrobots))
  - Oleg Elifantiev ([@Olegas](https://github.com/Olegas))
  - Domenic Denicola ([@domenic](https://github.com/domenic))
  - Rich Trott ([@Trott](https://github.com/Trott))

### Các lỗi hiện tại
### Known issues

See https://github.com/nodejs/io.js/labels/confirmed-bug for complete and current list of known issues.

Xem đầy đủ các lỗi được biết đến hiện nay tại https://github.com/nodejs/io.js/labels/confirmed-bug.

* Some problems with unreferenced timers running during `beforeExit` are still to be resolved. See [#1264](https://github.com/nodejs/io.js/issues/1264).
* Một vài vấn đề với unreferenced timers chạy trong  `beforeExit` vẫn đang được giải quyết. Xem tại [#1264](https://github.com/nodejs/io.js/issues/1264).

* Surrogate pair in REPL can freeze terminal [#690](https://github.com/nodejs/io.js/issues/690)
* Surrogate pair trong REPL có thể làm treo terminal [#690](https://github.com/iojs/io.js/issues/690)

* `process.send()` is not synchronous as the docs suggest, a regression introduced in 1.0.2, see [#760](https://github.com/nodejs/io.js/issues/760) and fix in [#774](https://github.com/nodejs/io.js/issues/774)
* `process.send()` không đồng bộ như trong tài liệu đề cập, đã được thông báo trong 1.0.2, Xem [#760](https://github.com/iojs/io.js/issues/760) để biết thông tin chi tiết và được sửa đổi trong [#774]
(https://github.com/iojs/io.js/issues/774)

* Calling `dns.setServers()` while a DNS query is in progress can cause the process to crash on a failed assertion [#894](https://github.com/nodejs/io.js/issues/894)
* Gọi `dns.setServers()`  khi 1 truy vấn DNS đang được sử lý trong progress có thể khiến process bị crash với 1 failed assertion [#894](https://github.com/iojs/io.js/issues/894)

* `url.resolve` may transfer the auth portion of the url when resolving between two full hosts, see [#1435](https://github.com/nodejs/io.js/issues/1435).
* `url.resolve` có thể chuyển phần auth của url khi sử dụng `require("url").resolve` giữa 2 full hosts, xem tại [#1435](https://github.com/iojs/io.js/issues/1435).

### Cập nhật từ cộng đồng
### Community Updates

* Openssl vulnerabilities are updated on io.js. **Resume:** *Upgrade to 1.0.2b and 1.0.2c, introduces DHE man-in-the-middle protection (Logjam) and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the security advisory for full details. (Shigeki Ohtsu) #1950 #1958*

* Lỗi hổng bảo mật Openssl đã được cập nhật trên io.js. **Tóm tắt:** *Upgrade to 1.0.2b and 1.0.2c, introduces DHE man-in-the-middle protection (Logjam) and fixes malformed ECParameters causing infinite loop (CVE-2015-1788). See the security advisory for full details. (Shigeki Ohtsu) #1950 #1958*


* io.js 2.3.0 os.homedir() [ponyfill](http://t.co/2XQV5XQblu)


* ["Should I use Node.js or io.js? And which version?"](https://strongloop.com/strongblog/should-i-use-node-js-or-io-js-and-which-version/) article by StrongLoop

* ["Tôi nên sử dụng Node.js hay io.js? Và version nào ?"](https://strongloop.com/strongblog/should-i-use-node-js-or-io-js-and-which-version/) bài viết bởi StrongLoop


* iojs now supports [`--use_strong`](https://t.co/4t1EaiiK27). Strong mode (part of Google v8 experiments) implements a stronger semantics.
* iojs đã hỗ trợ [`--use_strong`](https://t.co/4t1EaiiK27). Strong mode (là 1 phần trong các thử nghiệm của Google v8) triển khai 1 ngữ nghĩa mạnh. (Giúp code của bạn an toàn hơn, tránh các lỗi phổ biến, cải thiện hiệu xuất).


* ["Node.js and io.js Merge Under the Node Foundation"](http://www.infoq.com/news/2015/05/nodejs-iojs#.VX41fCR99Kc.twitter) by InfoQ.
* ["Node.js và io.js hợp nhất dưới tên Node Foundation"](http://www.infoq.com/news/2015/05/nodejs-iojs#.VX41fCR99Kc.twitter) bởi InfoQ.

### Sự kiện sắp diễn ra
### Upcoming Events

* [CascadiaJS](http://2015.cascadiajs.com/) tickets are on sale, July 8th - 10th at Washington State
* Vé [CascadiaJS](http://2015.cascadiajs.com/) đã được bán, diễn ra vào ngày 08 - 10 tháng 7 tại Washington State

* [BrazilJS Conf](http://braziljs.com.br/) tickets are on sale, August 21st - 22nd at Shopping Center BarraShoppingSul
* Vé [BrazilJS Conf](http://braziljs.com.br/)  đã được bán, diễn ra vào ngày 21 - 22 tháng 8 tại Shopping Center BarraShoppingSul

* [NodeConf EU](http://nodeconf.eu/) tickets are on sale, September 6th - 9th at Waterford, Ireland
* Vé [NodeConf EU](http://nodeconf.eu/) đã được bán, diễn ra vào ngày 06 - 09 tháng 9 tại Waterford, Ireland

* [JSConf CO](http://www.jsconf.co/), October 16th - 17th at Ruta N, Medellin
* [JSConf CO](http://www.jsconf.co/), diễn ra vào ngày 16 - 17 tháng 10 tại Ruta N, Medellin