
<img src="https://pbs.twimg.com/profile_images/788014136575668224/lxEKmMnB_400x400.jpg" width="100">

<img src="http://i.imgur.com/yqRg1pl.png" width="100">

---

<a name="getstarted"></a>
> **`jQuery` 是一個跨瀏覽器的免費開源 `JavaScript` 庫**。

> 流行的 `jQuery` `JavaScript` 庫有一個簡潔便攜的 `JavaScript` `API` 集合，用於快速的 `web` 開發，該庫是經 `MIT` 和 `GPL` 許可的免費庫。

> `jQuery` 庫是輕量級的（縮小/Gzip 壓縮後僅 25KB）、`CSS3` 相容且跨瀏覽器的。它提供一個豐富的 `API` 集合，包括 `HTML` `文件物件模型`（`DOM`）遍歷和操作，可使用事件，且允許通過使用 `Asynchronous JavaScript` 和 `XML` (`Ajax`) 請求 `API` 進行伺服器通訊。除此之外，它也提供>了網頁動畫和影象效果，以及一個功能強大的外掛架構。

> 其核心設計思想是“`寫更少的程式碼，做更多的事情`”(`Write Less Do More`)。

> `jQuery` 提供了一套易於使用的 `API`。這些 `API` 極大地簡化了客戶端(瀏覽器)程式設計過程中的許多方面，包括：
- `HTML` `DOM` 的遍歷與操作
- 瀏覽器事件處理
- `AJAX`（`Asynchronous JavaScript And XML`）程式設計
- 特效（如動畫效果）

> 在直接使用 `JavaScropt`+`DHTML` 的傳統客戶端程式設計方式下，開發人員不得不編寫冗長的程式碼。並且，為了使這些程式碼能夠相容不同的瀏覽器，我們還得編寫額外的程式碼來處理這些跨瀏覽器問題。`jQuery` 的設計目標正是在於簡化客戶端程式設計。讓我們能夠編寫簡練的程式碼，節約開發時間，而這些程式碼卻一樣可以功能強大，並且相容多種瀏覽器。

> **`jQuery` 網站上提供了兩種方式的釋出檔案。一種是內容經過壓縮的檔案；另一種是原始檔案。前者檔案中不包含程式碼註釋以及程式碼執行過程中不需要的空白字元，它適合於生產環境(正式使用的環境)中使用，可以減少檔案載入所需時間。後者檔案中包含詳細的程式碼註釋，適合於開發和測試環境中使用。**

> **`jQuery` 語法的設計思想是"選擇元素，對其操作"。這和 `CSS` 規則的語法非常類似。**

`jQuery` 的語法其實正是模仿了 `CSS` 規則的語法。其語法如下：

```js
$(selector).action(actionParameter);
```

這是個鏈式語法。因此，上述的語法等效於：

```js
var objTargetElements; //要施加操作的目標元素
objTargetElements = $(selector); //指定目標元素
//呼叫 objTargetElements 的相關方法，對目標元素進行操作
objTargetElements.action(actionParameter);
```

> $ ：美元符是 `jQuery` 核心函式 `jQuery` 的一個別名。當然，在 `JavaScript` 中“$”是一個合法的函式名。 Selector 引數指定了一個 `jQuery` 選擇器。`jQuery` 選擇器類似於 `CSS` 中的選擇器，它告訴 `jQuery` 我們準備對哪些元素進行操作(action)。並且，`CSS` 中的各種選擇器 `jQuery` 中都有等同的選擇器。

> action ：該方法指定了要對 selector 所指定的元素進行什麼具體操作。actionParameter 引數是個可選引數，是根據具體所指定的方法來定的，它會隨具體方法的變化而變化。

##### 從本地站點引用 `jQuery`
```html
<html>
  <head>
    <title>使用 jQuery</title>
    <script src="../js/lib/jQuery/1.9.1/jQuery.js"></script>
  </head>

  <body>
  </body>
</html>
```

##### 從 `CDN` 引用 `jQuery`
```html
<html>
  <head>
    <title>使用 jQuery</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
  </head>

  <body>
  </body>
</html>
```

