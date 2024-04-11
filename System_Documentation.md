<div align="center">
  <a href="https://github.com/ArvidWedtstein/Fagproove">
    <img src="https://content.energage.com/company-images/SE45893/SE45893_logo_orig.png" alt="Logo" width="200" height="200">
  </a>

  <h3 align="center">System Dokumentasjon</h3>

  <p align="center">
    <b>Fagprøve</b>
    <br />
    <sub>05.04.24 - 15.04.24</sub>
  </p>
</div>

<details>
  <summary>
    <b>Table of Contents</b>
  </summary>
  <ol>
    <li>
      <a href="#oppgave">Oppgave</a>
    </li>
    <li>
      <a href="#teknologier">Teknologier</a>
    </li>
    <li>
      <a href="#teknologier">Arkitektur</a>
       <ul>
        <li>
          <a href="#tabeller">Tabeller</a>
          <ul>
            <li>
              <a href="#sikkerhet-i-tabeller">Sikkerhet i Tabeller</a>
            </li>
          </ul>
        </li>
      </ul>
    </li>
    <li>
      <a href="#sikkerhet">Sikkerhet</a>
    </li>
    <li>
      <a href="#grensesnittbeskrivelse">Grensesnittbeskrivelse</a>
    </li>
    <li>
      <a href="#hindringer-under-utviklingen">Hindringer under utviklingen</a>
    </li>
    <li>
      <a href="#avvik-fra-plan">Avvik fra plan</a>
    </li>
    <li>
      <a href="#kilder">Kilder / Ressurser</a>
    </li>
  </ol>
</details>

<details open>
  <summary>
    <h2>Oppgave</h2>
  </summary>
  <p>
    Utvikle en enkel quiz-app hvor brukere kan svare på spørsmål med flere valgmuligheter, se sin poengsum ved slutten, og prøve igjen. Spørsmål og metadata ligger på en server, med et dokumentert integrasjonslag mellom klient og server. 
  </p>  
  <hr>
</details>
<details open>
  <summary>
    <h2>Teknologier</h2>
  </summary>
   <ol>
    <li>
      <p>Omega 365 (NT) rammeverket</p>
      Fordi det har innebygd sikkerhet, enkelt å komme igang med, er en av bedriftens standard rammeverk og fordi jeg har fått utrolig mye kjennskap til det. I tillegg så har rammeverket en god del komponenter som gjør ting lettere i forhold til å lage dem selv. 
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
      Fordi det va enklast å laga dokumentasjon i og lett å invitera andre.
    </li>
    <li>
      <p>DrawSQL</p>
      Fordi den var perfekt for å lage sql tabell diagram. Vi har i teorien en intern løsning for dette, men har av en eller annen grunn ikke fått tilgang til denne.
    </li>
    <li>
      <p>Figma</p>
      Paint va ikkje et alternativ, så då blei det figma og fordi det er ganske enkelt å bruke figma.
    </li>
  </ol>
  <hr>
</details>

<details open>
  <summary>
    <h2>Arkitektur</h2>
  </summary>
 <ul>
    <li>
      <details>
        <summary>
          <h4>Tabeller</h4>:
        </summary>      
        <a href="https://drawsql.app/teams/arvid/diagrams/quiz-application">Tabellstruktur</a>
      </details>
    </li>
   <li>
     
   </li>
  </ul>
  <hr />
</details>

<details open>
  <summary>
    <h2>Sikkerhet</h2>
  </summary>
  <p>
    Sikkerhet i Omega 365 rammeverket er slik at det lages en atbv for hver tabell.<br>
    Denne atbv'en inneholder en whereclause som sjekker opp tabellnavnet mot dine tabeller (disse tabellene fås gjennom rolletilganger, modultilganger, capabilities)<br>
    Så lages det ofte en aviw som henter data gjennom atbv'en for å ikke miste sikkerhetssjekken.<br>
    Stored procedures trenger egen tilgangssjekk siden de som regel unngår disse tilgangsjekkene, med mindre du spesifiseres dem i triggerene.
    <br><br>
    I dette tilfellet så har jeg ordnet sikkerhetssjekkene i atbv'en og triggerene
  </p>
  <hr />
</details>
<details open>
  <summary>
    <h2>Grensesnittbeskrivelse</h2>
  </summary>
  <p>
    For en veldig simpel beskrivelse se: <a href="User_Manual_NO.md">Brukerveiledning</a>
  </p>
  <br>
  <p>
    ss
  </p>
  <hr />
</details>

