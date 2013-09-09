---
[µProjects](http://github.com/g4v3/microProjects)/[bodyAbstractionLayer](http://github.com/g4v3/microProjects/tree/bodyAbstractionLayer)
---
##To avoid of `<frame>` or `<iframe>`
This model can be used to put previously prepared pages inside each other without need for `<frame>`s or `<iframe>`s.
###`#bodyAbstractionLayer`
* Use it as your page's window and `html` element.
* Only child is `#bodyContentHere`.

```
 #bodyAbstractionLayer
{bottom:0
;display:block
;left:0
;overflow:auto
;position:fixed
;right:0
;top:0
}
```
###`#bodyContentHere`
* Use it as your page's `body`.
* Nest inside `#bodyAbstractionLayer`.

```
 #bodyContentHere
{display:block
;min-height:100%
;position:relative
}
```
##Sandbox `<body>` content that isn't yours
###Hide everything outside `:root>body>#bodyAbstractionLayer>#bodyContentHere`
```
 :root > :not( body)        /* 1. */
,:root > :not( body) > *    /* 1. */
,body > :not( #bodyAbstractionLayer)        /* 2. */
,body > :not( #bodyAbstractionLayer) > *    /* 2. */
,#bodyAbstractionLayer > :not( #bodyContentHere)        /* 3. */
,#bodyAbstractionLayer > :not( #bodyContentHere) > *    /* 3. */
{border: 0 solid rgba(255,255,255,0) !important
;bottom: 999999999% !important
;left: 999999999% !important
;margin: 0 !important
;padding: 0 !important
;right: 999999999% !important
;top: 999999999% !important
}   /* 4. */
```
####Captions
1. Select every element inside the `:root` element but `body` and its descendants;
2. Select every element inside `body` but `#bodyAbstractionLayer` and its descendants;
3. Select every element inside `#bodyAbstractionLayer` but `#bodyContentHere`and its descendants.
4. Disfigurate the selected elements.

###And now try using ( !important, non-inline, 10 IDs , 10 classes, 10 elements) CSS specificity plus a full list of disfigurated property values!
```
 html:not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):root:root:root:root:root:root:root:root:root:root:not(a):not(a):not(a):not(a):not(a):not(a):not(a):not(a)>:not(body)
,html:not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):root:root:root:root:root:root:root:root:root:root:not(a):not(a):not(a):not(a):not(a):not(a):not(a):not(a)>:not(body)>*
,html:not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):root:root:root:root:root:root:root:root:root:root:not(a):not(a):not(a):not(a):not(a):not(a):not(a):not(a)>body>:not(#bodyAbstractionLayer)
,html:not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):root:root:root:root:root:root:root:root:root:root:not(a):not(a):not(a):not(a):not(a):not(a):not(a):not(a)>body>:not(#bodyAbstractionLayer)>*
,html:not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):root:root:root:root:root:root:root:root:root:root:not(a):not(a):not(a):not(a):not(a):not(a):not(a):not(a)>body>#bodyAbstractionLayer>:not(#bodyContentHere)
,html:not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):not(#\20):root:root:root:root:root:root:root:root:root:root:not(a):not(a):not(a):not(a):not(a):not(a):not(a):not(a)>body>#bodyAbstractionLayer>:not(#bodyContentHere)>*
{border:0rgba(255,255,255,0)solid!important
;bottom:999%!important
;left:999%!important
;margin:0!important
;padding:0!important
;right:999%!important
;top:999%!important
}
```
###Customize your
```
 #bodyAbstractionLayer
{
;
}
 #bodyContentHere
{
;
}
```
