```markdown
# 🗂 Danh Sách Kiểm Tra Front‑End

Danh Sách Kiểm Tra Front‑End là danh sách đầy đủ tất cả các hạng mục bạn cần có / cần kiểm thử trước khi đưa website / trang HTML của bạn lên môi trường production.

**Các danh sách khác:**

- [🎮 Danh Sách Kiểm Tra Hiệu Năng Front‑End](https://github.com/thedaviddias/Front-End-Performance-Checklist#---------front-end-performance-checklist-)
- [💎 Danh Sách Kiểm Tra Thiết Kế Front‑End](https://github.com/thedaviddias/Front-End-Design-Checklist#front-end-design-checklist)

> [!TIP]
> ⭐️ Các mẫu UX thân thiện với lập trình viên mà bạn hằng mong ước. 👉 [UX Patterns for Devs](https://uxpatterns.dev/en) ⭐️

## 📚 Mục Lục

- [Cách sử dụng](#cach-su-dung)
- [Head](#head)
- [HTML](#html)
- [Webfonts](#webfonts)
- [CSS](#css)
- [JavaScript](#javascript)
- [Khả năng truy cập](#kha-nang-truy-cap)

## Cách sử dụng?

<!-- prettier-ignore-start -->
> [!IMPORTANT]
> **Tuyên bố từ chối trách nhiệm:** Danh sách này dựa trên nhiều năm kinh nghiệm của các lập trình viên Front‑End, với các bổ sung từ những danh sách nguồn mở khác.
<!-- prettier-ignore-end -->

Tất cả các mục trong **Danh Sách Kiểm Tra Front‑End** đều bắt buộc đối với đa số dự án, nhưng một số hạng mục có thể bỏ qua hoặc không thiết yếu (ví dụ một ứng dụng web quản trị có thể không cần RSS feed). Chúng tôi sử dụng 3 mức linh hoạt:

- ![Low][low_img] cho biết hạng mục được khuyến nghị nhưng có thể bỏ qua trong một số tình huống.
- ![Medium][medium_img] cho biết hạng mục rất được khuyến nghị nhưng có thể bỏ qua trong các trường hợp cực kỳ đặc biệt. Tuy nhiên, bỏ qua có thể ảnh hưởng xấu đến hiệu năng hoặc SEO.
- ![High][high_img] cho biết hạng mục không thể bỏ qua dưới bất kỳ hoàn cảnh nào. Loại bỏ có thể gây lỗi trang hoặc vấn đề về khả năng truy cập và SEO. Việc kiểm thử nên ưu tiên các hạng mục này trước.

Một số tài nguyên có biểu tượng cảm xúc giúp bạn hiểu loại nội dung / trợ giúp có thể tìm thấy trong danh sách:

- 📖: tài liệu hoặc bài viết
- 🛠: công cụ trực tuyến / công cụ kiểm thử
- 📹: nội dung media hoặc video

## Head

<!-- prettier-ignore-start -->
> [!NOTE]
> Bạn có thể tìm [danh sách mọi thứ](https://github.com/joshbuchea/HEAD) có thể xuất hiện trong `<head>` của tài liệu HTML.
<!-- prettier-ignore-end -->

### Thẻ Meta

- [ ] **Doctype:** ![High][high_img] Doctype là HTML5 và nằm trên cùng của mọi trang HTML.

```html
<!doctype html><!-- HTML5 -->
```

- 📖 [Xác định bộ mã ký tự – HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

_Hai thẻ meta tiếp theo (Charset và Viewport) cần đặt đầu tiên trong head._

- [ ] **Charset:** ![High][high_img] Charset (UTF‑8) được khai báo chính xác.

```html
<!-- Thiết lập bộ mã ký tự cho tài liệu -->
<meta charset="utf-8">
```

- [ ] **Viewport:** ![High][high_img] Viewport được khai báo chính xác.

```html
<!-- Viewport cho thiết kế web đáp ứng -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

