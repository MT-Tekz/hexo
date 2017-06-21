# Hexo

Dưới đây là bài hướng dẫn sử dụng Hexo trên windows. Tài liệu sử dụng có thể tìm thấy ở trên trang chính của hexo [https://hexo.io/](https://hexo.io/). Bài viết này là một bài tóm tắt cách sử dụng ban đầu của Hexo viết lại bằng Tiếng Việt.

## Sử dụng nhanh

### Yêu cầu

Cài đặt Hexo khá dễ dàng. Tuy nhiên, bạn cần phải cài đặt một vài thứ khác:

* [Node.js](https://nodejs.org/)
* [Git](https://git-scm.com/)

Nếu máy tính của bạn đã có những ứng dụng trên, xin chúc mừng! Bạn chỉ cần cài đặt Hexo với npm như sau:

```
npm install -g hexo-cli
```

# Cách dùng hexo

## Khởi tạo dự án Blog

Gõ lệnh sau ở Command Prompt

```
hexo init blog
cd blog
npm install
hexo server
```

Sau khi hoàn tất, bạn có thể mở [http://localhost:4000](http://localhost:4000) để xem kết quả

# Sử dụng theme

Bạn có thể xem các themes public hiện có của hexo trên trang [https://hexo.io/themes/](https://hexo.io/themes/). Ở phần này mình sẽ cài đặt theme [Corporate](https://github.com/ptsteadman/hexo-theme-corporate) làm mẫu. Trình tự các bước cài đặt có thể xem ở trang dự án của theme. Tóm tắt như bên dưới:

## Cài đặt theme Corporate

``` bash
git clone https://github.com/ptsteadman/hexo-theme-corporate.git themes/corporate
```

## Kích hoạt theme Corporate

1. **Thêm trang mẫu ví dụ.** 

	Sao chép tất cả nội dung của thư mục `themes/corporate/_source` đến `source`.
	Nội dung này bao gồm một sample landing page và contact, project, và
	about pages.

	```bash
	cp -r themes/corporate/_source/* source
	```

  Nếu không thực thi được lên trên, vui lòng sao chép bằng thao tác thông thường, bằng cách chọn hết tất cả nội dung sao chép và dán vào thư mục `source` của dự án mà bạn đã tạo.

2. **Kích hoạt theme.** 
	Chỉnh sửa nội dung tệp `_config.yml` tại thư mục gốc của dự án để `theme` đặt lại là `corporate`. 

	```yml
	# Extensions
	## Plugins: http://hexo.io/plugins/
	## Themes: http://hexo.io/themes/
	theme: corporate # thay đổi ở đây

	```

	Cuối cùng, chạy lệnh `npm install` rồi đến lệnh `hexo server` để kiểm tra trang của bạn.

3. **Không bắt buộc: Kích hoạt landing page tự tạo**

  Để sử dụng landing page tùy chỉnh thay vì sử dụng trang mặc định, hãy loại bỏ
  Dòng có chứa hexo-generator-index từ file package.json trong thư mục gốc của dự án.
  Sau đó, chỉnh sửa `source/index.ejs`

### Cập nhật theme

Cập nhật theme bằng cách chạy lệnh sau

``` bash
cd themes/corporate
git pull
```

## Cấu hình theme

Sửa nội dung file `themes/corporate/_config.yml` để tùy chỉnh cấu hình cho theme. Ví dụ như bên dưới

``` yml
# Header Menu
menu:
  Home: /
  Projects: /projects/
  Blog: /archives/ # can set archive-dir in root config to custom value
  Contact: /contact/
  About: /about/
   
rss: /atom.xml

# Content
excerpt_link: Read More
fancybox: true # whether or not to load the fancybox library

# Integrations
disqus_shortname: 
google_analytics:
swiftype_install_key: 

# Social
social:
  github: https://github.com/ptsteadman
  twitter: https://twitter.com/ptsteadman
  facebook: https://www.facebook.com/ptsteadman
  rss: atom.xml
  linkedin: https://linkedin.com/in/ptsteadman
  stackoverflow: http://stackoverflow.com/users/2480493/patrick-steadman

# Miscellaneous
color_scheme: red   # options: blue, gray, green, orange, red, turquoise
favicon: /favicon.ico # path from root of hexo site
twitter_widget_id: "678830341331820544" # as a string, from https://twitter.com/settings/widgets
twitter_username: computerlab_ # twitter username without the @
default_author: Anonymous

about: Computer Lab is a software development and marketing company based in Brooklyn, New York. <br><br> Computer Lab was founded in 2015, and is focused on so on and so forth.
phone: 716-472-4484
email: ptsteadman@gmail.com
address_1: 140 Metropolitan Avenue
address_2: 5th Floor
address_3: Brooklyn, NY 11249
skype: ptsteadman
lat: 40.715911 
long: -73.962147
```


## Tính năng

### Trang tùy chỉnh (custom page)

Trang Contact, Projects, và About được bao gồm sẵn trong thư mục `_source`. Khi sao chép vào thư mục `source` của blog, chúng có thể được tùy chỉnh để thay đổi nội dung. Chỉnh sửa header menu của themes tại `_config.yml` để tạo đường dẫn đến những trang này.

Bạn có thể dung [metronic CSS components](http://keenthemes.com/metronic-theme/) để xây dựng những trang này.

``` yml
# Header Menu
menu:
  Home: /
  Projects: /projects/
  Blog: /archives/ # can set archive-dir in root config to custom value
  Contact: /contact/
  About: /about/
```

Xem thêm các tính năng khác của theme tại [https://github.com/ptsteadman/hexo-theme-corporate/blob/master/README.md#features](https://github.com/ptsteadman/hexo-theme-corporate/blob/master/README.md#features)

# Cách tạo bài đăng (post) mới

Bạn có thể tọa bài viết mới bằng lệnh sau:

```
hexo new "Tiêu đề post mới"
```

Sau khi chạy lệnh trên, một tệp mới sẽ được tạo ở thư mục `source/_posts` với tên là `Tieu-de-post-moi.md`.

Bạn có chỉnh sửa nội dung bài viết ở trong file đó. Mở file lên, bạn sẽ thấy nội dung tương tự như bên dưới

```
---
title: Tiêu đề post mới
date: 2017-06-21 22:43:18
tags:
---

Thêm nội dung của bạn cần viết đây
```

File trên là file markdown, nếu không biết markdown là gì thì có thể google để biết thêm chi tiết. Tóm tắt lại thì markdown là text file có cú pháp định dạng và có thể được chuyển đổi sang định dạng HTML.

Sau khi chỉnh sửa nội dung file xong, gõ lệnh `hexo generate` sau đó gõ lệnh `hexo server` để kiểm tra kết quả.

## Diễn giải các lệnh

```
hexo init <tên thư mục>   # khởi tạo một dự án mới
cd <tên thư mục>          # di chuyển đến thư mục
npm install               # cài đặt các yêu cầu trong file package.json
hexo generate             # Tạo file tĩnh của dự án, các file này được tạo ở thư mục public
hexo server               # chạy local server, để tắt quá trình chạy bấm tổ hợp phím Ctrl+C
...
```

## Deployment

Phần này sẽ viết hướng dẫn sau. Tạm thời sau khi tạo file tĩnh xong, bạn có thể copy nội dung trong thư mục `public` để lên host của bạn để xem kết quả. 

**Mẹo:** nén thư mục public trước khi upload lên server để nhanh hơn.

[https://hexo.io/docs/deployment.html](https://hexo.io/docs/deployment.html)
