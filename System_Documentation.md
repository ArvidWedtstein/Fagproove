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
      <a href="#arkitektur">Arkitektur</a>
       <ul>
        <li>
          <a href="#tabeller">Tabeller</a>
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
          <a href="https://vuejs.org" title="Vue.js">
           <img src="https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D" alt="Vue.js"> 
          </a>
        </li>
        <li> 
          <a href="https://getbootstrap.com/docs/5.3" title="Bootstrap">
           <img src="https://img.shields.io/badge/Bootstrap-dddddd?style=for-the-badge&logo=bootstrap&logoColor=572b8a" alt="bootstrap"> 
          </a>
        </li>
        <li>
          <a href="https://getbootstrap.com/docs/5.3" title="Transact SQL">
           <img src="https://img.shields.io/badge/Microsoft%20SQL%20Server-CC2927?logo=microsoftsqlserver&logoColor=fff&style=for-the-badge" alt="Transact SQL"> 
          </a>
        </li>
      </ul>
    </li>
    <li>
      <a href="https://github.com/ArvidWedtstein/Fagproove" title="Github">
       <img src="https://img.shields.io/badge/Github-000000?logo=github&logoColor=fff&style=for-the-badge" alt="Github"> 
      </a>
      Fordi det va enklast å laga dokumentasjon i og lett å invitera andre.
    </li>
    <li>
      <p>DrawSQL</p>
      Fordi den var perfekt for å lage sql tabell diagram. Vi har i teorien en intern løsning for dette, men har av en eller annen grunn ikke fått tilgang til denne.
    </li>
    <li>
      <img src="https://img.shields.io/badge/figma?logo=figma&style=for-the-badge" alt="Figma"> 
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
      <details>
        <summary>
         Views 
        </summary>
        <table>
          <tr>
            <th>View Navn</th>
            <th>Beskrivelse (Hvorfor eksisterer dette viewet?)</th>
            <th>Bilder</th>
          </tr>
          <tr>
            <td><b>aviw_ArvidWedtstein_QuizAttempts</b></td>
            <td>
              Dette viewet brukes for å blant annet vise stats over tidligere quiz-forsøk<br>
              og holde styr på sist svarte spørsmål i tilfelle brukeren velger å lukke siden med uhell eller lignende.
            </td>
            <td>
              <table>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/2873e437-e421-4458-9430-ba7c4a84ec3e" width="200" />
                </th>
              </table>
            </td>
          </tr>
          <tr>
            <td><b>aviw_ArvidWedtstein_QuizAttemptsResponses</b></td>
            <td>
              Dette viewet brukes egentlig bare for å hente inn svartekst og om svaret er rett i tillegg til brukerens svar
            </td>
            <td>
              <table>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/f304bcde-0abc-4eaa-a573-a1efc0357f7f" width="200" />
                </th>
              </table>
            </td>
          </tr>
          <tr>
            <td><b>aviw_ArvidWedtstein_QuizQuestions</b></td>
            <td>
              Brukes for å sjekke om et spørsmål er låst for redigering,<br>
              I tillegg henter dette viewet inn generell data om spørsmålstype, osv.
            </td>
            <td>
              <table>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/ee24ae71-ac91-46cd-bfb8-399f60f3dc9d" width="200" />
                </th>
              </table>
            </td>
          </tr>
        </table>
      </details>
    </li>
    <li>
      <details>
        <summary>
         Stored Procedures 
        </summary>
        <table>
          <tr>
            <th>Stored Procedure Navn</th>
            <th>Beskrivelse</th>
            <th>Bilde</th>
          </tr>
          <tr>
            <td><b>astp_ArvidWedtstein_CalculateQuizAttemptPoints</b></td>
            <td>
              Brukes for å kalkulere poengsum.<br>
              Var i utgangspunktet planen å ta me antall klarte og ikke-klarte spørsmål,<br>
              men fikk ikke tid til å implementere dette i frontend, så er derfor de ligger her foreløbig.
            </td>
            <td>
              <table>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/c16491a0-2183-4d93-bb3b-fedfeaed9c05" width="200" />
                </th>
              </table>
            </td>
          </tr>
          <tr>
            <td><b>astp_ArvidWedtstein_GetQuizQuestionsJson</b></td>
            <td>
              Denne stored proceduren kjøres i det en quiz redigeres, før modalen åpnes.<br>
              Alt denne gjør et å stappe spørsmålsradene og svaralternativene i et JSON objekt.<br>
              Dette JSON objektet sendes så tilbake i stored proceduren under (astp_ArvidWedtstein_CreateOrEditQuiz) for å oppdatere, slette eller inserte radene.
            </td>
            <td>
              <table>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/55e866c5-3ca8-4013-af24-f6ad56867666" width="200" />
                </th>
              </table>
            </td>
          </tr>
          <tr>
            <td><b>astp_ArvidWedtstein_CreateOrEditQuiz</b></td>
            <td>
              Denne sørger basicly for at quizdata blir oppdatert, inserted eller slettet.<br>
              Her brukes primkey som for å sjekke om raden kan oppdateres, insertes eller slettes.<br>
              Da data blir sendt inn gjennom JSON, har jeg "pakket" denne ut til to egne temp tabeller.<br>
              Siden dette er nesten JSON, så ble jeg nødt til å lage en referanse til questions tabellen fra answers tabellen.<br>
              Om PrimKey eksisterer på raden, så oppdateres denne, eksisterer den ikke, så insertes raden.<br><br>
              Til slutt kjøres det en delete spørring som luker vekk alle radene som ikke eksisterer i Questions JSON objektet.<br>
            </td>
            <td>
              <table>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/bcd803e2-b70a-4420-aee1-ed5cab395d67" width="200" />
                </th>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/8bc2a09e-5066-4fca-9968-23f59b16d007" width="200" />
                </th>
                <th>
                  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/e3c350f0-fc26-41c0-82d9-c57d01e40423" width="200" />
                </th>
              </table>
            </td>
          </tr>
        </table>
      </details>
    </li>
  </ul>
  <hr />
