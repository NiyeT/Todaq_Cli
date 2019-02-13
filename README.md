# Todaq_Cli
Todaq command line interface

# Usage


## Create Account
###### sample input (takes object as string)
  todaq  -createAccount  '{"email":"youremail@gmail.com","first-name":"john","last-name":"doe"}'
###### sample output (returns user id as string)
  6f859919-e4a3-4fee-8b9b-90e08c941c8b
  
## Get Account Info
###### sample input (takes user id)
  todaq  -getAccount  6f859919-e4a3-4fee-8b9b-90e08c941c8b
###### sample output (returns object containing user data)
  {"data":{"type":"account","id":"6f859919-e4a3-4fee-8b9b-90e08c941c8b","attributes":{"contact":{"email":"fds@fds.com","last-     name":"fds","first-name":"other"},"is-active":true,"admin-email":"fds@fds.com","account-type":"individual","enterprise-        id":"f75af6ca-3c9f-4485-87b9-03652787ada7"}},"meta":{"total-results":1}}

## Create Item
###### sample input (takes user id and object)
  todaq  -createItem  6f859919-e4a3-4fee-8b9b-90e08c941c8b  -id  '{"brand":"BigCosctco","serialNumber":"unique-id123"}'
###### sample output (returns item id as string)
  d4cb5630007dbd25ea73723ae2831b65a032020ece3aef419fa523858ea60d75
 
## List an Accounts Items
###### sample input (takes user id as string)
  todaq  -listItems  6f859919-e4a3-4fee-8b9b-90e08c941c8b
###### sample output (returns object with array of items owned by user)
  {"data":[{"type":"file","id":"d4cb5630007dbd25ea73723ae2831b65a032020ece3aef419fa523858ea60d75","attributes":{"payload":   {"brand":"costco","serial":"fds"}...
  
## Exchange an Item
###### sample input (takes item id, user id to send from, and user id to send to)
  todaq  -exchange  d4cb5630007dbd25ea73723ae2831b65a032020ece3aef419fa523858ea60d75  -from  6f859919-e4a3-4fee-8b9b-90e08c941c8b  to  -to  40e343d2-c7b0-4110-86ab-71d0218576ab
###### sample output (returns a transaction id)
  44c247c5-ef1b-43d4-89a8-0b5769f1f848
