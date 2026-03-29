+++
date = '2026-03-29T00:00:00+01:00'
draft = false
title = 'Java Design: علاش Interfaces أحسن من Abstract Classes؟'
tags = ["Java", "Interfaces", "Abstract Classes", "OOP", "Design Patterns"]
categories = ["blog"]

[cover] 
    image = "Interfaces vs Abstract Classes comparison.png"
    relative = true
+++
----------------------------------------------------------
<div dir="ltr">

3lach khasna nfdlou interfaces 3la abstract classes f Java 7it kay3tiw wahed flexibility kbira f design dyal applications. F Java kayn single inheritance, yani class t9der textend ghir abstract class wa7da, walakin t9der timplementi bzaf dyal interfaces f nafs lwa9t. Hadi katkhlli interfaces ahsan bach nbniw systems scalable w flexible.

Interfaces kaykhlou lina nzido behavior l classes bla ma nbddlou hierarchy dyalhom. Hada kaytsamma mixin, b7al Comparable li kaykhli objects ykounou comparable. Abstract classes ma y9drouch idirou hadchi 7it khas ykounou parent direct, w hadchi kay9yed design w kaydirou rigid.

Zid 3la hadchi, interfaces sahlin bach nimplementiwhom 3la classes 9damin (legacy code). Ghir katzid implements w katktb methods li khasin . B l3aks, abstract classes s3ib tdkhlhom ila makanchou mn lwl f design dyal project.

Mn ba3d Java 8, interfaces wllaw fihom default methods, yani t9der tktb implementation direct f interface. Hadi katna9s duplication w katsahl 3la developers lkhadma. Walakin kaynin restrictions: ma t9derch tdir default methods dyal equals, hashCode, w toString, w ma kaynach instance fields.

Bach njm3ou bin interfaces w abstract classes, kayn wahed pattern smitou skeletal implementation. Fih katdir interface bach tحدد contract, w mn b3d abstract class katimplementih w kat3ti implementation joz2iya. Developer ghir kaykmmel primitive methods w lb9i kaykoun wajd. Hada kaytsamma Template Method Pattern.

Ila ma9drtich t-extend abstract class (7it kayn inheritance akhor), t9der tst3ml composition, li kattsamma simulated multiple inheritance. Kat7et object west class dyalek w katstafed mn logic dyalo bla ma t7taj inheritance.

kholasa : interfaces homa a7san option bach tdefini types 7it kay3tiw flexibility, reusability, w scalability. Abstract classes khashom ytst3mlou ghir bach y3awnou f implementation, khasatan m3a skeletal implementation bach tsahl lkhadma bla ma tse3eb design dyalek.

source : item 20 - Effective Java 3rd Edition - Joshua Bloch

</div>
