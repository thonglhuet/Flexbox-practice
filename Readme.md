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
We can make children element span equally with flexbox.

Unlike the ones we’ve used so far, this property is applied to the children, not the container.

We need 
