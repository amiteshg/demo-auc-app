# smart-auc-demo
A demonstration SMART app that serves AUC external guidance for PAMA.

Instructions
------------

```sh
npm install
npm run demo
```

Visit http://localhost:3001/ to log in (use any username and password)

<img src="./images/login.png" alt="alt text" width="256">

Select a patient age, gender, indication, and order to determine whether it
is within recommended guidelines.

  <div>
    <form action="evaluate" method="POST">
      <table>
        <caption>Enter Patient Demographics</caption>
        <tr>
          <th><label for="gender">Gender</label></th>
          <td>
            <select name="gender" required>
              <option value="male">Male</option>
              <option value="female">Female</option>
              <option value="other">Other</option>
            </select>
          </td>
        </tr>
        <tr>
          <th><label for="age">Age</label></th>
          <td><input name="age" required></td>
        </tr>
        <tr>
          <th><label for="indication">Indication</label></th>
          <td>
            <input list="indications" name="indication" required>
            <datalist id="indications">
              <option value="13213009">congenital heart disease</option>
              <option value="25064002">headache</option>
              <option value="279039007">lower back pain</option>
              <option value="423341008">optic disc edema</option>
              <option value="27355003">toothache</option>
            </datalist>
          </td>
        </tr>
        <tr>
          <th><label for="procedure">Procedure</label></th>
          <td>
            <input list="procedures" name="procedure">
            <datalist id="procedures">
              <option value="75561">cardiac mri</option>
              <option value="70450">ct scan - no contrast material</option>
              <option value="71275">cta - with contrast material</option>
              <option value="72133">lumbar spine ct scan</option>
              <option value="70544">mra - head</option>
            </datalist>
          </td>
        </tr>
      </table>
      <input type="submit">
    </form>
  </div>

V1 TODO
-------

- [x] Mock a simple UI on paper / in Visio
- [x] Create a static page form to serve as the starting point
  - [x] Fake sign-in
  - [x] Enter Demographics (age and gender)
  - [x] Select a condition
  - [x] Select an appropriate imaging procedure
