Prisen stiger 200,- pr løsning i licens
Umiddelbart ser Migrate ud til at virke fint - flytter også domæner. Mangler en test med rules osv
Tager 20-30 minutter at lave en update og teste

Pre-todo:
Gennemgå subscriptions liste med Michael og lav afklaring, om der er nogen af løsningerne vi kan springe over, da de måske alligvel skal lukkes ned?

TODO:
	1) Lav opdatering af Umbraco 1.3.1 og test med en løsning som anvender denne version. Om muligt så test med Pressalit, da den alligevel skal lukkes efterfølgende
	2) Når første installation er lavet, skal der laves en plan for opdateringern
		1) Backup af kørende løsning (frontend, Umbraco og SQL)
		2) Opdatering af CDN og test det virker
		3) Opdatering af Umbraco til seneste version med ny purge
		4) Test purge virker i staging
	3) 

Umbraco
Version 8 kan ikke purge Frontdoor, og den findes i flere versioner
2-3 dage til en opdatering og test, herefter kan vi opdatere alle løsninger

https://portal.azure.com/#@cadpeople.dk/resource/subscriptions/7fcf7e9a-8f5a-4af3-b6f6-2474b60175f5/resourceGroups/virtuel-cadpeople.dk/overview

Testet på https://virtuel.cadpeople.dk/

Status
- Det er ikke muligt at bygge v1.0.8 eller 1.0.9 længere, selvom der ikke foretages ændringer. Det er uklart hvad der går galt - måske Dominique har en idé
- Test med implementering i Umbraco v1.3.1 (performance test) om det lykkes der. Det virker fint med AVK og den nye Azure Function.
- Opdater Azure-Function så den er mere sikker (evt). PT anvender den RBAC til at sikre, at den har rettigheder nok til at lave en purge, men måske skal vi beskytte endpoint yderligere, så den i det mindste ikke kan kaldes udefra. 
- 

Todo:
VirtuelCadpeople kører version 1.0.8 som skal kunne purge en frontdoor CDN.
- Fix purge
- Afklaring om version 1..0.9 kunne være en mulig opgradering, eller om det er bedre bare kopiere koden til Frontdoor ind i de forskellige versioner, så der ikke sker ændringer i publiceringen på eksisterende løsnigner


Test
* Test om en purge af 1 domæne også har indflydelse på de andre, så længe der kun er 1 endpoint

Flow

Prereq:
- Contributer and User-Access Admin permissions on subscript

Umbraco 13.x update
1) Backup solution (umbraco, storage, database)
2) Migrate CDN
3) Update SQL

ALTER ROLE db_ddladmin ADD MEMBER [THE_DATABASE_USERNAME];

ALTER TABLE umbracoRedirectUrl WITH NOCHECK  
ADD CONSTRAINT FK_umbracoRedirectUrl_umbracoNode_uniqueID CHECK (contentKey <> '') ;

ALTER TABLE umbracoNode  
DROP CONSTRAINT IX_umbracoNode_UniqueId


1) Fix Umbraco config and upload bin, app_plugins, config  folder
	1) Check if mime-types need updates as well
2) Add FrontdoorPurgeFunction permissions - CDN Endpoint Contributor &   
CDN Profile Contributor on cdn
	
3) restart  umbraco to refresh credentials
4) Test publish function
5) Delete App Registration when publish by function works