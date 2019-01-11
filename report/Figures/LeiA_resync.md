```plantuml
skinparam monochrome true

Sender <- Receiver: AUTH_FAIL
rnote over Sender
update_counters()
endrnote

Sender -> Receiver: counter_s, epoch_s
Sender -> Receiver: counter_s, MAC
rnote over Receiver
check epoch_s||counter_s > epoch_r||counter_r
endrnote

rnote over Receiver
Verify MAC of epoch_si
endrnote

rnote over Receiver
update epoch and counter
calculate new session key
endrnote

```