<details open>
  <summary>
    <h2>Hindringer under utviklingen</h2>
  </summary>
  <ol>
    <li>
      <p>
        En av hindringene har vært å finne ut beste måte kalkulere poeng.<br>
        I utgangspunktet var planen å gi poeng per spørsmål og så dele opp poengsum på antall mulig rette svaralternativer, vis brukeren ikke hadde svart alle rett.
        Endte opp med å gi bruker poeng for hvert rette svar for å gjøre utregning enklere
      </p>   
    </li>
    <li>
      <p>
        Har brukt en del tid på å finne beste måte for å opprette en quiz på.<br>
        Problemer var at måten Omega 365 rammeverket er satt opp så opprettes det en "master-child binding" mellom to tabeller.<br>
        Så når du lager en ny rad i quiz tabellen og så prøver å legge til spørsmål,<br>
        så har spørsmålstabellen ingen ID å referere til i quiz tabellen siden quiz raden ikke er lagret til databasen enda.
        Samme problem eksisterte også for svaralternativer til spørsmålene.
      </p>
      <p>Mulighetene jeg kom frem til her var:</p>
      <ul>
        <li>
          Lage en modal og lagre til databasen hver gang et nytt spørsmål eller svaralternativ legges til eller endres på.<br>
          Ulempen med dette er at brukeren da mister mulighet for å kansellere endringer og trigger sjekker ble vanskeligere å få til.
        </li>
        <li>
          Lage en modal for hver tabell.<br>
          Dette blir så å si det samme som løsning nr 1, at du lagrer hver gang.
        </li>
        <li>
          <p>
            Lage en variabel for innholdet i en quiz, og så bruke en sql stored procedure som da inserter rader som vanlig vis quiz opprettes. <br>
            Om en quiz redigeres, så slettes da alle gamle radene for så å opprette nye rader med de aktuelle endringene.
          </p>
        </li>
      </ul>
      <p>
        Endte opp med å gå for løsning nr 3. da jeg foretrakk å kunne kansellere endringer.
      </p>
      <p>
        En av sideeffektene denne løsningen har er at brukerens forsøk på quizzen er referert til spørsmål i quizzen.<br>
        Så når spørsmålene blir slettet for å opprettes igjen så skaper dette foreign key conflict.
      </p>
      <p>
        Løsningen på dette ble å rett og slett låse spørsmålet for redigering vis brukere har kjørt quizzen og fullført det spørsmålet.<br>
        Ved å låse spørsmålet så unngikk jeg dermed også mulighet for å jukse på quizresultater ved at man endrer spørsmålene eller poengsum i etterkant.
      </p>
      <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/f323d9b3-ab67-42d4-908c-c536cee0d24f" width="200">
    </li>
  </ol>
<hr />
</details>

<details open>
  <summary>
    <h2>Avvik fra plan</h2> (Endringer under utvikling)
  </summary>
  
  <ol>
    <li>
      <p>
        Hadde neon "minimale" endringer i tabellstrukturen for å slippe hardkodinger her og der.<br>
        La blant annet til InputType kolonne i questiontypes tabellen for å støtte flere typer i fremtiden.
      </p>
    </li>
    <li>
      <p>
        Endret litt på layout i selve siden for quiz for å få en bedre oversikt over hvilket spørsmål brukeren er på.<br>
        Reset knappen ble blant annet flyttet til høyre og hvilket spørsmål brukeren er på opp.
      </p>
    </li>
  </ol>
  <hr />
</details>

<details open>
  <summary>
    <h2>Kilder</h2>
  </summary>

  <ol>
    <li>
      <a href="https://stackoverflow.com/questions/49729243/insert-nested-json-array-into-multiple-tables-in-sql-server">Stackoverflow post om hvordan inserting i forskjellige tabeller kan gjøres med nested json data</a>
    </li>
    <li>
      <a href="https://vuejs.org/">Vue Docs</a>
    </li>
    <li>
      <a href="https://getbootstrap.com/docs/5.3">Bootstrap Docs</a>
    </li>
    <li>
      Omega 365 Docs (Har dessverre ikke link til denne. Ligger litt spredt rundt i diverse apper)
    </li>
    <li>
      <a href="https://github.com/TorAasheimOmega">Tor (for teknisk støtte)</a>
    </li>
    <li>
      <a href="https://chat.openai.com">ChatGPT</a>
    </li>
    <li>
      <a href="roger.torkelsen@omega365.com">Roger (SQL Expert)</a>
    </li>
  </ol>
 
<hr />
</details>
