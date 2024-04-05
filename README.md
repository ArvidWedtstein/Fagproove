<div align="center">
  <a href="https://github.com/ArvidWedtstein/Fagproove">
    <img src="https://content.energage.com/company-images/SE45893/SE45893_logo_orig.png" alt="Logo" width="200" height="200">
  </a>

  <h3 align="center">Planlegging</h3>

  <p align="center">
    <b>Fagprøve</b>
    <br />
    <sub>05.04.24 - 15.04.24</sub>
  </p>
</div>

## Målet med oppgaven:
Utvikle en enkel quiz-app hvor brukere kan svare på spørsmål med flere valgmuligheter, se sin poengsum ved slutten, og prøve igjen. Spørsmål og metadata ligger på en server, med et dokumentert integrasjonslag mellom klient og server. 


Funksjonalitet og Krav: 

- Applikasjonskomponenter: Klient-applikasjon for visning av spørsmål, server lagrer spørsmål og tilbyr disse via et sikret API. 
- Quizfunksjonalitet: Flervalgsspørsmål med umiddelbar tilbakemelding på om svaret er riktig eller feil. 
- Poengsum: Beregn og vis brukerens poengsum ved slutten av quizen. 
- Gjenstartfunksjon: La brukeren starte quizen på nytt med et enkelt klikk. 
- Design: Design som møter grunnleggende krav til universell utforming og tilgjengelighet. 

## Utstyr
Omega 365 NT rammeverket / Vue.js fordi dette har brukerregistrering/innlogging integrert og er lett å komme igang med.
DrawSQL for å tegne Tabellstruktur
Bootstrap icons

 <ol>
    <li>
      <p>Omega 365 NT rammeverket</p>
      <small>Fordi det har innebygd sikkerhet</small>
       <ul>
        <li>
          Vue.js
        </li>
        <li>
         Bootstrap
        </li>
        <li>
          Transact SQL
        </li>
      </ul>
    </li>
    <li>
      <p>Github</p>
    </li>
    <li>
      <p>DrawSQL</p>
    </li>
    <li>
      <p>Figma</p>
    </li>
  </ol>

## Eventuelle informasjonskilder:
- Vue Docs
- Bootstrap Docs
- Omega 365 Docs


## Fremgangsmåte:
<ol>
  <li>
    <p>Planlegga tabellstruktur, sikkerhet og design layout</p>
  </li>
  <li>
    <p>Lage tabellene</p>
    <ul>
      <li>
        <details>
          <summary>
            Lager tabellstruktur
          </summary>
          <p>
            For å dekke mest mulig av kravene så har jeg delt det opp slik at vi har en tabell for quizer. 
            Denne tabellen kan kun brukere med "Arvid Wedtstein Quiz Admin" rollen legge til, endre og slette data.
          </p>
          <p>
            Så har vi en sub tabell for spørsmål i quizen. Denne har en mange-til-en relasjon til quiz tabellen. 
          </p>
          <p>
            Denne tabellen igjen har en sub tabell for svar til hvert spørsmål hvor rette svar markeres med IsCorrect bit felt.
            Denne tabellen har en mange-til-en relasjon til en tabell for spørsmålstyper. Det er typen som bestemmer om spørsmålet blir "multi choice", "radio", tekst, dato osv.
            Om bare ett av svarene til et spørsmål har IsCorrect definert som 1 (true) så blir spørsmålet et "radio choice" felt, dersom det er flere som er markert som rette så blir det "multiple choice" og vis bare et svar eksisterer på spørsmålet så blir det text.
          </p>
          <p>
            Så har me ein tabell for Quiz Attempts. Her er planen at det skal opprettes en rad for hver gang en bruker kjører quizen. Denne tabellen lagrer også brukerens endelige poengsum. Denne har en sub tabell for svar og brukerens valgte svar.
          </p>
        </details>
      </li>
      <li>
        <details>
          <summary>
            Sikkerhet for tabellene med triggerene (Insert, Update, Delete)
          </summary>
          <p>I Omega 365 rammeverket så løses tilganger gjennom roller</p>
        </details>
      </li>
    </ul>
  </li>
  <li>
    <p>Lager deretter appene (mobile first)</p>
    <ul>
      <li>
        <details>
          <summary>
            Design
          </summary>
          <p>
            I designprosessen så var planen å ha støtte for både mobil og desktop visning i tillegg til standard brukervennlighet.  
          </p>
          <p>
            Har prøvd å få til en ca <a href="https://www.figma.com/file/wAfk628QcepBXb72LQu2fh/Quiz-Application?type=design&node-id=0%3A1&mode=design&t=KoQn02fTknG43iEB-1">figma skisse</a> om hvordan jeg tenker layouten kan være. 
          </p>
          <p>
            For å 
          </p>
        </details>
      </li>
    </ul>
  </li>
  <li>
    <p>Legger til planlagt funksjonalitet (se Skisse av løsningen).</p>
  </li>
  <li>
    <p>Legger opp for mulighet for brukerregistrering og pålogging</p>
  </li>
  <li>
    <p>Legger eventuelt til bonusfunksjonalitet, avhengig av tid til overs.</p>
  </li>
  <li>
    <p>Tester gjennom appen(e) og dokumenterer dette i en test rapport.</p>
  </li>
  <li>
    <p>Lager system dokumentasjon</p>
  </li>
  <li>
    <p>Lager brukeranvisning (på engelsk, norsk og tysk om jeg får tid).</p>
  </li>
  <li>
    <p>Lage presentasjon.</p>
  </li>
</ol>


## Skisse av løsningen:

<a href="https://drawsql.app/teams/arvid/diagrams/quiz-application">SQL Tabell Struktur</a>

<a href="https://www.figma.com/file/wAfk628QcepBXb72LQu2fh/Quiz-Application?type=design&node-id=0%3A1&mode=design&t=KoQn02fTknG43iEB-1">Grov Figma Skisse</a>

## Tidsskjema:

<details>
  <summary>
    Fredag <sub>05.04</sub>
  </summary>

  <ul>
    <li>Planlegging</li>
    <li>Lage tabellstruktur (ca 1.5t)</li>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Lørdag <sub>06.04</sub>
  </summary>
  
  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Søndag <sub>07.04</sub>
  </summary>

  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Mandag <sub>08.04</sub>
  </summary>
    
  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Tirsdag <sub>09.04</sub>
  </summary>


  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Onsdag <sub>10.04</sub>
  </summary>
  
  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Torsdag <sub>11.04</sub>
  </summary>

  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Fredag <sub>12.04</sub>
  </summary>

  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Lørdag <sub>13.04</sub>
  </summary>

  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Søndag <sub>14.04</sub>
  </summary>

  <ul>
    <li>Dokumentere dagens arbeid (ca 0.5t)</li>
  </ul>
</details>
<details>
  <summary>
    Mandag <sub>15.04</sub>
  </summary>

  <ul>
    <li>Presentera (tar så lang tid det tar)</li>
    <li>Egenvurdering</li>
  </ul>
</details>


