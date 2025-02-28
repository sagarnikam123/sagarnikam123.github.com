---
layout: post
title: "commands for linux troubleshooting (draft)"
description: "imp commands used during troubleshooting"
category: [linux]
tags: [troubleshooting, commands]
---
{% include JB/setup %}

### Logging

##### simple logging on terminal
```
import logging

logging.basicConfig(format='%(asctime)s %(levelname)-1s: [%(lineno)d] %(message)s',
    datefmt='%Y-%m-%d %H:%M:%S', encoding='utf-8', level=logging.INFO)
logger = logging.getLogger(__name__)
logger.propagate = True

logger.info("Hello World!")
```