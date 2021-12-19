---
id: g5pcjz3ugS7GYb6RkZ9Eo
title: CSS
desc: ''
updated: 1639887278086
created: 1639847566812
---

# Flexbox

## Trick 1

If one element needs to be at the right of the flex container, while other elements in the container are using `justify-content: flex-start`, can set this element `margin-left: auto` to achieve this.

# Animation

## [Twitter like animation](https://codepen.io/chrismabry/pen/ZbjZEj?__cf_chl_jschl_tk__=dfde8d6c259f07cbd7a5354ba065d59103455647-1590141673-0-AQ_F1aBWj7Q4Gvk1MzfzPqJ9OX4lw2CbPBQW3_2iBc8d4M2-rhGO76mtCirt2TpG_aGCNprgzUSr-wj0zaqmJU5EdXy9hWDiPdAiuC8s-QcYSjia0ij_-HMnvSJvfbAa8UhCIO0rhv8RzsJErlsGwAhjXZSYAVS_1mXmRLlxJgj07F1IqellWyMxGM8DahSRfqYjW1FIqfZoa_MBh0_VQ7MqlvEIIqdTN52O5TvJHIX-H__QItXFiSgrB2oBj8cAuALlriBjkmIvDvONT3bmc2jBzitc11gpmo-BWtfDwcEgumF8jGi_dw6c4FYSSY59GUR3lTd4vosc6u_YB5de2CerskQ0_oW9rsVwN2VulOvx)

## Parallax scroll implementations

1. AOS
2. Ant motion
3. Scrollmagic and gsap

# CSS attributes

## A new CSS attributes `aspect-ratio`, supported by Chrome from version 88, 2021

https://web.dev/aspect-ratio/ google 关于这个属性的 blog，从 chrome88 开始支持，所以目前应该不算支持很好，过一两年再用比较保险。  
这个属性的来源一切要从图片长宽比说起。加载一个图片，要在 html 里面规定长和宽，如果没有规定的话，加载之前没有长和宽，加载完了之后会把下面的文字内容挤下去，这种现象叫做 cumulative layout shift。那我们只要规定长宽就好了吗？没那么简单。  
很多时候我们还需要做响应式支持，图片的宽度会变小，但高度不变。还有的时候我们需要保持长宽比不变。aspect-ratio 这个属性就是用来保证长宽比不变的。  
先说之前的跨浏览器解决方案是使用 padding-top 或 padding-bottom，这两个属性的百分比单位的值是相对于自身宽度来说的，所以很适合拿来搞长宽比。通常的方案就是外面 div container padding-top 规定长宽比，它的里面有一个绝对定位的图片。用 padding 不太好的地方就是，padding 它本来不是用来干这件事的，还有 就是还需要计算。以后就可以拿 aspect-ratio 来替换它了。  
这里提一个和图片有关的另外一个属性，就是 object-fit。这个属性规定 replaced element 如何填充它的容器，所谓 replaced element 是指内容不受 CSS 控制的元素，比如<img\> <video\> <iframe\>等。你虽然可以控制他们的 size，position，但里面的内容是无法通过 CSS 来控制的。比如就是 img 里面图像的内容应该怎么填充<img\>这个容器。里面最常用的就是 cover，它将内容最短的边和容器匹配，然后进行 crop。这样可以保证填充满容器，并且内容的长宽比不会变，缺点是会被 crop 掉一部分图片内容。
