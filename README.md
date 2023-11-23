# gitpod-troubleshooting
Minimal repo to troubleshoot issues with dev environments.

The .gitpod.yml file should install automatically the dnsutils so we just need to run the command: `dig charles.upgradedpoints.tech` and see that sometimes we receive this error. We need to fix this issue. This is not happening for other local environments, only for Gitpod environments.

# Example of error

```
gitpod /workspace/gitpod-troubleshooting (main) $ dig charles.upgradedpoints.tech

; <<>> DiG 9.18.12-0ubuntu0.22.04.3-Ubuntu <<>> charles.upgradedpoints.tech
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: SERVFAIL, id: 2644
;; flags: qr rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; EDE: 22 (No Reachable Authority): (at delegation upgradedpoints.tech.)
;; QUESTION SECTION:
;charles.upgradedpoints.tech.   IN      A

;; Query time: 7 msec
;; SERVER: 1.1.1.1#53(1.1.1.1) (UDP)
;; WHEN: Thu Nov 23 19:16:12 UTC 2023
;; MSG SIZE  rcvd: 96
```

# Example of success

```
gitpod /workspace/gitpod-troubleshooting (main) $ dig charles.upgradedpoints.tech

; <<>> DiG 9.18.12-0ubuntu0.22.04.3-Ubuntu <<>> charles.upgradedpoints.tech
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 6465
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;charles.upgradedpoints.tech.   IN      A

;; ANSWER SECTION:
charles.upgradedpoints.tech. 300 IN     A       104.21.35.155
charles.upgradedpoints.tech. 300 IN     A       172.67.177.3

;; Query time: 15 msec
;; SERVER: 1.1.1.1#53(1.1.1.1) (UDP)
;; WHEN: Thu Nov 23 19:19:27 UTC 2023
;; MSG SIZE  rcvd: 88
```