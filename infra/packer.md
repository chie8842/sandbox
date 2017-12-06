# rebootするときのconfigurationの書き方

```json
     "type": "shell",
     "inline": [
         "sudo reboot"
     ],
     "expect_disconnect": "true"
   },
   {
     "type": "shell-local",
     "command": "sleep 120"
   }
```

expect_disconnectを入れる。
rebootのあともprovisionerの実行があるときは、
後続のprovisionerの実行のオプションに、start_retry_timeout（default 5m）値を設定するといいかも。