##### `Hello World`
```html
<html>
  <head>
    <meta http-equiv="content-type" content="text/html;charset=utf-8">
    <script src="../js/lib/jQuery/1.9.1/jQuery.js"></script>
    <script>
      function initPage() {
        //jQuery 程式碼：呼叫 jQuery 的核心函式－－－$函式
        $("#message").html("Hello World, it is now:" + new Date().toLocaleString());
      }
    </script>
  </head>

  <body onload="initPage()">
    <span id="message"></span>
  </body>
</html>
```

> initPage 這個函式會在頁面載入完畢後被呼叫。而該函式在執行後會在 ID 為 message 的 HTML 結點內新增表示客戶端當前時間的字串。

![](http://www.ibm.com/developerworks/cn/web/1311_huangwh_jqueryhandson/image007.jpg)

```html
<a href="https://www.ibm.com/developerworks/cn/" target="_blank">IBM developerWorks 中文站</a><br/>
<a href="https://www.ibm.com/developerworks" target="_blank">IBM developerWorks</a><br/>
<a href="/" target="_blank">首頁</a><br/>
```

```js
//用基于元素名称的选择器去匹配页面中的所有链接元素
$("a").each(function(index, ele) { //匿名函数作为 each 方法的参数，供其调用
  console.log("链接" + index + ":" + ele.href); //往控制台中打印链接 URL
});
```

```js
$("#tip").css("font-weight","bold");
```

---

```css
a {
  font-size: 25px;
}
```


```js
$("a").each(function() { //選擇器表示式是"a"
  $(this).css("fontSize", "25px");
});
```

```js
/*
選擇所有類為 amount 的元素
each 方法會針對選擇器所匹配的每個元素
呼叫該方法的引數中所指定的函式。並將該
元素作為函式呼叫的第二個實際引數。
*/
$(".amount").each(function(i, ele) {
  //設定元素的值為其當前值加上貨幣符號字首
  $(ele).val("￥" + $(ele).val());
});
```

```css
input[type="text"] {
  background-color: yellow;
}
```

```js
$("input[type=text]").css('background-color', 'yellow');
```
---

```js
$(document).ready(initPage); //頁面載入完畢後，jQuery 會回撥 initPage
```

```js
$(function() { //該函式在頁面載入完畢會被 jQuery 呼叫
  //事件處理程式碼
});
```
---

```js
//當 ID 為 btnDetails 的按鈕被單擊時，下面的匿名函式會被 jQuery 呼叫
$("#btnDetails").bind("click", function() {
  $("#divDetails").toggle(); //顯示或者隱藏 ID 為 divDetails 的元素
});
```

> `bind` 方法的語法是：
`event`：要處理的事件的名稱。該名稱不需要加字首 on。
`handler`：事件監聽器，即對瀏覽器事件進行處理的函式。這通常是一個匿名函式。**在 `event` 引數所表示的事件被觸發後，`jQuery` 會呼叫這個函式（即回撥），並向該函式傳入一個 `jQuery` 自定義的事件物件**。該事件物件是 `jQuery` 根據原始的瀏覽器事件物件建立的。`jQuery` 這麼做是通過
一個"中立"的事件物件來規避不同的瀏覽器所提供的同一個事件的事件物件的屬性不同的問題。這使得我們可以用同樣的程式碼處理事件，而不必關心不同瀏覽器所提供的原始事件物件的差異。
`data` ：表示需要在事件觸發後傳遞給事件監聽器的額外資料。它是作為 `jQuery` 事件物件的 `data` 屬性傳遞給事件監聽器的。

```js
$("#txtVerifyCode").bind("keypress", function(evt) {
  var keyCode = evt.which; //從事件物件中獲取當前按鍵的編碼值
  var char = String.fromCharCode(keyCode); //將按鍵的編碼轉換為相應的字元
  if (!/\d/.test(char)) { //當前輸入的字元不是數字字元
    //呼叫事件物件的 preventDefault 方法，取消事件的預設行為，此處即取消輸入。
    evt.preventDefault();
  }
});
```
---

```js
function showTip(msg) {
  $("#divTips").html(msg); //顯示具體的提示內容
}
```

```js
function showTipHandler(evt) {
  var data = evt.data; //獲取額外引數
  /*額外引數是一個我們根據需要的自定義物件。這裡，我們假設這個物件有個 msg 屬性。
    它表示希望要顯示的提示資訊。
  */
  var msg = data.msg;
  showTip(msg);
}
```

```js
$('#tip1').bind('click', {
  msg: '中文提示'
}, showTipHandler);
$('#tip2').bind('click', {
  msg: 'English tip'
}, showTipHandler);
```

#### :books: 參考網站：
- [jQuery 实验教程](http://www.ibm.com/developerworks/cn/web/1311_huangwh_jqueryhandson/)
- [使用 jQuery 进行基于 DOM 的数据存储和检索 ](http://www.ibm.com/developerworks/cn/web/wa-domjquery/)
- [.mouseout()](https://api.jquery.com/mouseout/)
- [.css()](https://api.jquery.com/css/)
- https://msdn.microsoft.com/en-us/library/bb299886.aspx

---

```js
$("p").addClass("myClass yourClass");
```

- [.addClass()](https://api.jquery.com/addclass/)

---

#### :books: 參考網站：
- [lazyload](#lazyload)

---

```js
jQuery(document).ready(function() {});

$(document).ready(function() {});

$(function() {});
```

#### :books: 參考網站：
- [ready](http://api.jquery.com/ready/)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>jQuery demo</title>
  </head>

  <body>
    <!--[if lt IE 9]>
    <script src="jquery-1.9.0.js"></script>
  <![endif]-->
    <!--[if gte IE 9]>
    <script src="jquery-2.0.0.js"></script>
  <!--<![endif]-->

    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    <script>
      $(document).ready(function() {
        $("p").text("The DOM is now loaded and can be manipulated.");
      });
    </script>
  </body>
</html>

```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>load demo</title>
    <style>
      body {
        font-size: 12px;
        font-family: Arial;
      }
    </style>
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
  </head>

  <body>
    <b>Successful Response (should be blank):</b>
    <div id="success"></div><b>Error Response:</b>
    <div id="error"></div>
    <script>
      $("#success").load("/not-here.php", function(response, status, xhr) {
        if (status == "error") {
          var msg = "Sorry but there was an error: ";
          $("#error").html(msg + xhr.status + " " + xhr.statusText);
        }
      });
    </script>
  </body>
</html>
```

#### :books: 參考網站：
- [load](http://api.jquery.com/load/)

---

`ajax/test.html`

```html
<ul class="level-1">
  <li class="item-i">I</li>
  <li class="item-ii">II
    <ul class="level-2">
      <li class="item-a">A</li>
      <li class="item-b">B
        <ul class="level-3">
          <li class="item-1">1</li>
          <li class="item-2">2</li>
          <li class="item-3">3</li>
        </ul>
      </li>
      <li class="item-c">C</li>
    </ul>
  </li>
  <li class="item-iii">III</li>
</ul>
```


```js
$.post("ajax/test.html", function(data) {
  $(".result").html(data);
});

$.post("ajax/test.html", function(data) {
  $($.parseHTML(data)).find("li").css("background-color", "red");
});
```

#### :books: 參考網站：
- [post](http://api.jquery.com/jQuery.post/)
- [get](https://api.jquery.com/jquery.get/)
- [parseHTML](http://api.jquery.com/jQuery.parseHTML/)
- [find](http://api.jquery.com/find/)

---

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>attr demo</title>
    <style>
      p {
        margin: 20px 0 0;
      }
      
      b {
        color: blue;
      }
    </style>
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
  </head>

  <body>
    <input id="check1" type="checkbox" checked="checked">
    <label for="check1">Check me</label>
    <p></p>

    <script>
      $("input")
        .change(function() {
          var $input = $(this);
          $("p").html(".attr( 'checked' ): <b>" + $input.attr("checked") + "</b><br>" +
            ".prop( 'checked' ): <b>" + $input.prop("checked") + "</b><br>" +
            ".is( ':checked' ): <b>" + $input.is(":checked") + "</b>");
        })
        .change();
    </script>
  </body>
</html>

```

#### :books: 參考網站：

- [attr](http://api.jquery.com/attr/)

---

<a name="lazyload"></a>

[source code](https://jsfiddle.net/cccgtso7/)


```html
<script src="jquery.js"></script>
<script src="jquery.lazyload.js"></script>

<img class="lazy" data-original="http://placehold.it/640x480" width="640" height="480">

<script>
  $(function() {
    //  $("img.lazy").lazyload();
    $("img.lazy").lazyload({
      effect: "fadeIn"
    });
  });

</script>
```

**Install with Bower**
```
shell> bower install jquery.lazyload
```

- [jquery_lazyload](https://github.com/tuupola/jquery_lazyload)
- [lazyload](http://www.appelsiini.net/projects/lazyload)
- [lazyload](http://www.appelsiini.net/projects/lazyload/enabled_fadein.html)

---

```js
$("div.demo-container").text("<p>This is a test.</p>");
$("p").text("<b>Some</b> new text.");

$("div.demo-container").html();

$("li").add("p").css("background-color", "red");
$("p").add("span").css("background", "yellow");

$(".inner").append("<p>Test</p>");

$("#target").click(function() {
  alert("Handler for .click() called.");
});

$("p").click(function() {
  var htmlString = $(this).html();
  $(this).text(htmlString);
});

$("div.demo-container").html("<p>All new content. <em>You bet!</em></p>");

$.ajax({
  url: "test.html",
  context: document.body
}).done(function() {
  $(this).addClass("done");
});

$.ajax({
  statusCode: {
    404: function() {
      alert("page not found");
    }
  }
});

$.ajax({
  method: "POST",
  url: "some.php",
  data: {
    name: "John",
    location: "Boston"
  }
}).done(function(msg) {
  alert("Data Saved: " + msg);
});


$.ajax({
  url: "test.html",
  cache: false
}).done(function(html) {
  $("#results").append(html);
});


$.getJSON("test.js", function(json) {
  console.log("JSON Data: " + json.users[3].name);
});
```

```js
$( "#result" ).load( "ajax/test.html" );
$( "#result" ).load( "ajax/test.html", function() {
  alert( "Load was performed." );
});

```

```js
$("#result").load("ajax/test.html");
$("#result").load("ajax/test.html", function() {
  alert("Load was performed.");
});
```

---

#### :books: 參考網站：
- [lazyload](http://www.appelsiini.net/projects/lazyload)
- [dummyimage](http://dummyimage.com/)
- [jquery-dateFormat](https://github.com/phstc/jquery-dateFormat)
- [jquery-number](https://github.com/customd/jquery-number)
- [jQuery.formError](https://github.com/GarethElms/jQuery.formError)

---

```html
<!doctype html>
<html lang="en">

  <head>
    <meta charset="utf-8">
    <title>scrollTop demo</title>
    <style>
      pre {
        height: 600px;
      }
    </style>
  </head>

  <body>
    <a href="#" id="header">Header</a>
    <pre></pre> Go to <a href="#header">Header</a>
    <pre></pre> Go to <a href="#header">Header</a>
    <pre></pre> Go to <a href="#header">Header</a>

    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-easing/1.3/jquery.easing.min.js"></script>
    <script>
      $(function() {
        $('a').click(function() {
          $('html,body').animate({
            scrollTop: $('#header').offset().top
          }, 2000, 'easeOutBounce');

          return false;
        });
      });
    </script>
  </body>
</html>
```

#### :books: 參考網站：

- http://gsgd.co.uk/sandbox/jquery/easing/
- [animate](http://api.jquery.com/animate/)
- [offset](http://api.jquery.com/offset/)
- [fadeout](http://api.jquery.com/fadeout/)

---

```html
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"></script>
<script src="http://malsup.github.com/jquery.cycle2.js"></script>
```

#### :books: 參考網站：
- http://jquery.malsup.com/cycle2/
- http://jquery.malsup.com/cycle2/demo/background.php
- http://jquery.malsup.com/block/

---

[source code](https://jsfiddle.net/wo3oqodm/)

```html
<div id="box1"></div>
```
```css
#box1 {
  width: 60px;
  height: 60px;
  background-color: green;
}
```
```js
$("#box1").click(function() {
  $(this).fadeOut(1000, function() {
    $(this).css("background-color", "blue").fadeIn(1000);
  });
});

```

#### :books: 參考網站：
- [click](http://api.jquery.com/click/)
- [fadeOut](http://api.jquery.com/fadeOut/)
- [css](http://api.jquery.com/css/)
- [fadeIn](http://api.jquery.com/fadeIn/)


---

```html
<script type="application/javascript">
  $(function() {
    $.getJSON("https://api.ipify.org?format=jsonp&callback=?",
      function(json) {
        document.write("My public IP address is: ", json.ip);
      }
    );
  });
</script>
```
#### :books: 參考網站：
- [ipify](https://www.ipify.org/)

---

```js
var a = 1;

function myCallback() {
  if (a == 1) {
    $(this).css("background-image", "url('http://placehold.it/350x150')");
    a = 2;
  } else if (a == 2) {
    $(this).css("background-image", "url('http://placehold.it/350x150')");
    a = 3;
  } else if (a == 3) {
    $(this).css("background-image", "url('http://placehold.it/350x150')");
    a = 1;
  }
}

setInterval(myCallback, 2000);
```
```js
var a = 1;
setInterval(function() {
  switch (a++ % 3) {
    case 0:
      $(this).css("background-image", "url('http://placehold.it/350x150')");
      break;
    case 1:
      $(this).css("background-image", "url('http://placehold.it/350x150')");
      break;
    case 2:
      $(this).css("background-image", "url('http://placehold.it/350x150')");
      break;
  }
}, 2000);
```

#### :books: 參考網站：
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch
- https://jsfiddle.net/

---

`jQuery UI`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>jQuery UI Draggable - Default functionality</title>
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <link rel="stylesheet" href="/resources/demos/style.css">
    <style>
      #draggable {
        width: 150px;
        height: 150px;
        padding: 0.5em;
      }
    </style>
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script>
      $(function() {
        $("#draggable").draggable();
      });
    </script>
  </head>

  <body>
    <div id="draggable" class="ui-widget-content">
      <p>Drag me around</p>
    </div>
  </body>
</html>
```

### Accordion

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>jQuery UI Accordion - Default functionality</title>
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <link rel="stylesheet" href="/resources/demos/style.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script>
      $(function() {
        $("#accordion").accordion();
      });
    </script>
  </head>

  <body>
    <div id="accordion">
      <h3>Section 1</h3>
      <div>
        <p>
          Mauris mauris ante, blandit et, ultrices a, suscipit eget, quam. Integer ut neque. Vivamus nisi metus, molestie vel, gravida in, condimentum sit amet, nunc. Nam a nibh. Donec suscipit eros. Nam mi. Proin viverra leo ut odio. Curabitur malesuada. Vestibulum
          a velit eu ante scelerisque vulputate.
        </p>
      </div>
      <h3>Section 2</h3>
      <div>
        <p>
          Sed non urna. Donec et ante. Phasellus eu ligula. Vestibulum sit amet purus. Vivamus hendrerit, dolor at aliquet laoreet, mauris turpis porttitor velit, faucibus interdum tellus libero ac justo. Vivamus non quam. In suscipit faucibus urna.
        </p>
      </div>
      <h3>Section 3</h3>
      <div>
        <p>
          Nam enim risus, molestie et, porta ac, aliquam ac, risus. Quisque lobortis. Phasellus pellentesque purus in massa. Aenean in pede. Phasellus ac libero ac tellus pellentesque semper. Sed ac felis. Sed commodo, magna quis lacinia ornare, quam ante aliquam
          nisi, eu iaculis leo purus venenatis dui.
        </p>
        <ul>
          <li>List item one</li>
          <li>List item two</li>
          <li>List item three</li>
        </ul>
      </div>
      <h3>Section 4</h3>
      <div>
        <p>
          Cras dictum. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aenean lacinia mauris vel est.
        </p>
        <p>
          Suspendisse eu nisl. Nullam ut libero. Integer dignissim consequat lectus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.
        </p>
      </div>
    </div>
  </body>
</html>
```

### Autocomplete

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>jQuery UI Autocomplete - Default functionality</title>
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <link rel="stylesheet" href="/resources/demos/style.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script>
      $(function() {
        var availableTags = [
          "ActionScript",
          "AppleScript",
          "Asp",
          "BASIC",
          "C",
          "C++",
          "Clojure",
          "COBOL",
          "ColdFusion",
          "Erlang",
          "Fortran",
          "Groovy",
          "Haskell",
          "Java",
          "JavaScript",
          "Lisp",
          "Perl",
          "PHP",
          "Python",
          "Ruby",
          "Scala",
          "Scheme"
        ];
        $("#tags").autocomplete({
          source: availableTags
        });
      });
    </script>
  </head>

  <body>
    <div class="ui-widget">
      <label for="tags">Tags: </label>
      <input id="tags">
    </div>
  </body>
</html>

```
---

#### :books: 參考網站：
- [jQuery.Marquee](https://github.com/aamirafridi/jQuery.Marquee)

---

```html
<script>
  window.onload = fnInit;

  function fnInit() {}
</script>
```

---

```js
function Person(firstName) {
  this.age = 0;
  this.firstName = firstName;

  setInterval(function growUp() {
    this.age++;
  }, 1000);
};

Person.prototype = {
  sayHello: function() {
    console.log("Hello, I'm " + this.firstName);
  },
  walk: function() {
    console.log("I am walking!");
  },
  sayGoodBye: function() {
    console.log("Goodbye!");
  }
};

/*
var p = new Person();
var person1 = new Person();
var person2 = new Person();
*/

var person1 = new Person('Alice');
var person2 = new Person('Bob');

console.log('person1 is ' + person1.firstName); // logs "person1 is Alice"
console.log('person2 is ' + person2.firstName); // logs "person2 is Bob"

person1.sayHello();
person2.sayHello();

person1.walk();
person2.walk();
```
---

```html
<script>
  $("a").click(function(event) {
    event.preventDefault();
    $("<div>")
      .append("default " + event.type + " prevented")
      .appendTo("#log");
  });
</script>
```

```html
<script type="text/javascript">
  $.ajax({
    type: "GET",
    url: "/path/to/data.xml",
    dataType: "xml",
    success: function(xmlData) {
      var totalNodes = $('*', xmlData).length; // count XML nodes
      alert("This XML file has " + totalNodes);
    },
    error: function() {
      alert("Could not retrieve XML file.");
    }
  });
</script>
```

```js
$("#target").submit(function(event) {
  alert("Handler for .submit() called.");
  //prevent the default action	
  event.preventDefault();
});
```
---

```html
<script type="text/javascript">
  var allImages = $("img"); // all IMG elements 
  var allPhotos = $("img.photo"); // all IMG elements with class "photo"
  var curPhoto = $("img#currentPhoto"); // IMG element with id "currentPhoto"
</script>

<script type="text/javascript">
  $("img").css({
      "padding": "1px",
      "border": "1px solid #333"
    })
    .wrap("<div class='img-wrap'/>");
</script>
```

```js
// shows every <p> on the page
$("p").show();

// hides every <p> on the page
$("p").hide();

// hides every other <p> on the page
$("p:odd").hide();
```
```html
<input type="button" id="showPicture">
<img src="/pic.jpg" id="picture"><span>This is the picture's caption</span>

<script type="text/javascript">
  $("#picture").hide().next().hide();
  $("#showPicture").click(function() {
    $("#picture").show("fast", function() {
      $("#picture").next().show();
    });
  });
</script>
```

#### :books: 參考網站：
- https://www.ibm.com/developerworks/xml/tutorials/x-processxmljquerytut/

---

#### :books: 參考網站：
- [CodeIgniter and Ajax using jQuery](https://www.ibm.com/developerworks/library/wa-aj-codeigniter/)
- [Very simple login using Perl, jQuery, Ajax, JSON and MySQL](https://www.ibm.com/developerworks/library/ws-simplelogin/)

---

```js
if ($(window).width() < 960) {
  console.log('Less than 960');
} else {
  console.log('More than 960');
}
```

#### :books: 參考網站：
- [width](http://api.jquery.com/width/)

---

<img src="http://zeptojs.com/logo.png" width="300">

#### :books: 參考網站：
- [zeptojs](http://zeptojs.com/)
- [velocityjs](http://velocityjs.org/)

---
