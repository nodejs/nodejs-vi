---
layout: post
title: Cài đặt nvm và iojs
categories: [tutorial]
tags: [tutorial, publish]
description: Cài đặt nvm và iojs
---

## Cài đặt NVM

Như đã được giải thích trong file Readme từ mã nguồn NVM => [https://github.com/creationix/nvm](https://github.com/creationix/nvm).Bạn sẽ cài đặt NVM với một trong hai cách dưới đây:

* dùng cURL:

        curl https://raw.githubusercontent.com/creationix/nvm/v0.24.1/install.sh | bash

* dùng Wget:

        wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.24.1/install.sh | bash

Nó sẽ tải về tất cả các tập tin vào trong một thư mục *~ / .nvm* vừa tạo.
Sau đó:

    source ~/.bashrc
Bây giờ bạn sẽ có thể sử dụng các NPM CLI.Kiểm tra lại kết quả bằng cách gõ

    nvm --version

---

## Sử dụng NVM

Sau khi hoàn thành việc cài đặt nvm, bạn có thể cài đặt và bắt đầu sử dụng các version khác nhau của Node.js và io.js bằng cách thực hiện các lệnh khác nhau.
Để liệt kê tất cả các lệnh của nvm dùng lệnh:

    nvm help

---

## Cài đặt iojs với nvm

Đầu tiên, bạn dùng lệnh

    nvm ls-remote

để liệt kê tất cả các version bạn có thể cài đặt.
Sau đó,

* Để cài đặt version iojs mà bạn mong muốn:

        nvm install iojs-v1.x.x

* Để cài đặt nhanh iojs: Nó sẽ tự động cài đặt cho bạn version mới nhất của iojs.

        nvm install iojs

Bạn có thể dùng lệnh

    nvm ls

để liệt kê các version iojs và Node.js mà bạn đã cài đặt.

---

## Hello World!

Tạo mới một file example.js với code dưới đây:

    console.log("Hello World");

Sau đó save file và trong terminal chạy nó với dòng lệnh dưới đây:

    iojs example.js

Và, bạn sẽ nhận được 'Hello World' xuất hiện trong terminal của bạn.
