<div align="center">
  <a href="https://github.com/ArvidWedtstein/Fagproove">
    <img src="https://content.energage.com/company-images/SE45893/SE45893_logo_orig.png" alt="Logo" width="200" height="200">
  </a>

  <h3 align="center">Daily Log</h3>

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
      <a href="#0504">Fredag 05.04</a>
    </li>
    <li>
      <a href="#0604">Lørdag 06.04</a>
    </li>
    <li>
      <a href="#0704">Søndag 07.04</a>
    </li>
    <li>
      <a href="#0804">Mandag 08.04</a>
    </li>
    <li>
      <a href="#0904">Tirsdag 09.04</a>
    </li>
    <li>
      <a href="#1004">Onsdag 10.04</a>
    </li>
    <li>
      <a href="#1104">Torsdag 11.04</a>
    </li>
    <li>
      <a href="#1204">Fredag 12.04</a>
    </li>
    <li>
      <a href="#1304">Lørdag 13.04</a>
    </li>
    <li>
      <a href="#1404">Søndag 14.04</a>
    </li>
    <li>
      <a href="#1504">Mandag 15.04</a>
    </li>
  </ol>
</details>

<details open>
  <summary>
    <h2>05.04</h2>
  </summary>
  <p>
    Fiksa figma skissa, laget tabellstruktur. Vurdert ka som e beste måten å løsa detta på. 
  </p>


<hr>
</details>
<details open>
  <summary>
    <h2>06.04</h2>
  </summary>
  <p>
    La til AllowMultipleOptions og IsDefault på QuestionTypes tabellen.<br>
    Dette så jeg slipper å hardkode inn standard type og maks antall svarmuligheter for de typene 'Text' og 'Date'
  </p>
<hr>
</details>
<details open>
  <summary>
    <h2>07.04</h2>
  </summary>
  <p>
    La til InputType på QuestionTypes tabellen.<br>
    Dette er ment for å kunne supporte andre typer input som feks "star rating" i tillegg til radio, som ikke ville gått, hadde jeg hardkodet dette inn.  
  </p>

<hr>
</details>
<details open>
  <summary>
    <h2>08.04</h2>
  </summary>
  <p>
    Oppsto litt problemer med å legge til tabeller i modulen.<br>
    Visste seg å være kø i objects cache, så funket etter en stund 🙂
  </p>

  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/cc5c7e6a-49b9-474b-a72a-734b1288240c">
  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/bf9ce9d3-da17-4bde-9478-6dd068a09661">

  <p>
    Laget tabellene i tabellskjema.<br>
    Fikset trigger security<br>
    Checkliste triggers:
  </p>

  <table>
    <tr>
      <th>Tabell</th>
    </tr>
    <tr>
      <td>
        <details>
          <summary>atbl_ArvidWedtstein_Quizes</summary>
          <table>
            <tr>
              <th>Insert</th>
              <th>Update</th>
              <th>Delete</th>
            </tr>
            <tr>
              <td>✅</td>
              <td>✅</td>
              <td>✅</td>
            </tr>
          </table>
        </details>
      </td>
    </tr>
    <tr>
      <td>
        <details>
          <summary>atbl_ArvidWedtstein_QuizQuestions</summary>
          <table>
            <tr>
              <th>Insert</th>
              <th>Update</th>
              <th>Delete</th>
            </tr>
            <tr>
              <td>✅</td>
              <td>✅</td>
              <td>✅</td>
            </tr>
          </table>
        </details>
      </td>
    </tr>
    <tr>
      <td>
        <details>
          <summary>atbl_ArvidWedtstein_QuizQuestionAnswers</summary>
          <table>
            <tr>
              <th>Insert</th>
              <th>Update</th>
              <th>Delete</th>
            </tr>
            <tr>
              <td>✅</td>
              <td>✅</td>
              <td>✅</td>
            </tr>
          </table>
        </details>
      </td>
    </tr>
    <tr>
      <td>
        <details>
          <summary>atbl_ArvidWedtstein_QuizQuestionTypes</summary>
          <table>
            <tr>
              <th>Insert</th>
              <th>Update</th>
              <th>Delete</th>
            </tr>
            <tr>
              <td>✅</td>
              <td>✅</td>
              <td>✅</td>
            </tr>
          </table>
        </details>
      </td>
    </tr>
    <tr>
      <td>
        <details>
          <summary>atbl_ArvidWedtstein_QuizAttempts</summary>
          <table>
            <tr>
              <th>Insert</th>
              <th>Update</th>
              <th>Delete</th>
            </tr>
            <tr>
              <td>✅</td>
              <td>✅</td>
              <td>✅</td>
            </tr>
          </table>
        </details>
      </td>
    </tr>
    <tr>
      <td>
        <details>
          <summary>atbl_ArvidWedtstein_QuizAttemptsResponses</summary>
          <table>
            <tr>
              <th>Insert</th>
              <th>Update</th>
              <th>Delete</th>
            </tr>
            <tr>
              <td>✅</td>
              <td>✅</td>
              <td>✅</td>
            </tr>
          </table>
        </details>
      </td>
    </tr>
  </table>

  <p>
    Møtte på et problem med at jeg glemte helt ut at selve quizzen må vær laget for at foreign key til questions tabellen skal funke.<br>
    Endte opp med å lage en kolonne "IsTemporary" i quiz tabellen.
  </p>

  <p>
    Begynte på details siden.<br>
    Lagt til validering på spørsmålene
  </p>
  
  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/144792bb-dc5b-4944-8df2-8cf85737c750">
  <img src="https://github.com/ArvidWedtstein/Fagproove/assets/71834553/745eb11a-f9e8-4119-9f7a-9e9076af08f8">

<hr>
</details>
<details open>
  <summary>
    <h2>09.04</h2>
  </summary>
  <p>
    Fortsatt på modal for å opprette quiz.<br>
    Vurderer å bruke stored procedure for å opprette ny quiz / redigere siden innebygd dataobject classe ikke har mulighet for å opprette flere "nye" rader uten å lagre.<br>
    Alternativet hadde vært å bare lagre hele tiden. 
  </p>

<hr>
</details>
<details open>
  <summary>
    <h2>10.04</h2>
  </summary>


<hr>
</details>
<details open>
  <summary>
    <h2>11.04</h2>
  </summary>


<hr>
</details>
<details open>
  <summary>
    <h2>12.04</h2>
  </summary>


<hr>
</details>
<details open>
  <summary>
    <h2>13.04</h2>
  </summary>


<hr>
</details>
<details open>
  <summary>
    <h2>14.04</h2>
  </summary>


<hr>
</details>
<details open>
  <summary>
    <h2>15.04</h2>
  </summary>


<hr>
</details>

