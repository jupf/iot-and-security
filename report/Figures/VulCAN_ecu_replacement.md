```plantuml
skinparam monochrome true
hide footbox
title ECU integration

rnote over ECU
    ECU contains unique
    replacement identifier: IDr
endrnote
activate ECU

ECU -> AS: IDr
AS -> Vendor: cert(PK_AS) | IDr
activate Vendor

rnote over Vendor
    look up IDr and 
    mark as used
endrnote

Vendor -> AS: encrypt(PK_AS, IDr | moduleKey)
deactivate Vendor

ref over AS: load-time attestation

activate AS






```