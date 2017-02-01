# digdag-slack

[![Release](https://jitpack.io/v/bwtakacy/digdag-slack.svg)]
(https://jitpack.io/bwtakacy/digdag-slack)

[![Build Status](https://travis-ci.org/bwtakacy/digdag-slack.svg?branch=master)](https://travis-ci.org/bwtakacy/digdag-slack)

## How to use

### file tree
```
.
├── digdag-slack          <-- This project release file
├── message.txt
└── hello_world.dig
```

### Create File 

[hello_world.dig]
```
_export:
  plugin:
    repositories:
      - file://${repository_path}
      # - https://jitpack.io
    dependencies:
      - jp.techium.blog:digdag-slack:0.1.2
      # - com.github.bwtakacy:digdag-slack:0.1.2

+step1:
  slack>: message.txt
  webhook: https://hooks.slack.com/services/XXXXXXXX/XXXXXXXXX/XXXXXXXXXXXXXXXXXXXXXX      # <-- Slack Incoming WebHooks url
  channel: general
  username: webhookbot
  icon_emoji: ghost
```

This plugin should be taken by local file path or JitPack over HTTPS.

[message.txt]
```
hello world!
```

### Run

```
$ digdag r hello_world.dig -p repository_path=/path/to/workspace/digdag-slack
```

