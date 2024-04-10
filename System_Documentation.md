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
      <a href="#info">Info</a>
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
        <li>
          <a href="#views">Views</a>
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
    <h2>Info</h2>
  </summary>
    
  Fagprøve oppgave.
  
 Insert oppgava her



<hr>
</details>
<details open>
  <summary>
    <h2>Teknologier</h2>
  </summary>
    
Insert stuff here
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
        
Insert diagram of tables here
  <!-- [Tabellstruktur](https://drawsql.app/teams/arvid/diagrams/tabellstruktur) -->
        
   <details>
      <summary>
        <h4>Sikkerhet i Tabeller</h4>:
      </summary>

  <table>
        <tr>
          <th>Tabell Navn</th>
          <th>Beskrivelse</th>
          <th>Regler Insert</th>
          <th>Regler Update</th>
          <th>Regler Delete</th>
          <th>Bilder</th>
        </tr>
        <tr>
          <td><b>Insert table name here</b></td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td>
            <table>
              <th>
                <img src="" width="60" />
              </th>
            </table>
          </td>
        </tr>
      </table>
  </details>
      </details>
    </li>
    <li>
      <details>
          <summary>
            <h4>Views</h4> (TSQL):
          </summary>
        
  <table>
  <tr>
    <th>View Navn</th>
    <th>Beskrivelse</th>
    <th>Kode</th>
  </tr>
  <tr>
    <td>Insert view name here</td>
    <td></td>
    <td>
     <img src="" width="60" />
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
    Sikkerhet i Omega 365 rammeverket er slik at det lages en atbv for hver tabell.<br>
    Denne atbv'en inneholder en whereclause som sjekker opp tabellnavnet mot dine tabeller (disse tabellene fås gjennom rolletilganger, modultilganger, capabilities)<br>
    Så lages det ofte en aviw som henter data gjennom atbv'en for å ikke miste sikkerhetssjekken.<br>
    Stored procedures trenger egen tilgangssjekk siden de som regel unngår disse tilgangsjekkene, med mindre du spesifiseres dem i triggerene.
    <br><br>
    I dette tilfellet så har jeg ordnet sikkerhetssjekkene i atbv'en og triggerene
  </p>

   <table>
    <th>
      <img src="" width="60" />
    </th>
  </table>
  
<hr />
</details>
<details open>
  <summary>
    <h2>Grensesnittbeskrivelse</h2>
  </summary>


  <details>
    <summary><h5>Insert title here</h5></summary>
    <table>
        <tr>
          <th>Funksjoner</th>
          <th colspan="3">Beskrivelse</th>
          <th>Kode</th>
          <th>Bilder</th>
        </tr>
      <tr>
          <td>Insert function here</td>
          <td colspan="3"></td>
          <td>
            <table>
              <th>
                <img src="" width="60" />
              </th>
            </table>
          </td>
          <td> 
            <table>
              <th>
                <img src="" width="60" />
              </th>
            </table>
          </td>
        </tr>
      </table>
  </details>
    
<hr />
</details>
<details open>
  <summary>
    <h2>Hindringer under utviklingen</h2>
  </summary>

  <ol>
    <li>
      <p>
        En av hindringene har vært å kalkulere poeng.<br>
        I utgangspunktet var planen å gi poeng per spørsmål og så dele opp poengsum på antall mulig rette svaralternativer, vis brukeren ikke hadde svart alle rett.
        Endte opp med å gi bruker poeng for hvert rette svar for å gjøre utregning enklere
      </p>
      <table>
        <th><img src="" width="60"></th>
      </table>    
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
      <p></p>
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
  </ol>
 
<hr />
</details>
