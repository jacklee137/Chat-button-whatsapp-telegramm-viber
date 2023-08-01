```html
<div class="messenger">
    <div title="Чат с менеджером" class="messenger-btn"><img
            src="/files/2/chat.svg"
            alt="Чат с менеджером"
        /></div>
    <div id="messenger-links" class="messenger-links">
        <a title="phone" href="tel:+79093802519" target="_blank"><img
                src="/files/2/icons8-phone.svg"
                alt="phone"
            /></a>
        <a title="Whatsapp" href="https://wa.me/+79093802519" target="_blank"><img
                src="/files/2/whatsapp.svg"
                alt="Whatsapp"
            /></a>
        <a title="Viber" href="viber://chat?number=%2B+79093802519" target="_blank"><img
                src="/files/2/icons8-viber.svg"
                alt="Viber"
            /></a>
        <a title="Telegramm" href="https://t.me/kopiprint34" target="_blank"><img
                src="/files/2/telegramm.svg"
                alt="Вконтакте"
            /></a>
    </div>
</div>
```

2. Блок - CSS
```css


.messenger {
  display: block;
  position: fixed;
  right: 5%;
  bottom: 10%;
  width: 260px;
  height: 60px;
  /* overflow: hidden; */
  }
  .messenger-btn {
    text-align: center;
  padding: 14px;
  display: block;
  width: 100px;
  height: 100px;
  border-radius: 60px;
  background-color: #f35858;
  position: absolute;
  right: 0;
  top: 0;
  cursor: pointer;
  z-index: 2;
  }
  .messenger-btn img {
  width: 80px;
  height: 80px;
  }
  .messenger-links {
  position: absolute;
  width: 400px;
  left: 50px;
  top: 10px;
  transform: scale(0);
  transform-origin: 100% 50%;
  -webkit-transition: all 0.3s;
  -o-transition: all 0.3s;
  transition: all 0.3s;
  z-index: 0;
  }
  .messenger-links.show {
  left: -270px;
  transform: scale(1);
  }
  .messenger-links a {
  width: 40px;
  margin-left: 4px;
  }
  .messenger-links img {
    width: 90px;
  max-width: 90px;
  -webkit-transition: all 0.3s;
  -o-transition: all 0.3s;
  transition: all 0.3s;
  }
  .messenger-links a:hover img {
  transform: scale(1.1);
  text-decoration: none;
  }
```

3. Блок
```js
/* При клике показываем или скрываем кнопки мессенджеров */

var menuBtn = $('.messenger-btn'),
menu = $('.messenger-links');
menuBtn.on('click', function() {
if ( menu.hasClass('show') ) {
menu.removeClass('show');
} else {
menu.addClass('show');
}
});

/*  Скрыть div при клике в любом месте сайта кроме самого div */

$(document).mouseup(function (e){
var div = $('.messenger');
if (!div.is(e.target)
&& div.has(e.target).length === 0) {
$('.messenger-links').removeClass('show');
}
});