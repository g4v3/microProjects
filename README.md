---
[µProjects](http://github.com/g4v3/microProjects)/[bodyAbstractionLayer](http://github.com/g4v3/microProjects/tree/bodyAbstractionLayer)
---
##Instead of `<frame>` or `<iframe>`
This model can be used to put previously prepared pages inside each other without need for `<frame>`s or `<iframe>`s.
##As a `<body>` sandbox
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
###_Bonus:_ Hide ALL elements outside `:root>body>#bodyAbstractionLayer>#bodyContentHere`
```
 :root > :not( body)        /* 1. */
,:root > :not( body) > *    /* 1. */
,body > :not( #bodyAbstractionLayer)        /* 2. */
,body > :not( #bodyAbstractionLayer) > *    /* 2. */
,#bodyAbstractionLayer > :not( #bodyContentHere)        /* 3. */
,#bodyAbstractionLayer > :not( #bodyContentHere) > *    /* 3. */
{:!important
;:!important
}
```
####Captions
Select every element inside:

1. the `:root` element but `body` and its descendants;
2. `body` but `#bodyAbstractionLayer` and its descendants;
3. `#bodyAbstractionLayer` but `#bodyContentHere`and its descendants.
