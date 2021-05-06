## COMMAND SETUPS FOR CLEARING INGAME CHAT

### Command to Clear Chat for Individual Players. Ex. If you enter `/clearooc`, it will clear only your chat. - To be PASTED in any Client File. 
```
-- Paste this in any Client sided file 

RegisterCommand('clearooc', function(source, args)
    TriggerEvent('chat:clear')
end, false)
```

### Command to Clear Chat for ENTIRE SERVER. Ex. Admin sends `/clearallchat` thus wiping chat for everyone at once. 
```
-- Paste this in any Server Sided FIle
QBCore.Commands.Add("clearallchat", "Full Server Chat Clear", {}, false, function(source, args)
		
	TriggerClientEvent('chat:clear', -1)
	TriggerClientEvent('QBCore:Notify', source, "Cleared Server Chat", "error")
	
end, "admin")
```
