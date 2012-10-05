## Bi App SASS
bi-app lets you write your stylesheets once, and have them compiled into 2 different stylesheets one for `left-to-right` layout, and the other for `right-to-left` layouts 

created by [Anas Nakawa](//twitter.com/anasnakawa), inspired by 
[Victor Zamfir](//twitter.com/victorzamfir)

## License
[MIT License](http://www.opensource.org/licenses/mit-license.php)

## Why
usually when writing stylesheets for bi-directional sites/apps, both `ltr` & `rtl` stylesheets mostly will look the same, except for direction related properties (`float, text-align, padding, margin ..etc` ), so when you write a `float: left` in some `ltr` stylesheet, you'll have to write it again as `float: right` for the `rtl` one

when using **bi-app-sass** , all you have to do is to write your stylesheets once using a predefined mixins for those direction related properties, and once you compile your stylesheets, you'll have a ready 

## How to use it
create three sass files
<pre>
app-rtl.scss    // rtl interface to be compiled
app-ltr.scss    // ltr interface
_app.scss       // private file where you will write your styles (won't be compiled)
</pre>
in the `app-ltr.scss` only include the following
```css
@import 'bi-app-ltr';
@import 'app';
```

same for `app-rtl.scss`
```css
@import 'bi-app-rtl';
@import 'app';
```

now you can write your styles in `_app.scss`, using bi-app mixins, as you were styling for only `ltr` layouts, and the `rtl` styles will be compiled automatically!
```css
.foo {
  display: block;
  @include float(left);
  @include border-left(1px solid white);
  ...
}
```