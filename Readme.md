Flexbox is very good technique, but it introduce many concepts and that can make difficult to use.
To learn flexbox well, practice with some patterns with your own code is very good.

This is practice lessions, assume you've learned some basic concepts with flexbox. 

1. Site header

![Screenshot from 2020-10-26 05-50-40](https://user-images.githubusercontent.com/25763557/97121244-61775d80-174f-11eb-8af1-1993c6b7fdfe.png)

If you've learned float before, the typical way to layout this would be wrap the logo and left element with one container, and the settings & Logout with another. 
Use float to push one to the left, and another to the right. You still need clearfix to clear float for another element.

But we can do this with float. Our **display: flex** work fine here.

**justify-content: space-between** will make the element span all the container space. There space is not equal, and one container will be placed on the left, and another on the right.

**align-items: center** centers all the element on the cross axis,(here is vertical). 

```
.header {
    display: flex;
    justify-content: space-between;
    padding: 10px;
    background-color: #56727C;
}

.header__section {
    display: flex;
    align-items: center;
}

.siteHeader__item {
    padding: 5px 15px;
    font-size: 12px;
}

.header__item + .header__item {
    margin-left: 5px;
}

.header__item.is-site-header-item-selected {
    color: #FFFFFF;
    background-color: #415F69;
    border-radius: 4px;
}

.headerLogo {
    font-size: 20px;
    line-height: 0;
    color: white;
}

.headerButton {
    cursor: pointer;
    color: #D9E9EF;
}
```

HTML 


``` html
<div class="header">
  <!-- This section gets pushed to the left side-->
  <div class="header__section">
    <div class="header__item headerLogo">
      <div class="fa fa-inbox"></div>
    </div>
    <div class="header__item headerButton is-site-header-item-selected">Inbox</div>
    <div class="header__item headerButton">Sent</div>
    <div class="header__item headerButton">Trash</div>
  </div>
  <!-- This section gets pushed to the right side-->
  <div class="header__section">
    <div class="header__item headerButton">Settings</div>
    <div class="header__item headerButton">Log out</div>
  </div>
</div>

```


2. Center our element 

![Screenshot from 2020-10-26 06-15-38](https://user-images.githubusercontent.com/25763557/97121928-799dab80-1754-11eb-968b-7ad7292870e2.png)


You can center 1 element with

**flex-direction: column** This specify the main axis(default is row).
**justify-content: center** groups the children as close as possible to one another, make element center in the main-axis 
**align-items: center** centers the children along this axis(cross axis), having a similar effect as settingtext-align: center.

```css
.centered {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 300px;
    padding: 10px;
}

.centered__item + .centered__item {
    margin-top: 5px;
}

.centeredIcon {
    font-size: 60px;
    line-height: 0;
}

.centeredLabel {
    color: #86969C;
    font-size: 30px;
    font-weight: 700;
    text-align: center;
}

.centeredDetails {
    color: #86969C;
    font-size: 16px;
    margin-bottom: 10px;
    text-align: center;
}

.icon {
    color: #BCD2DA;
}

```


```html
<div class="centered">
  <div class="centered__item centeredIcon">
    <div class="icon fa fa-smile-o"></div>
  </div>
  <div class="centered__item centeredLabel">Welcome to the app!</div>
  <div class="centered__item centeredDetails">Thanks for signing up. Let&rsquo;s take a look around.</div>
  <div class="centered__item button">Begin tour</div>
</div>

```

3. Card items

![Screenshot from 2020-10-26 06-19-48](https://user-images.githubusercontent.com/25763557/97121942-a18d0f00-1754-11eb-9c6c-96fd56d99e4f.png)


We can make children element span equally with flexbox.

Unlike the ones we’ve used so far, this property is applied to the children, not the container.
We will use flex property, this is  a flexbox short-hand

```css
.card__containner {
	display: flex;
	border: 1px solid #CAD0D2;
	border-radius: 4px;
	overflow: hidden;
}

.card__containner__card {
	flex: 1 1 0%;
	border: none;
	border-radius: 0;
}

.card__containner__card+.card__containner__card {
	border-left: 1px solid #D7DBDD;
}

.card__containner__cardDescription {
	flex: 1 1 auto;
}

```

```html
<div class="card__containner">
    <div class="card card__containner__card">
        <div class="card__description card__containner__cardDescription">
            <div class="icon fa fa-thumbs-o-up card__descriptionIcon"></div>
            <div class="card__descriptionText">Trial</div>
        </div>
        <div class="card__price">Free!</div>
    </div>
    <div class="card card__containner__card">
        <div class="card__description card__containner__cardDescription">
            <div class="icon fa fa-trophy card__descriptionIcon"></div>
            <div class="card__descriptionText">Basic tier<br />(most popular)</div>
        </div>
        <div class="card__price">$10.00</div>
    </div>
    <div class="card card__containner__card">
        <div class="card__description card__containner__cardDescription">
            <div class="icon fa fa-bolt card__descriptionIcon"></div>
            <div class="card__descriptionText">Advanced tier<br />(only for enterprise-level professionals)</div>
        </div>
        <div class="card__price">$6,000.00</div>
    </div>
</div>

```


4. The last one, this is the last difficult example. I did not completed this fully yet.

![Screenshot from 2020-10-26 06-45-01](https://user-images.githubusercontent.com/25763557/97122209-cc786280-1756-11eb-8e35-2f23748fa333.png)

```html
<div class="stream">
    <div class="post">
        <div class="postUser">
            <div class="postUser__portrait">
                <span class="icon fa fa-user-circle-o"></span>
            </div>
            <div class="postUser__name">CJ C.</div>
        </div>
        <div class="postBody">
            <div class="postBody__content">
                do something
            </div>
            <div class="postBody__date">
                May 27
            </div>
        </div>
    </div>

    <div class="post">
        <div class="postUser">
            <div class="postUser__portrait">
                <span class="icon fa fa-user-circle-o"></span>
            </div>
            <div class="postUser__name">Jatesh V.</div>
        </div>
        <div class="postBody">
            <div class="postBody__content">
                flexbox learning pattern
            </div>
            <div class="postBody__date">
                May 28
            </div>
        </div>
    </div>

    <div class="post">
        <div class="postUser">
            <div class="postUser__portrait">
                <span class="icon fa fa-user-circle-o"></span>
            </div>
            <div class="postUser__name">Damien S.</div>
        </div>
        <div class="postBody">
            <div class="postBody__content">
                cross the line
            </div>
            <div class="postBody__date">
                June 1
            </div>
        </div>
    </div>

    <div class="post">
        <div class="postUser">
            <div class="postUser__portrait">
                <span class="icon fa fa-user-circle-o"></span>
            </div>
            <div class="postUser__name">Ziggie G.</div>
        </div>
        <div class="postBody">
            <div class="postBody__content">
                puff
            </div>
            <div class="postBody__date">
                June 5
            </div>
        </div>
    </div>
</div>
```

```css
.stream {
	display: flex;
	flex-direction: column-reverse;
}

.post+.post {
	margin-bottom: 5px;
}
.post {
	display: -ms-flexbox;
	display: flex;
}

.postUser {
	-ms-flex: 0 1 auto;
	flex: 0 1 auto;
	padding-bottom: 10px;
}

.postUser__portrait {
	display: -ms-flexbox;
	display: flex;
	-ms-flex-pack: center;
	justify-content: center;
	-ms-flex-align: center;
	align-items: center;
	width: 100px;
	height: 90px;
	font-size: 70px;
	line-height: 0;
}

.postUser__name {
	color: #57727C;
	font-size: 12px;
	font-weight: 700;
	line-height: 1;
	text-align: center;
}

.postBody {
	-ms-flex: 1 1 0%;
	flex: 1 1 0%;
	position: relative;
	padding: 15px;
	border: 1px solid #CAD0D2;
	border-radius: 4px;
}

.postBody:after,
.postBody:before {
	right: 100%;
	top: 35px;
	border: solid transparent;
	content: " ";
	height: 0;
	width: 0;
	position: absolute;
	pointer-events: none;
}

.postBody:after {
	border-color: transparent;
	border-right-color: #ffffff;
	border-width: 8px;
	margin-top: -8px;
}

.postBody:before {
	border-color: transparent;
	border-right-color: #CAD0D2;
	border-width: 9px;
	margin-top: -9px;
}

.postBody__content {
	color: #57727C;
	font-size: 12px;
}

.postBody__date {
	margin-top: 5px;
	color: #86969C;
	font-size: 10px;
	text-transform: uppercase;
	letter-spacing: 1px;
}

```

