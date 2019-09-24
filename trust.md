# Fællesoffentlig referencearkitektur for brugerstyring
Brugere fuldmagter, delegering, rettigheder og adgangskontrol

# I Referencearkitektur

## 1. Indledning

### 1.1 Formål og scope
Denne referencearkitektur er udarbejdet i sammenhæng med den fællesoffentlige
strategi for brugerstyring og for at understøtte implementeringen af Den fællesoffentlige digitaliseringsstrategi 2016-2020. Målet er, at referencearkitekturen skal
fungere som et teknisk pejlemærke for udvikling af brugerstyringsløsninger generelt i den offentlige sektor. Dermed har den en tæt relation til den fællesoffentlige
rammearkitektur affødt af Digitaliseringsstrategiens initiativ 8.1, som indtil videre
er kommet til udtryk i ”En digitalt sammenhængende offentlig sektor: Hvidbog
om arkitektur for digitalisering”.

Den fællesoffentlige referencearkitektur for brugerstyring skal målrette, strukturere og prioritere indsatsen for at skabe sammenhængende, effektive, sikre og
brugervenlige løsninger på tværs af domæner, nationalt og transnationalt. Fokus
er således på det tværgående, dvs. adgang til tjenester på tværs af organisationer,
herunder føderering på tværs af sikkerhedsdomæner med gensidig tillid via trust
frameworks. Brugeren i brugerstyring er en entitet, der kan være en person, en
organisation, en ting, et system eller en tjeneste.

Scope for strategi og referencearkitektur for brugerstyring er offentlige tjenesteudbydere, men referencearkitekturen kan også anvendes af private. Fokus er på
brugerstyring i forhold til offentlige tjenester – herunder adgang på tværs for
såvel borgere som offentlige og private brugerorganisationer.

Scope omfatter også rollen som leverandør af brugerstyringstjenester (registreringstjenester, akkreditivtjenester, autentifikationstjenester, identitetsbrokere,
attributtjenester mv.) i forhold til offentlige tjenester med både offentlige og private leverandører. Det omfatter desuden private virksomheders mulighed for at
anvende bruger- og rolledata og login-systemer.

Scope omfatter både brugeradministration og adgangskontrol, herunder det der
på engelsk betegnes Credential and Identity Management (CIM), Identity Rights
Management (IRM), Access Control (AC) og Identity and Access Management
(IAM/IdAM).

Den foreliggende udgave af referencearkitekturen for brugerstyring behandler
ikke de særlige aspekter ved ting, tjenester og systemer, og dermed er NonPerson Entities (NPE) ikke i scope for nuværende udgave.

Parallelt med arbejdet på referencearkitekturen er der igangsat analyser af hhv.
fuldmagt og samtykke, med henblik på at afdække behov og muligheder inden
for disse områder. Dermed er disse heller ikke i scope for nærværende udgave af
referencearkitekturen.

Referencearkitekturens formål er at skabe en arkitekturmæssig ramme for, hvordan man skal indrette løsninger, så systemer understøttet af en sikkerhedsløsning
kan kommunikere med systemer og tjenester understøttet af en anden sikkerhedsløsning. Herved bliver interoperabilitet lettere at etablere og drive, så brugerne undgår at skulle logge på flere gange, og så oplysninger om brugere ikke
skal vedligeholdes flere steder.

### 1.2 Resumé

De senere års udvikling på brugerstyringsområdet har medført, at der er etableret
en række løsninger i samarbejde mellem interessenter. Disse løsninger sikrer
sammenhæng inden for afgrænsede delområder, men der findes ikke en overordnet sammenhæng i initiativer og løsninger.

Situationen er i dag præget af, at der er flere forholdsvis ukoordinerede løsninger
(NemID/NemLog-in, SOSI-STS på sundhedsområdet, KOMBITs brugerstyring, WAYF på undervisningsområdet, Miljøportalen m.fl.). Der findes ikke den
sammenhængende tværoffentlige strategi og governance, der i stigende grad efterlyses fra flere sektorer. Der er overlap, sub-optimering og dublering af løsninger med økonomiske konsekvenser. Der er stor usikkerhed hos myndigheder i
forbindelse med it-investeringer – særligt i forbindelse med udbud, hvor der er
brug for at kravspecificere løsninger, der skal kunne holde fem til seks år. Her er
der behov for at kende retningen, man skal orientere sig imod.

Formålet med referencearkitekturen er således at skabe **rammer** for brugerstyring og dermed skabe grundlag for, at parterne kan udvikle brugerstyring på
tværs.