</details>

<details open>
  <summary>
    <h2>Sikkerhet</h2>
  </summary>
  <p>
    Autentiseringssikkerhet i appframe er slik at når bruker åpner en Appframe nettside, så blir bruker først redirected til login side.<br>
    Der kan bruker velge mellom å logge inn med microsoft bruker eller SQL login.
    Velger bruker microsoft, blir dette kjørt internt hos microsoft og det returneres en token.<br>
    Ved SQL innlogging så sjekkes brukernavn og passord opp mot en bruker i databasen gjennom et API kall.<br>
    Dette skjer på en sikker og forsvarlig måte.
  </p>
  <p>
    Tabellsikkerhet i Appframe rammeverket er slik at det lages en atbv for hver tabell.<br>
    Denne atbv'en inneholder en whereclause som sjekker opp tabellnavnet mot dine tabeller (disse tabellene fås gjennom rolletilganger, modultilganger, capabilities)<br>
    Så lages det ofte en aviw som henter data gjennom atbv'en for å ikke miste sikkerhetssjekken.<br>
    Stored procedures trenger egen tilgangssjekk siden de som regel unngår disse tilgangsjekkene, med mindre du spesifiseres dem i triggerene.
    <br>
  </p>
  <p>
    I dette tilfellet så har jeg ordnet sikkerhetssjekkene i atbv'en og triggerene.<br>
    Dermed vil ingen uten "Quiz user" rollen se, åpne eller kunne bruke quiz appen(e).<br>
    I tillegg så kan ingen uten "Quiz Admin" redigere eller opprette nye quizer.
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
    Quizzen er delt opp i 2 apper, en for oversikt over alle quizzene, og en for å svare på spørsmål i en valgt quiz.<br>
    Oppretting/redigering av quiz, spørsmål og svaralternativer skjer gjennom en modal på samme side som viser alle quizzene.<br>
    Modalen funker slik at den tar en kopi av quiz innholdet ved redigering,<br>
    og så laster dette opp til en stored procedure som sjekker om raden(e) må insertes, updates eller slettes.
  </p>
  <p>
    Er mulighet for å se tidligere forsøk på en quiz etter at bruker har fullført quiz eller i hovedsiden.
  </p>
  <p>
    I det bruker starter en quiz, så opprettes det et nytt "forsøk" i tabellen for quizforsøk.<br>
    Om bruker har et ufullført forsøk fra før, så vil bruker bli spurt om dette forsøket skal fortsettes på.
  </p>
  <p>
    Bruker kan deretter begynne å svare på quiz.<br>
    Hver gang bruker leverer inn et svar, så vil dette lagres i databasen.
  </p>
  <p>
    Alt dette er stylet med bootstrap (bedriftens standard) og en smule custom css.
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
        Endte opp med å gå for løsning nr 3. da jeg foretrakk å kunne kansellere endringer.<br>
        I utgangspunktet var planen i bruke SQL Merge for dette.<br>
        Fikk etter hvert vite av Roger, at dette ikke var så lurt da MERGE er full av bugs.<br>
        Derfor ledet Roger meg på rett spor og jeg endte opp med å sjekke opp mot PrimKey kolonnen om raden skal oppdateres, insertes eller slettes.
      </p>
      <p>
        En av sideeffektene denne løsningen har er at brukerens forsøk på quizzen er referert til spørsmål i quizzen.<br>
        Så når et spørsmål blir slettet så skaper dette foreign key conflict.
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
    <li>
      <p>
        Planen var egentlig å være ferdig med stored procedures på mandag,<br>
        dette skjedde jo selvfølgelig ikke..<br>
        Ble en del frem og tilbake i forbindelse med å opprette/redigere quiz, så derfor måtte jeg også oppdattere brukerveileding og testrapporten i etterkant.
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
      <a href="https://chat.openai.com">ChatGPT (Fekk an te å forklara kossen eg brukte SQL MERGE, men fekk ikke bruk for MERGE til slutt alikevel)</a>
    </li>
    <li>
      <a href="mailto:roger.torkelsen@omega365.com">Roger</a>
    </li>
    <li>
      <a href="https://shields.io">Shields.io (bagdes)</a>
    </li>
  </ol>
 
<hr />
</details>

<!-- Urls -->
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