- [ ] **Title:** ![High][high_img] Tiêu đề được dùng trên tất cả trang (SEO: Google tính bề rộng pixel của tiêu đề và cắt ở khoảng 472–482 px, giới hạn ~55 ký tự).

```html
<!-- Tiêu đề tài liệu -->
<title>Tên trang dưới 55 ký tự</title>
```

- 📖 [Title – HTML – MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
- 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

- [ ] **Description:** ![High][high_img] Thẻ meta description được cung cấp, duy nhất và không quá 150 ký tự.

```html
<!-- Meta Description -->
<meta name="description" content="Mô tả trang dưới 150 ký tự">
```

- 📖 [Meta Description – HTML – MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

- [ ] **Favicons:** ![Medium][medium_img] Mỗi favicon được tạo và hiển thị đúng. Nếu chỉ có `favicon.ico`, đặt ở gốc site. Thường không cần markup nhưng vẫn nên liên kết như ví dụ dưới. **PNG được khuyến nghị** hơn `.ico` (kích thước 32x32px).

```html
<!-- Favicon chuẩn -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Định dạng favicon khuyến nghị -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
<!-- Favicon hiện đại (không khuyến nghị cho trình duyệt cũ) -->
<link rel="icon" type="image/svg+xml" href="https://example.com/favicon.svg">
```

- 🛠 [Favicon Generator](https://www.favicon-generator.org/)
- 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
- 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
- 📖 [Favicons, Touch Icons, Tile Icons, v.v. Bạn cần gì? – CSS Tricks](https://css-tricks.com/favicon-quiz/)
- 📖 [PNG favicons – caniuse](https://caniuse.com/link-icon-png)

- [ ] **Apple Web App Meta:** ![Low][low_img] Thẻ meta dành cho Apple có mặt.

```html
<!-- Apple Touch Icon (ít nhất 200x200px) -->
<link rel="apple-touch-icon" href="/custom-icon.png">

<!-- Chạy ứng dụng web ở chế độ toàn màn hình -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- Kiểu thanh trạng thái -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">
```

- 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)
- 📖 [Supported Meta Tags](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

- [ ] **Windows Tiles:** ![Low][low_img] Windows tiles có mặt và được liên kết.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml">
```

Đoạn markup XML tối thiểu cho `browserconfig.xml`:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

- 📖 [Browser configuration schema reference](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/dn320426(v=vs.85))

- [ ] **Canonical:** ![Medium][medium_img] Sử dụng `rel="canonical"` để tránh nội dung trùng lặp.

```html
<!-- Tránh vấn đề nội dung trùng lặp -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-read.html">
```

- 📖 [Sử dụng canonical URLs – Google Support](https://support.google.com/webmasters/answer/139066?hl=vi)
- 📖 [5 sai lầm phổ biến với rel=canonical – Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### Thẻ HTML

- [ ] **Thuộc tính ngôn ngữ:** ![High][high_img] Thuộc tính `lang` của website được chỉ định phù hợp với ngôn ngữ trang hiện tại.

```html
<html lang="en"></html>
```

- [ ] **Thuộc tính hướng:** ![Medium][medium_img] Hướng đọc được chỉ định trên thẻ html (có thể dùng trên thẻ HTML khác).

```html
<html dir="rtl">
  <!-- ... -->
</html>
```

- 📖 [dir – HTML – MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

- [ ] **Ngôn ngữ thay thế:** ![Low][low_img] Thẻ ngôn ngữ thay thế được chỉ định phù hợp.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

- [ ] **x-default:** ![Low][low_img] Thẻ ngôn ngữ cho trang đích quốc tế.

```html
<link rel="alternate" href="https://example.com/" hreflang="x-default" />
```

- 📖 [x-default – Google](https://webmasters.googleblog.com/2013/04/x-default-hreflang-for-international-pages.html)

- [ ] **Conditional comments:** ![Low][low_img] Conditional comments cho IE nếu cần.

- 📖 [About conditional comments (Internet Explorer) – MSDN](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

- [ ] **RSS feed:** ![Low][low_img] Nếu dự án là blog hoặc có bài viết, liên kết RSS được cung cấp.

- [ ] **CSS Critical:** ![Medium][medium_img] CSS quan trọng ("above the fold") chứa toàn bộ CSS cần để render phần nhìn thấy của trang. Được nhúng trước CSS chính và giữa `<style></style>` dưới dạng một dòng (đã nén).

- 🛠 [Critical by Addy Osmani](https://github.com/addyosmani/critical) tự động hóa việc này.

- [ ] **Thứ tự CSS:** ![High][high_img] Tất cả file CSS được tải trước bất kỳ file JavaScript nào trong `<head>` (trừ khi JS được load async ở đầu trang).

### Social meta

Tạo và xem trước tự động thẻ social meta bằng [Meta Tags](https://metatags.io/)

**_Facebook OG_** và **_Twitter Cards_** được khuyến nghị cao. Các thẻ mạng xã hội khác xem xét khi bạn nhắm đến nền tảng đó.

- [ ] **Facebook Open Graph:** ![Low][low_img] Tất cả thẻ OG được kiểm thử, không thiếu hoặc sai. Ảnh ít nhất 600 × 315 px, khuyến nghị 1200 × 630 px.

> [!NOTE]
> Sử dụng `og:image:width` và `og:image:height` để khai báo kích thước ảnh giúp crawler render ngay mà không tải bất đồng bộ.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Tiêu đề nội dung">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Mô tả tại đây" />
<meta property="og:site_name" content="Tên site">
<meta property="og:locale" content="en_US">
<!-- Thẻ tiếp theo tuỳ chọn nhưng khuyến nghị -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

- 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
- 📖 [Best Practices – Sharing](https://developers.facebook.com/docs/sharing/best-practices/)
- 🛠 Kiểm thử với [Facebook OG debugger](https://developers.facebook.com/tools/debug/)

- [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Tiêu đề nội dung">
<meta name="twitter:description" content="Mô tả nội dung dưới 200 ký tự">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

- 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
- 🛠 Kiểm thử với [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ quay lại đầu](#-muc-luc)**

## HTML

### Thực hành tốt

- [ ] **Phần tử ngữ nghĩa HTML5:** ![High][high_img] Các phần tử ngữ nghĩa HTML5 được sử dụng đúng (header, section, footer, main...).

- 📖 [HTML Reference](http://htmlreference.io/)

- [ ] **Trang lỗi:** ![High][high_img] Trang lỗi 404 và 5xx tồn tại. Trang 5xx cần CSS tích hợp (không gọi ngoài server hiện tại).

- [ ] **Noopener:** ![Medium][medium_img] Nếu dùng liên kết ngoài với `target="_blank"`, thêm `rel="noopener"` để tránh tab nabbing. Nếu cần hỗ trợ Firefox cũ, dùng `rel="noopener noreferrer"`.

- 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

- [ ] **Dọn comment:** ![Low][low_img] Mã không cần thiết bị xoá trước khi đưa lên production.

### Kiểm thử HTML

- [ ] **Tuân thủ W3C:** ![High][high_img] Tất cả trang được kiểm thử bằng trình xác thực W3C.

- 🛠 [W3C validator](https://validator.w3.org/)

- [ ] **HTML Lint:** ![High][high_img] Sử dụng công cụ phân tích lỗi HTML.

- 🛠 [Dirty markup](https://www.10bestdesign.com/dirtymarkup/)
- 🛠 [webhint](https://webhint.io/)

- [ ] **Trình kiểm tra liên kết:** ![High][high_img] Không có liên kết hỏng, kiểm tra lỗi 404.

- 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

- [ ] **Kiểm thử adblocker:** ![Medium][medium_img] Website hiển thị nội dung đúng khi bật adblocker (có thể hiển thị thông báo).

- 📖 [Sử dụng AdBlocking trong môi trường Dev](https://andreicioara.com/use-adblocking-in-your-dev-environment-48db500d9b86)

**[⬆ quay lại đầu](#-muc-luc)**

---

## Webfonts

> [!NOTE]
> Sử dụng web font có thể gây Flash Of Unstyled Text / Flash Of Invisible Text – cân nhắc font fallback và/hoặc web font loader để kiểm soát.

- 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

- [ ] **Định dạng Webfont:** ![High][high_img] WOFF, WOFF2 và TTF được hỗ trợ bởi các trình duyệt hiện đại.

- 📖 [WOFF – Caniuse](https://caniuse.com/woff)
- 📖 [WOFF2 – Caniuse](https://caniuse.com/woff2)
- 📖 [TTF/OTF – Caniuse](https://caniuse.com/ttf)
- 📖 [Using @font-face – CSS‑Tricks](https://css-tricks.com/snippets/css/using-font-face/)

- [ ] **Kích thước Webfont:** ![High][high_img] Tổng kích thước webfont không vượt quá 2 MB (bao gồm mọi biến thể).

- [ ] **Webfont loader:** ![Low][low_img] Kiểm soát hành vi tải với webfont loader.

- 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ quay lại đầu](#-muc-luc)**

---

## CSS

> **Ghi chú:** Tham khảo [CSS guidelines](https://cssguidelin.es/) và [Sass Guidelines](https://sass-guidelin.es/) được nhiều lập trình viên Front‑End theo. Nếu phân vân thuộc tính CSS, xem [CSS Reference](http://cssreference.io/). Cũng có [Code Guide](http://codeguide.co/) ngắn gọn cho tính nhất quán.

- [ ] **Thiết kế web đáp ứng:** ![High][high_img] Website sử dụng responsive.
- [ ] **CSS in Print:** ![Medium][medium_img] Stylesheet in cho máy in được cung cấp và đúng trên mỗi trang.
- [ ] **Tiền xử lý:** ![Low][low_img] Dự án dùng CSS preprocessor (vd. [Sass](http://sass-lang.com/), [Less](http://lesscss.org/), [Stylus](http://stylus-lang.com/)).
- [ ] **ID duy nhất:** ![High][high_img] Nếu dùng ID, chúng là duy nhất trên trang.
- [ ] **Reset CSS:** ![High][high_img] Sử dụng reset (reset, normalize hoặc reboot) và cập nhật.

- 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
- 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
- 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

- [ ] **Tiền tố JS:** ![Low][low_img] Tất cả class (hoặc id) dùng trong JS bắt đầu bằng **js-** và không được style trong CSS.

```html
<div id="js-slider" class="my-slider">
  <!-- Hoặc -->
  <div id="id-used-by-cms" class="js-slider my-slider"></div>
</div>
```

- [ ] **CSS nhúng/inline:** ![High][high_img] Tránh nhúng CSS trong `<style>` hoặc inline trừ lý do chính đáng (vd. hình nền slider, CSS quan trọng).
- [ ] **Tiền tố vendor:** ![High][high_img] Tiền tố vendor được dùng và sinh ra theo hỗ trợ trình duyệt.

- 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Hiệu năng

- [ ] **Gộp file:** ![High][high_img] File CSS được gộp thành một _(Không áp dụng HTTP/2)_.
- [ ] **Nén:** ![High][high_img] Tất cả CSS được nén.
- [ ] **Không chặn:** ![Medium][medium_img] File CSS cần non‑blocking để DOM không bị trì hoãn.

- 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
- 📖 [Ví dụ preload CSS bằng loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **CSS không dùng:** ![Low][low_img] Xoá CSS không sử dụng.

- 🛠 [UnCSS Online](https://uncss-online.com/)
- 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
- 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
- 🛠 [Chrome DevTools Coverage](https://developer.chrome.com/docs/devtools/coverage/)

### Kiểm thử CSS

- [ ] **Stylelint:** ![High][high_img] Không lỗi stylelint trong CSS/SCSS.

- 🛠 [stylelint](https://stylelint.io/)
- 📖 [Sass guidelines](https://sass-guidelin.es/)

- [ ] **Thiết kế web đáp ứng:** ![High][high_img] Tất cả trang được test ở các breakpoint: 320px, 768px, 1024px (có thể khác theo analytics).

  - 🛠 [Am I Responsive?](http://ami.responsivedesign.is/)
  - 🛠 [Mobile Friendly Test](https://search.google.com/test/mobile-friendly)
  - 🛠 [Responsive Design Checker](https://responsivedesignchecker.com/)

- [ ] **Trình xác thực CSS:** ![Medium][medium_img] CSS được kiểm thử và sửa lỗi.

- 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

- [ ] **Trình duyệt desktop:** ![High][high_img] Kiểm thử trên mọi trình duyệt desktop hiện tại (Safari, Firefox, Chrome, IE, EDGE...).
- [ ] **Trình duyệt mobile:** ![High][high_img] Kiểm thử trên mọi trình duyệt mobile hiện tại (Native, Chrome, Safari...).
- [ ] **Hệ điều hành:** ![High][high_img] Kiểm thử trên mọi OS hiện tại (Windows, Android, iOS, Mac...).

- [ ] **Độ chính xác thiết kế:** ![Low][low_img] Tuỳ dự án, có thể cần sát với thiết kế. Dùng công cụ so sánh.

> [Pixel Perfect – Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

- [ ] **Hướng đọc:** ![High][high_img] Kiểm thử cho ngôn ngữ LTR và RTL nếu cần hỗ trợ.

- 📖 [Building RTL‑Aware Web Apps & Websites: Phần 1](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
- 📖 [Phần 2](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ quay lại đầu](#-muc-luc)**

---

## Hình ảnh

> **Ghi chú:** Để hiểu đầy đủ tối ưu hình ảnh, xem ebook miễn phí **[Essential Image Optimization](https://images.guide/)** của Addy Osmani.

### Thực hành tốt

- [ ] **Tối ưu:** ![High][high_img] Tất cả hình ảnh được tối ưu cho trình duyệt. Có thể dùng WebP cho trang quan trọng.

- 🛠 [Imagemin](https://github.com/imagemin/imagemin)
- 🛠 [ImageOptim](https://imageoptim.com/)
- 🛠 [KeyCDN Image Processing](https://www.keycdn.com/support/image-processing)
- 🛠 [TinyPNG](https://tinypng.com/)
- 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/)
- 🛠 [SVGO](https://github.com/svg/svgo)
- 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/)

- [ ] **Picture/Srcset:** ![Medium][medium_img] Sử dụng picture/srcset để cung cấp ảnh phù hợp viewport.

- 📖 [Xây dựng ảnh đáp ứng với srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

- [ ] **Retina:** ![Low][low_img] Cung cấp ảnh 2x hoặc 3x cho màn hình retina.
- [ ] **Sprite:** ![Medium][medium_img] Ảnh nhỏ được gộp sprite (biểu tượng có thể dùng SVG sprite).
- [ ] **Width và Height:** ![High][high_img] Đặt thuộc tính `width` và `height` trên `<img>` nếu biết kích thước cuối cùng.
- [ ] **Văn bản thay thế:** ![High][high_img] Mọi `<img>` có văn bản thay thế mô tả hình.

- 📖 [Alt-texts: Hướng dẫn toàn diện](https://axesslab.com/alt-texts/)

- [ ] **Lazy loading:** ![Medium][medium_img] Ảnh được lazyload (luôn có noscript fallback).
  - 🛠 [Native lazy loading polyfill](https://github.com/mfranzke/loading-attribute-polyfill/)

**[⬆ quay lại đầu](#-muc-luc)**

---

## JavaScript

### Thực hành tốt

- [ ] **JavaScript inline:** ![High][high_img] Không có JS inline.
- [ ] **Gộp file:** ![High][high_img] File JS được gộp.
- [ ] **Nén:** ![High][high_img] File JS được nén (thêm hậu tố `.min`).

- 📖 [Minify Resources](https://developers.google.com/speed/docs/insights/MinifyResources)

- [ ] **Bảo mật JS:** ![High][high_img]

- 📖 [Hướng dẫn phát triển ứng dụng bảo mật với JS](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

- [ ] **Thẻ `noscript`:** ![Medium][medium_img] Sử dụng `<noscript>` nếu script không được hỗ trợ hoặc bị tắt.

```html
<noscript>Bạn cần bật JavaScript để chạy ứng dụng này.</noscript>
```

- [ ] **Không chặn:** ![Medium][medium_img] File JS được tải async (`async`) hoặc hoãn (`defer`).

- 📖 [Remove Render‑Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

- [ ] **Thư viện JS tối ưu và cập nhật:** ![Medium][medium_img] Thư viện JS cần thiết, phiên bản mới nhất, tránh thừa.

- 📖 [You may not need jQuery](http://youmightnotneedjquery.com/)
- 📖 [Plain JS](https://plainjs.com/)

- [ ] **Modernizr:** ![Low][low_img] Nếu cần, dùng Modernizr tuỳ chỉnh để thêm class vào `<html>`.

- 🛠 [Tùy chỉnh Modernizr](https://modernizr.com/download?setclasses)

### Kiểm thử JavaScript

- [ ] **ESLint:** ![High][high_img] Không lỗi ESLint.

- 📖 [ESLint](https://eslint.org/)

**[⬆ quay lại đầu](#-muc-luc)**

---

## Bảo mật

### Quét và kiểm tra website

- [securityheaders.io](https://securityheaders.io/)
- [Observatory by Mozilla](https://observatory.mozilla.org/)

### Thực hành tốt

- [ ] **HTTPS:** ![High][high_img] HTTPS được dùng trên mọi trang và cho mọi nội dung ngoài.

- 🛠 [Let's Encrypt](https://letsencrypt.org/)
- 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
- 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

- [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] Header `Strict-Transport-Security` được thiết lập.

- 🛠 [Kiểm tra HSTS preload](https://hstspreload.org/)
- 📖 [HSTS Cheat Sheet – OWASP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)

- [ ] **CSRF:** ![High][high_img] Đảm bảo yêu cầu tới server hợp lệ để ngăn CSRF.

- 📖 [CSRF Prevention Cheat Sheet – OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)

- [ ] **XSS:** ![High][high_img] Trang không có lỗ hổng XSS.

- 📖 [XSS Prevention Cheat Sheet – OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)

- [ ] **Content Type Options:** ![Medium][medium_img] Ngăn Chrome & IE sniff MIME ngoài khai báo.

- 📖 [X-Content-Type-Options – Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

- [ ] **X-Frame-Options:** ![Medium][medium_img] Bảo vệ khỏi clickjacking.

- 📖 [X-Frame-Options – Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)

- [ ] **Content Security Policy:** ![Medium][medium_img] Xác định cách và nguồn tải nội dung.

- 📖 [Content Security Policy – Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)

**[⬆ quay lại đầu](#-muc-luc)**

---

## Hiệu năng

### Thực hành tốt

- [ ] **Mục tiêu đạt được:** ![Medium][medium_img] Trang nên đạt:
  - First Meaningful Paint < 1 s
  - Time To Interactive < 5 s trên cấu hình trung bình (Android $200, 3G chậm) và < 2 s cho lần truy cập lại
  - Kích thước file quan trọng < 170 KB gzip

- 🛠 [Pingdom Tools](https://tools.pingdom.com)
- 🛠 [WebPageTest](https://www.webpagetest.org/)

- [ ] **HTML nén:** ![Medium][medium_img] HTML được nén.

- [ ] **Lazy loading:** ![Medium][medium_img] Ảnh, script, CSS được lazyload.

- [ ] **Kích thước cookie:** ![Medium][medium_img] Mỗi cookie ≤ 4096 byte và domain ≤ 20 cookie.

- 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)

- [ ] **Thành phần bên thứ ba:** ![Medium][medium_img] iframe/JS bên ngoài được thay bằng thành phần tĩnh khi có thể.

- 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Chuẩn bị yêu cầu sắp tới

- 📖 [Giải thích các kỹ thuật](https://css-tricks.com/prefetching-preloading-prebrowsing/)

- [ ] **DNS Prefetch:** ![Low][low_img]

```html
<link rel="dns-prefetch" href="https://example.com" />
```

- [ ] **Preconnect:** ![Low][low_img]

```html
<link rel="preconnect" href="https://example.com" />
```

- [ ] **Prefetch:** ![Low][low_img]

```html
<link rel="prefetch" href="image.png" />
```

- [ ] **Preload:** ![Low][low_img]

```html
<link rel="preload" href="app.js" />
```

- 📖 [Khác biệt giữa prefetch và preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Kiểm thử hiệu năng

- [ ] **Google PageSpeed:** ![High][high_img] Tất cả trang đạt ≥ 90/100.

- 🛠 [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
- 🛠 [Test My Site](https://testmysite.withgoogle.com)
- 🛠 [WebPagetest](https://www.webpagetest.org/)
- 🛠 [GTmetrix](https://gtmetrix.com/)

**[⬆ quay lại đầu](#-muc-luc)**

## Khả năng truy cập (Accessibility)

> **Ghi chú:** Xem playlist [A11ycasts với Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Thực hành tốt

- [ ] **Progressive enhancement:** ![Medium][medium_img] Chức năng chính như navigation và search hoạt động khi tắt JS.

- 📖 [Bật/tắt JavaScript trong DevTools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Tương phản màu:** ![Medium][medium_img] Tương phản đạt tối thiểu WCAG AA (AAA cho mobile).

- 🛠 [Contrast ratio](https://www.siegemedia.com/contrast-ratio)

#### Tiêu đề

- [ ] **H1:** ![High][high_img] Mọi trang có H1 không phải tiêu đề website.
- [ ] **Tiêu đề:** ![High][high_img] Sử dụng tiêu đề đúng thứ tự H1–H6.

- 📹 [Tại sao tiêu đề & landmark quan trọng – A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

### Ngữ nghĩa

- [ ] **Loại input HTML5 cụ thể:** ![Medium][medium_img] Quan trọng cho mobile hiển thị bàn phím phù hợp.

- 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Biểu mẫu

- [ ] **Label:** ![High][high_img] Mỗi input có label. Nếu không hiển thị được, dùng `aria-label`.

- 📖 [aria-label – MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### Kiểm thử khả năng truy cập

- [ ] **Chuẩn A11y:** ![High][high_img] Dùng WAVE để kiểm thử.

- 🛠 [WAVE](http://wave.webaim.org/)

- [ ] **Điều hướng bàn phím:** ![High][high_img] Kiểm thử chỉ với bàn phím theo thứ tự dự đoán.
- [ ] **Trình đọc màn hình:** ![Medium][medium_img] Kiểm thử với screen reader (VoiceOver, ChromeVox, NVDA, Lynx).
- [ ] **Focus style:** ![High][high_img] Nếu focus bị tắt, thay bằng trạng thái hiển thị trong CSS.

- 📹 [Managing Focus – A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ quay lại đầu](#-muc-luc)**

## SEO

- [ ] **Google Analytics:** ![Low][low_img] GA được cài đặt đúng.

- 🛠 [Google Analytics](https://analytics.google.com/analytics/web/)
- 🛠 [GA Checker](http://www.gachecker.com/)

- [ ] **Search Console:** ![Low][low_img] Search Console được cài đặt đúng.

- 🛠 [Search Console](https://search.google.com/search-console/about)

- [ ] **Logic tiêu đề:** ![Medium][medium_img] Tiêu đề giúp hiểu nội dung trang.

- 🛠 [Tota11y – tab Headings](http://khan.github.io/tota11y/#Try-it)

- [ ] **sitemap.xml:** ![High][high_img] sitemap.xml tồn tại và gửi lên Search Console.

- 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

- [ ] **robots.txt:** ![High][high_img] robots.txt không chặn trang quan trọng.

- 🛠 [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

- [ ] **Structured Data:** ![High][high_img] Trang dùng structured data không lỗi.

- 📖 [Giới thiệu Structured Data](https://developers.google.com/search/docs/guides/intro-structured-data)
- 📖 [JSON-LD](https://json-ld.org/)
- 📖 [Microdata](https://www.w3.org/TR/microdata/)
- 🛠 [Rich Results Test](https://search.google.com/test/rich-results)
- 🛠 [Schema.org Full Hierarchy](http://schema.org/docs/full.html)

- [ ] **Sitemap HTML:** ![Medium][medium_img] Sitemap HTML được cung cấp và truy cập từ footer.

- 📖 [Hướng dẫn sitemap – Google Support](https://support.google.com/webmasters/answer/183668?hl=vi)

**[⬆ quay lại đầu](#-muc-luc)**

## Dịch thuật

Danh Sách Kiểm Tra Front‑End cũng có sẵn ở ngôn ngữ khác. Cảm ơn các dịch giả!

- 🇯🇵 Tiếng Nhật: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
- 🇪🇸 Tiếng Tây Ban Nha: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
- 🇨🇳 Tiếng Trung Giản Thể: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
- 🇰🇷 Tiếng Hàn: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
- 🇧🇷 Tiếng Bồ Đào Nha: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
- 🇻🇳 Tiếng Việt: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
- 🇹🇼 Tiếng Trung Phồn Thể: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)
- 🇫🇷 Tiếng Pháp: [ynizon/Front-End-Checklist](https://github.com/ynizon/Front-End-Checklist)
- 🇷🇺 Tiếng Nga: [ungear/Front-End-Checklist](https://github.com/ungear/Front-End-Checklist)
- 🇹🇷 Tiếng Thổ Nhĩ Kỳ: [eraycetinay/Front-End-Checklist](https://github.com/eraycetinay/Front-End-Checklist)
- 🇩🇪 Tiếng Đức: [xfuture603/Front-End-Checklist](https://github.com/xFuture603/Front-End-Checklist)
- 🇵🇱 Tiếng Ba Lan: [mbiesiad/Front-End-Checklist](https://github.com/mbiesiad/Front-End-Checklist)
- 🇮🇩 Tiếng Indonesia: [nniinnoo/Front-End-Checklist](https://github.com/nniinnoo/Front-End-Checklist)

## Hỗ trợ

Nếu bạn có câu hỏi hay gợi ý, hãy liên hệ tôi trên X:

- [X (trước đây là Twitter)](https://ddias.link/x)
- [Chat trên Discord](https://ddias.link/discord)

## Người đóng góp

Dự án tồn tại nhờ tất cả những người đóng góp. ([Đóng góp](https://github.com/thedaviddias/Front-End-Checklist/blob/main/CONTRIBUTING.md)).
<a href="https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors"><img src="https://opencollective.com/front-end-checklist/contributors.svg?width=890" alt="Contributors" /></a>

## Nhà tài trợ

Cảm ơn các nhà tài trợ! 🙏 [[Trở thành nhà tài trợ](https://opencollective.com/front-end-checklist#backer)]

<a href="https://opencollective.com/front-end-checklist#backers" target="_blank"><img src="https://opencollective.com/front-end-checklist/backers.svg?width=890" alt="Backers" /></a>

## Nhà tài trợ chính

Hỗ trợ dự án bằng cách trở thành nhà tài trợ. Logo của bạn sẽ xuất hiện ở đây kèm liên kết website.
[[Trở thành nhà tài trợ](https://opencollective.com/front-end-checklist#sponsor)]

<a href="https://opencollective.com/front-end-checklist" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/1/avatar.svg" alt="Sponsors" /></a>

## Giấy phép

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ quay lại đầu](#-muc-luc)**

[low_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/low.svg
[medium_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/medium.svg
[high_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/high.svg
```