Brugerstyring dækker opgaver og funktioner i forbindelse med håndtering af
brugere i forhold til digitale løsninger, som kan opdeles i administrative funktioner og adgangskontrol. De administrative funktioner omfatter oprettelse, ændring og nedlæggelse af brugere i brugerstyringssystemer, tilknytning af akkreditiver til brugere og tilknytning af rettigheder til brugere.

Hovedaktiviteterne i **administration i brugerstyring (adm., brugeradm.)** er
følgende:
- **Registrering** af entiteters elektroniske identiteter (eID) og den løbende vedligeholdelse heraf.
- **Akkreditivtilknytning** af akkreditiver til et eller flere eID og den løbende
vedligeholdelse heraf. Akkreditivet anvendes af entiteten til at bevise sin identitet over for en tjeneste, man vil have adgang til.
- **Attributbeskrivelse** af karakteristika ved entiteten, som en tjeneste kræver
for at give adgang, og den løbende vedligeholdelse heraf. Det er fx rettighedsrelevante attributter i form af roller og/eller andre attributter, der udtrykker kvaliteter ved entiteten, som en tjeneste forlanger at kende for at give
adgang.

Hovedaktiviteterne i **anvendelse af brugerstyring (anv.)** er følgende:
- **Autentifikation** af entiteten, der ønsker adgang til tjenester, dvs. validering
af entitetens identitet på grundlag af de fremviste akkreditiver.
- **Billetudstedelse,** der på grundlag af den autentificerede eID udsteder en
adgangsbillet (eng: Security Token) med det sæt attributter, som tjenesten
kræver for at give adgang. I denne proces kan der ske en veldefineret og entydig omveksling mellem tekniske formater for akkreditiver eller attributter,
således at tjenesten er i stand til at læse adgangsbilletten. Har entiteten ikke
fået tildelt de nødvendige beskrivende attributter i det rette format, vil entiteten ikke opnå adgang hos tjenesten.
- **Adgangskontrol,** som er håndhævelse af en tjenestes adgangspolitik. Det
styrer, hvilke handlinger entiteten må udføre på en tjeneste, eller hvilke informationer entiteten må få adgang til på grundlag af den adgangsbillet, entiteten møder op med.

Har en brugeradministration udstyret en entitet med det akkreditiv og den attributbeskrivelse, en tjeneste kræver, vil anvendelse af brugerstyring give adgang til
tjenestens ressourcer, typisk i form af funktioner eller informationer i itsystemer.

Referencearkitekturen for brugerstyring fastlægger en række principper for at
styre frem mod en fælles forretnings- og it-arkitektur for det offentliges elektroniske identiteter, akkreditiver, attributbeskrivelser, autentifikation, billetudstedelse og adgangskontrol:

#### Principper
*Principper med brugerfokus:*
1. Brugerne oplever en sammenhængende adgangsstyring
2. Brugerstyringsløsninger udvikles med fokus på brugernes behov
3. Brugerstyringsløsninger respekterer brugernes privatliv
Principper med teknisk fokus:
4. Aktører indgår i føderationer baseret på tillid
5. Aktører i føderationer vurderer i deres styring af informationssikkerhed
samspillet med andre aktører
6. Administration af brugere flyttes så vidt muligt ud af fagapplikationer
7. Tjenesteudbyder (den dataansvarlige) har ansvaret for at håndhæve brugernes adgange
*Principper med udviklingsfokus*
8. Brugerstyring realiseres i løst koblede komponenter
9. Tværoffentlige brugerstyringsløsninger baseres på en kerne af fælles komponenter i samspil med øvrige komponenter i infrastrukturen
10. Tværoffentlig brugerstyring etableres i overensstemmelse med internationale standarder og løsninger

Forretningsbehov og ovenstående principper peger entydigt frem mod en løst
koblet, fødereret arkitektur, hvor de enkelte tjenester/tjenesteudbydere håndhæver adgang baseret på forudgående (ekstern) autentifikation og således ikke selv
håndterer administration af brugere, anvendersystemer og rettigheder.

Der er derfor valgt en token-baseret model for adgangsstyring. Denne indebærer,
at brugere og systemer efter autentifikation får udstedt en adgangsbillet, et såkaldt Security Token, af en betroet komponent i infrastrukturen. Adgangsbilletten præsenteres herefter over for den tjeneste, som leverer data eller funktionalitet, der ønskes adgang til. En adgangsbillet indeholder information om brugerens
eller en tjenestekonsuments identitet, om brugerens karakteristika i form af attributter samt tildelte adgangsrettigheder. Den kan desuden være digitalt signeret af
den betroede udsteder, så den ikke kan forfalskes eller manipuleres.

