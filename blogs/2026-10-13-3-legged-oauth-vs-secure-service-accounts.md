---
title: "3-legged OAuth vs Secure Service Accounts"
url: "https://aps.autodesk.com/blog/3-legged-oauth-vs-secure-service-accounts"
date: "2026-10-13"
author: "adam.nagy"
feed_url: "https://aps.autodesk.com/rss.xml"
---
3-legged OAuth vs Secure Service Accounts adam.nagy 14 Oct 2026 Adam Nagy Share There is a detailed blog post on Secure Service Accounts , but it does not discuss when to use normal 3-legged authentication instead of Secure Service Accounts . As the above picture shows, if you need to do things on behalf of a specific user and the operations take place while the user is running your application, then relying on normal 3-legged authentication is fine. Since the user is in front of your application, even if the token refresh goes wrong, you can ask them to log in again - it should not cause any 
