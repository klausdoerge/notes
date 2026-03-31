Prisen stiger 200,- pr løsning i licens
Umiddelbart ser Migrate ud til at virke fint - flytter også domæner. Mangler en test med rules osv
Tager 20-30 minutter at lave en update og teste

Umbraco
Version 8 kan ikke purge Frontdoor, og den findes i flere versioner
2-3 dage til en opdatering og test, herefter kan vi opdatere alle løsninger


https://portal.azure.com/#@cadpeople.dk/resource/subscriptions/7fcf7e9a-8f5a-4af3-b6f6-2474b60175f5/resourceGroups/virtuel-cadpeople.dk/overview

Testet på https://virtuel.cadpeople.dk/

Todo:
VirtuelCadpeople kører version 1.0.8 som skal kunne purge en frontdoor CDN.
- Fix purge
- Afklaring om version 1..0.9 kunne være en mulig opgradering, eller om det er bedre bare kopiere koden til Frontdoor ind i de forskellige versioner, så der ikke sker ændringer i publiceringen på eksisterende løsnigner


Flow

Prereq:
- Contributer and User-Access Admin permissions on subscript

Umbraco 13.x update
1) Backup solution (umbraco, storage, database)
2) Migrate CDN
3) Update SQL
	1) ALTER TABLE umbracoRedirectUrl WITH NOCHECK  
ADD CONSTRAINT FK_umbracoRedirectUrl_umbracoNode_uniqueID CHECK (contentKey <> '') ;

ALTER TABLE umbracoNode  
DROP CONSTRAINT IX_umbracoNode_UniqueId
1) Fix Umbraco config and upload bin folder
2) Add FrontdoorPurgeFunction permissions - CDN PRofile contributer
3) Delete App Registration when publish by function works