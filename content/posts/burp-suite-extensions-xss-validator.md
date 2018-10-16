---
title: "Burp Extensions - Setting up XSS Validator"
date: 2018-10-15T18:56:18-05:00
draft: true
---

## Hunting for XSS

XSS / Cross-site scripting (which is just another form of [Code Injection](https://en.wikipedia.org/wiki/Code_injection)) can be a severe vulnerability. 

It's also [very common](https://www.info-point-security.com/sites/default/files/cenzic-vulnerability-report-2014.pdf). 

That potent combination  - profitability and ubiquity - marks it as a worthy target for penetration testers interested in collecting on public bounties.

But because of a high rate of false-positives (and inevitably imperfect logic) the process of ferreting out XSS causes a lot of noise. The [XSS Validator from Nvisium](https://blog.nvisium.com/2014/01/accurate-xss-detection-with-burpsuite.html) is designed to solve this problem. It verifies XSS findings exported from the [Burp Suite](http://phantomjs.org/) interface in a node server designed to receive, analyze, and pass back possible XSS snippets. The extension is critical for testing a target with a large attack surface.

## Installing XSS Validator

The easiest way to download the XSS Validator plugin is to install it via the Bapp Store - Burp's version of Google Play or the Apple App Store - by navigating to the "Extender" tab and then the "Bapp Store" submenu.

![Bapp Store](images/bapp-store-xss-val.png)

If you're having an issue installing straight from the store, you can also perform a manual install by downloading the extension's `jar` file from either its github or product page and selecting it from the "Manual Install" file uploader.

![Bapp Store Manual Install](images/bapp-sore-manual-install.png)

