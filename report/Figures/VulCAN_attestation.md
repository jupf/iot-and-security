```plantuml
skinparam monochrome true
hide footbox
title Load-Time Attestation

rnote over AS
    generate random 
    session keys
endrnote
activate AS

rnote over ECU
    Load and enable PM
endrnote


group for each PM
AS -> ECU: encrypt(moduleKey, sessionKey | nonce)
activate ECU
ECU -> AS: MAC(moduleKey, nonce)
deactivate ECU
end alt

rnote over AS 
    turn on vehicle ignition
endrnote
```