---
title: মার্কডাউন ওয়েবসাইট
header: মার্কডাউন ওয়েবসাইট 
description: খুবই সাধারণ আর সরল ভাবে এটা ডিজাইন করা।কোন রকম জাভাস্ক্রিপ্ট আর থিম ছাড়াই।
permalink: contents/markdown
layout: default
---
এটা বানাতে আমি শুধু _congif.yml, _layout আর  css এই তিনটি directory ব্যবহার করছি। খুবই সাধারন তবে অনেক হাই পারফরম্যান্সড ওয়েবসাইট।

# প্রথম ধাপ (কনফিগারেশন)
শুরুতে একটি `_config.yml` ফাইল বানাইছি। এখানে তেমন কিছুই করি নাই শুধু এক লাইনে আমার ওয়েবসাইটের এড্রেসটি লিখছি।
```
url: "https://sohelkhan.rbind.io"

```
# দ্বিতীয় ধাপ (লেআউট)
যেহেতু আমি প্রতিটি ক্ষেত্রেই এইচটিএমএল এর পরিবর্তে মার্কডাউন ব্যবহার করবো  তাই  আমাকে বেশ কয়েকটি কাজ করতে হবে যাতে আমাকে একি জিনিস বার বার না লিখা লাগে । প্রথমত মার্কডাউনটি যেহেতু এইচটিএমএল এ কনভার্ট হবে তাই এইচটিএমএল এর একটি ডিফাল্ট পেইজ লেআউট তৈরি করলে সকল পেজে এই লেআউট আকারেই বের হবে। আমি সেজন্য _layouts নামে একটি  ফোল্ডার তৈরি করি এবপর সেখানে  default.html নামের একটিএইচটিএমএল ফাইল তৈরি করি।
```
<!doctype html>
```
## এইচটিএমএল এ বাংলা ভাষা যোগ
```
<html lang="bn">

```
হেডে UTF-8 character সেট 
```
<head>
    <meta charset="utf-8">
```    
সার্চ থিম কালার পরিবর্তন
```
    <meta name="theme-color" content="#778899">
```
ডিভাইসের স্ক্রীন সাইজ অনুসারে রেন্ডার
```
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```
## ফেভিকন সেট
এসেটস্ ফোল্টারে ইমেজেস সাবফোল্ডার করে ৫১২ বর্গ পিক্সেলের ফেভিকন পিএনজি আপলোড করছি। 
```
    <link rel="icon" href="/assets/images/favicon.png" />
```
## পেইজ টাইটেল ও বিবরন
```
    <title>{{ page.title }}</title>
    <meta name="description" content="{{ page.description }}" />
 ```   
 এসেটস্ এ সিএসএস ফোল্ডারে স্টাইল.সিএসএস এম্পটি রেখে এখানে লিংক যোগ করছি। 
 ```   
    <link rel="stylesheet" href="/assets/css/style.css" />

  </head>
 ```
## বডি হেডার
 ```
 <header>
      <h1>
         <a href="/">হোম</a>
         <a href="/প্রবন্ধ/পরিচিতি">পরিচিতি</a>
         <a href="/প্রবন্ধ/যোগাযোগ">যোগাযোগ</a>
         <a href="/প্রবন্ধ/মার্কডাউন">প্রবন্ধ</a></h1>
         <h1>{{ page.header }}</h1>
         <p>{{ page.description }}</p>
    </header>
```
মেইনে শুধু content এড করছি।

## ফুটার

```    
    <footer>
      <p>সোহেল খান©২০২১</p>
    </footer>
```
# তৃতীয় ধাপ (সিএসএস সেটাপ)

খুবই অল্প পরিসরে যেগুলি খুবই গুরুত্বপূর্ণ সেগুলিই শুধু ডিজাইন করছি।

```
html {
  font-size: 20px;
}
```
## বডি কাস্টমাইজ
```
body {
  color: #000;
  background: #fff;
  font-size: 1.15rem;
  line-height: 1.618;
  display: flex;
  min-height: 100vh;
  flex-direction: column;
  flex: 1;
  margin: 0 auto;
  max-width: 45rem;
  padding: 0 .5rem;
  overflow-x: hidden;
	word-break: break-word;
	overflow-wrap: break-word;
}
```
## হেডার ও ফুটার কাস্টমাইজ
``` 
header,footer {
  font-size: .9rem;
  text-align: center;
  background: #778899;
  width: 100%;
}
```
## টেক্সএরিয়া কাস্টমাইজ
```

textarea {
  width: 80%
}
```
## মোবাইল স্ক্রিন কাস্টমাইজ
```
@media only screen and (max-width: 720px) {
  textarea,
  select,
  input {
    width: 100%;
  }
}

```
## হেডিং কাস্টমাইজ
```
h1, h2 {
	clear: both;
  font-weight: bold;
}

h1 {
	font-size: 2em;
        color: green;
}

h2 {
	font-size: 1.8em;
        margin-top: 2em;
           color: #778899;
}


```

```
i.hash {
  font-size: 0.8em;
  color: blue;
}
```
## ব্লককোট কাস্টমাইজ
```
blockquote {
    margin-left: 2em;
    margin-bottom: 2rem;
    margin-top: 2rem;
    padding: .4rem .8rem;
    border-left: .35rem solid green;
    color: red;
    font-style: italic;
}

```
## কোড কাস্টমাইজ
```
pre {
        overflow: auto; 
	padding: 20px;
	overflow: auto;
	max-height: 300px;
	font-size: 14px;
	background: #000;
	color: #fff;
}
```
ব্যাস সাইটির ফ্রেম পুরাপুরি কমপ্লিট। এখন শুধু মার্কডাউন এড করলেই সাইটটি এভাবে শো করবে।
# চতুর্থ ধাপ(মার্কডাউন ফাইল)
ইনডেক্স মার্কডাউন ফাইল তৈরি করে টাইটেল, হেডার,বর্ননা, পারমালিংক, লেআউট ডিফল্ট করলে কমপ্লিট
```
---
tytle:
header:
description:
permalink:
layout:
---
```
এরপর লোকাল রিপুটা গিটহাবে পুশ করছি।তারপর ডোমেইন ইউআরএল সেট করছি। ব্যাস ওয়েবসাইট হয়ে গেল।
