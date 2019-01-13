```plantuml
skinparam monochrome true


Sender -> Receiver: <id> data

rnote over Sender, Receiver
    calculate HMAC in parallel
endrnote

Sender -> Receiver: <id+1> HMAC

rnote over Receiver
    compare calculated HMACs
endrnote

```