---
title: "Use Fusion Automation API without PAT"
url: "https://aps.autodesk.com/blog/use-fusion-automation-api-without-pat"
date: "2026-07-28"
author: "adam.nagy"
feed_url: "https://aps.autodesk.com/rss.xml"
---
Use Fusion Automation API without PAT adam.nagy 30 Jul 2026 Adam Nagy Share Previously, if you wanted to automate something on another user's behalf, the user needed to create a PAT (Personal Access Token) and provide it for your app. That's how the Fusion Configurator sample used to work too - see https://github.com/autodesk-platform-services/aps-configurator-fusion/tree/ac4096f22cc09ae3e8d3bfd0ccba0f8771d6b052 Now you can achieve the same without a PAT , simply using 2LO (2-legged authentication) when starting a work item, plus 3LO (3-legged authentication) passed in as a work item parameter
