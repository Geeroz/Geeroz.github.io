---
layout: post
title:  "Jekyll กับการ Embed Video"
date:   2015-02-15 13:25:00
categories: dev
thumbnail: /images/thumb/003.jpg
published: true
tags: [dev,video,responsive]
---

Embed Video กับ Jekyll

**วิธีที่ 1**  
หลายคนคงเคยใช่ [Embed Responsively](http://embedresponsively.com/) เพื่อสร้าง code สำหรับ embed content ใน website กันมาแล้ว

ลองไปที่ [Embed Responsively](http://embedresponsively.com/) แล้วเอา URL ของ video จาก YouTube หรือ Vimeo ไปใส่ดู

    https://vimeo.com/119509577

[Embed Responsively](http://embedresponsively.com/) ก็จะสร้าง Embed code ให้เราแบบนี้


    <style>
    .embed-container { position: relative; padding-bottom: 56.25%; h
    eight: 0; overflow: hidden; max-width: 100%; } .
    embed-container iframe, .embed-container object,
    .embed-container embed { position: absolute; top: 0;
    left: 0; width: 100%; height: 100%; }
    </style>
    <div class='embed-container'>
    <iframe src='http://www.youtube.com/embed/m/119509577'
    frameborder='0' allowfullscreen>
    </iframe></div>

<!--more-->

วิธีข้างบนก็ง่ายดี ถ้าเราไม่ได้ embed อะไรบ่อยๆ แต่ถ้าเราต้อง embed อะไรเป็นประจำ ทุกครั้งที่เราต้องการ embed อะไรใน blog ของเรา เราก็ต้องไปที่ [Embed Responsively](http://embedresponsively.com/) ทุกครั้งเพื่อจะสร้าง embed code เอามาแปะ

ลองมาดูอีกวิธีสำหรับ embed video ลงใน Jekyll Blog ของเรา

**วิธีที่ 2**  
[Jekyll Responsive Embed Converter](http://keyes.ie/jekyll-responsive-embed/)

วิธีการใช้งาน  
ขั้นแรก เราต้อง download Gist จาก link ด้านล่างนี้เสียก่อน  
[ResponsiveEmbedConverter Gist](https://gist.github.com/jkeyes/ff1979ee60f32422de83)

เราจะได้ file มา 3 files

    _vimeo.html
    _youtube.html
    responsive_embed.rb


นำไฟล์ responsive_embed.rb ไปใส่ไว้ใน _plugins (ถ้ายังไม่มี folder นี้ก็สร้างขึ้นมาได้เลย)

อีกสอง file ที่เหลือให้นำไปใส่ไว้ที่ _includes

ลองเอา video ไป embed ใน blog ของเรา  

![Google Cardboard](/images/googlecardboard_embed_code.jpg)


เราก็จะได้ video ที่ embed ใน Jekyll Bolg ของเราแล้ว

<style>.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; } .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }</style><div class='embed-container'><iframe src='https://player.vimeo.com/video/109344494' frameborder='0' webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe></div>

<br>
***Note:*** ดูเหมือนว่า plugin ตัวนี้จะทำงานไม่ถูกต้องถ้า extension ของไฟล์ใน _posts ของเราเป็น .markdown ลองเปลี่ยนเป็น .md แล้วสามารถแก้ปัญหาได้  
***Note:*** เราไม่สามารถใช้ plugin ได้ถ้าเรา host blog ของเรา บน github ... too bad
