```plantuml
skinparam monochrome true

rnote over Sender, Receiver
    nonce = 30
endrnote

Sender -x Receiver: <id> data
Sender -x Receiver: <id+1> HMAC(nonce = 30)

rnote over Sender
    nonce = 31
endrnote

== Receiver deaf ==

Sender -> Receiver: <id> data
Sender -> Receiver: <id+1> HMAC(nonce = 31)

rnote over Receiver
    authentication error
endrnote

...until nonce generation interval reached...

NG -> Sender: nonce = 746
NG -> Receiver: nonce = 746

Sender -> Receiver: <id> data
Sender -> Receiver: <id+1> HMAC(nonce = x)

rnote over Sender, Receiver
    update nonce to 746
endrnote

== resynchronized ==

```