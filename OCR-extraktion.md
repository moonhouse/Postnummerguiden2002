OCR-extraktion
--------------

Ett sätt att få ut datat utan reverse-engineering av databasen är att köra programmet och sedan läsa av innehållet på skärmen. För att slippa skrolla manuellt behöver man automatisera processen något.

I en första ansats tänkte jag köra programmet under Windows-emulatorn [Wine](https://www.winehq.org/) men att få programmet att köra utan att Wine klagade på 

```
wine: Unhandled exception 0x0eedfade in thread 9 at address 0x7b4446ea:0x7b427499 (thread 0009), starting debugger...
0009:err:seh:start_debugger Couldn't start debugger
```
visade sig vara svårt. En senare version av Postnummerguiden (2007) [omnämns i WineHQ:s lista över program](https://appdb.winehq.org/objectManager.php?sClass=application&iId=6512) och [ska fungera enligt två rapporter](https://appdb.winehq.org/objectManager.php?sClass=version&iId=10485). Av bilden att döma är den versionen väsentligt annorlunda (och omfattas ändå av katalogskydd fortfarande).

Därför fick alternativet bli att starta sin gamla iMac med Bootcamp och Windows 7.

Med [Autohotkey](https://autohotkey.com/) kan man skriva skript som körs automatiskt vid en knapptryckning. Den stöder att skicka knapptryckningar, anropa andra program och loopar vilket räcker för att (i pseudokod):

 * Skapa en ny katalog (på en ansluten USB-sticka)
 * Loopa följande steg säg 2000 gånger
   * Ta en skärmbild genom att anropa ett program som kan spara aktivt fönster som en bildfil
   * Trycka [Page down]
   * Vänta någon sekund
 * Visa ett meddelande om att skriptet körts färdigt
 
 Ett program som kan skapa en bildfil av det aktiva fönstret är [Irfanview](https://www.irfanview.com/).
 
 Väntetiden efter tangenttryckningen är för att kompensera för det faktum att programmet ibland är lite slött på att fylla vyn med nästa sida med postnummer. Exakt hur lång tid som man behöver vänta får man testa sig fram till. Det kommer nog behövas ett steg som analyserar de skapade skärmbilderna och upptäcker dubbletter.
 
 Fel som kan inträffa är att något annat program helt plötsligt tar fokus och man har hundra bilder på en dialogruta från Chrome.
 
 Hur många gånger man ska loopa är inte lätt att avgöra. Jag valde att loopa 2000 gånger och avgöra hur långt skrollisten tagit sig ner och köra några gånger till. Ett alternativ är att ta till rejält i överkant och sedan leta sig fram bland de skapade bilderna till var man nått slutet och radera bilderna som togs efter det.
 
 Efterprocessningssteget blir att köra OCR på de skapade bilderna. Med tanke på att det är pixelperfekta bilder tagna där samma bokstav alltid ser likadan ut är det lite overkill att använda vanlig OCR men det blir antagligen det snabbaste sättet (även om det [kan kräva lite förbehandling av bilderna](https://stackoverflow.com/questions/4209284/best-way-to-recognize-characters-in-screenshot)). De olika datapunkterna ligger i varsin kolumn så det kommer behövas viss logik för att separera de delarna.
