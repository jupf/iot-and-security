```plantuml
skinparam monochrome true

rnote over Sender
update_counters()
endrnote
Sender -> Receiver: counter, data
Sender -> Receiver: counter, MAC
rnote over Receiver
update_counters()
endrnote
rnote over Receiver
Verify MAC
endrnote
```