Digitalisering kræver informationssikkerhed, og brugerstyring er et af midlerne til
at sikre det valgte niveau af informationssikkerhed. Deraf følger, at det er en
forudsætning, at brugerstyring har et tilstrækkeligt højt sikkerhedsniveau både for
de enkelte komponenter i brugerstyring og for de samlede brugerstyringsløsninger.

I referencearkitekturen fastlægges en række standarder for registrering af brugere,
akkreditiver og attributter. Der er behov for standarder for overførsel af data om
autentificerede brugere mellem autentifikationstjenester, login-tjenester/brokere
og tjenester. Der er behov for standarder i forbindelse med rettighedsrelevante
attributter, og der er behov for standarder for kommunikation mellem føderationer. Dette behandles i afsnit 9.6.1.

### 1.3 Hvad er en referencearkitektur
En referencearkitektur giver både myndigheder og virksomheder fælles pejlemærker for fremadrettet udvikling i forbindelse med videreudvikling og nyanskaffelser. Med denne referencearkitektur gælder det for både virksomheder og
myndigheder i deres forskellige roller:
- som brugerorganisationer og arbejdsgivere
- som tjenesteudbydere og udbydere af brugerstyringstjenester.

En referencearkitektur er en fælles referenceramme for den måde, der bygges
løsninger på inden for et specifikt område. Den beskriver de forretningsmæssige
visioner og mål, og den fastlægger principper og begreber. Den beskriver, hvordan man kan realisere de egenskaber, som der er behov for både på forretningsniveau og på teknisk niveau.

En referencearkitektur er en beskrivelse på konceptuelt og logisk niveau. Referencearkitekturen for brugerstyring er styrende for arbejdet med tværoffentlig
brugerstyring og kan ligeledes være vejledende for arbejdet med brugerstyring i
sektorer, myndigheder og virksomheder. Dette er specificeret gennem anvendelse af termerne SKAL, BØR, KAN, hvis betydning er fastlagt i afsnit 1.3.1.

#### 1.3.1 Referencearkitekturen er både vejledende og regelsættende
Referencearkitekturen er som fælles referenceramme styrende for arbejdet med
tværoffentlig brugerstyring og kan ligeledes være vejledende for arbejdet med
brugerstyring i sektorer, myndigheder og virksomheder.

På nogle områder indeholder referencearkitekturen krav og anbefalinger:
- Afsnit angivet med “SKAL” er krav, som skal efterkommes af offentlige
myndigheder i Danmark.
- Afsnit angivet med “BØR” er anbefalinger, som bør efterkommes af offentlige myndigheder, men der er ikke krav om det. Efterkommer man det ikke,
SKAL man give en begrundelse for ikke at gøre det ud fra et ”følg eller forklar”-princip.
- Afsnit angivet med ”KAN” er vejledende, som myndighederne kan efterkomme efter behov.

Referencearkitekturens krav og anbefalinger gælder, når der er tale om nyudvikling eller større ændringer. Der kan være andre regelsæt, der kræver bagudrettede
ændringer

Der vil være forskelle med hensyn til, hvem et SKAL/BØR/KAN gælder for.
Referencearkitekturen skelner mellem følgende:
- **Fællesoffentlige løsninger.** Det er løsninger, der er finansieret og specificeret gennem en fællesoffentlig aftale fx det fællesoffentlige eID (pt. NemID),
NemLog-in og Digital Post.
- **Tværoffentlige brugerstyringsløsninger.** Det er løsninger, der anvendes af
flere myndigheder og er finansieret på anden måde end gennem fællesoffentlig aftale fx Uni*Login, Miljøportalen, WAYF, Kommunerne, Sundhed.
- **Tjenester der anvender fællesoffentlige og tværoffentlige løsninger,** og
som er rettet mod borgere og virksomheder som slutbrugere. Eksempler er
borger.dk, virk.dk, sundhed.dk og kommunale tjenester.
- **Løsninger der finansieres og fungerer inden for en offentlig sektor.** Det
omfatter både løsninger til brugerstyring i myndigheder og fx fagsystemer i
myndigheder.

For hvert afsnit angives en af følgende formuleringer:
&rarr Dette afsnit SKAL/BØR/KAN efterkommes i fællesoffentlige løsninger.
&rarr Dette afsnit SKAL/BØR/KAN efterkommes i tværoffentlige brugerstyringsløsninger.
&rarr Dette afsnit SKAL/BØR/KAN efterkommes i tjenester, der anvender
fællesoffentlige og tværoffentlige løsninger.
&rarr Dette afsnit BØR/KAN efterkommes af løsninger i offentlige sektorer.
Referencearkitekturen vil give status for standarder mv. På arkitekturguiden.digitaliser.dk vil der være oplysninger om konkrete standarder, efterhånden som de beskrives og fastlægges.

### 1.4 Metoderamme
