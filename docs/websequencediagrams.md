# Happy flow

```websequencediagrams
title Building Premit Happy flow
Actor Citizen as C
Actor Application as S
Actor Workflow BB as O
Actor Information Mediator as IM
Actor Digital registries as Registry
Actor Identity BB as ID
Actor Consent BB as Consent
Actor Messaging BB as M
Actor GIS BB as Geo
Actor Payment BB as Pay
Opt: Start using system
# Citizen wants to applie for building premit
C->S: Go to Log-in page in Portal
S->O: Citizen ends at log-in page
O->ID: Orcestrator start flow management
ID->S: ID BB sends request to enter credentials
C->S: Citizen enter credentials
S->ID:Application sends credential to be confirmed
ID->S:Credentials approved
S->C: System open session for start application
end
Opt:Giving consent
# Citizen gives concent for reusing personal data
C->S:Citizen land at dashboard with option to start choosing....
S->Consent: Citizen is taken to concent
Consent->S:Citizen accepts consent
S->O:Citizen make the joice for start application
O->C:Citizen lands at dashboar for start application
end
Opt:Start applying
#Citizen start entering application
C->S:Citizen chooses application form
S->Geo:Citizen start entering data according to form
Geo->IM:Post request to fetch exsisting data to present it at form
IM->Registry: Fetching  excisting data
Registry->Registry:Bring existing data from different registries
Registry->O:Workflow manage the application steps
O->O:As many circles needed
O->S:Final stage to review full application
O->C:Finishing entering application deactivate
end
Opt:Send/ finish application
#Citizen confirm data and make payment for start process
C->S:Citizen review application and chooses to proceed
S->Pay: Citizen chooses to pay fee
Pay->Pay: G2P payment data will be fetched
Pay->Registry: Payment data saved in payment registry
Registry->O: After payment will be triggered confirmation message
O->M:create message about succesful payment
M->C:Confirmation sent and application is finished
end```