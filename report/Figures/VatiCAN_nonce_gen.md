```plantuml
skinparam monochrome true

rnote over Sender, Receiver
    nonce = 30
endrnote

NG -> Sender: nonce = 746
NG -> Receiver: nonce = 746

Sender -> Receiver: <id> data
Sender -> Receiver: <id+1> HMAC(nonce = 30)

rnote over Sender, Receiver
    update nonce to 746
endrnote

```