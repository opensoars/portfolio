---
layout: post
title:  "ytmp3dl-core"
date:   2016-10-19 20:27:31 +0200
categories: projects
oneline: Reverse engineered Google's media signature enciphering. Ytmp3dl is an asynchronous power Node.js Youtube mp3 downloader module utilizing some of the latest (proposed) ECMAScript features.
---

Async YouTube power mp3 downloader. Utilizing ES6 and ES7 features.

[![Build Status](https://travis-ci.org/opensoars/ytmp3dl-core.svg?branch=master)](https://travis-ci.org/opensoars/ytmp3dl-core)

<!---
[![Coverage Status](https://coveralls.io/repos/opensoars/ytmp3dl-core/badge.svg?branch=master&service=github)](https://coveralls.io/github/opensoars/ytmp3dl-core?branch=master)
[![Inline docs](http://inch-ci.org/github/opensoars/ytmp3dl-core.svg?branch=master)](http://inch-ci.org/github/opensoars/ytmp3dl-core)
[![Codacy Badge](https://api.codacy.com/project/badge/f3e64501763645b9aa483bf83a4dd1d5)](https://www.codacy.com/app/sam_1700/ytmp3dl-core)
[![Code Climate](https://codeclimate.com/github/opensoars/ytmp3dl-core/badges/gpa.svg)](https://codeclimate.com/github/opensoars/ytmp3dl-core)
[![Dependency Status](https://david-dm.org/opensoars/ytmp3dl-core.svg)](https://david-dm.org/opensoars/ytmp3dl-core)
[![devDependency Status](https://david-dm.org/opensoars/ytmp3dl-core/dev-status.svg)](https://david-dm.org/opensoars/ytmp3dl-core#info=devDependencies)
-->

---

# Install

`npm install ytmp3dl-core`


# Use

{% highlight javascript %}
new (require('ytmp3dl-core').Download)({ v: 'NnTg4vzli5s' })
  .on('callMethod', method => console.log(`callMethod: ${method}`))
  .on('stream-progress', prog => console.log('stream-progress', prog))
  .on('conversion-progress', prog => console.log('conversion-progress', prog))
  .on('error', err => console.log('error', err))
  .on('succes', result => console.log('succes', result))
  .callMethod('start'); 
{% endhighlight %}
