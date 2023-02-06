<style>
table {
  border-collapse: collapse;
  width: 100%;
}
td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
  color: white
}
</style>

<html>
    <head>
        <title>Sign UP</title>
    </head>
    <body>
            <h1>Register</h1>
            <form method="POST">
                <br><br>
                <input type="username" name="username" placeholder="Username"><br>
                <input type="password" name="password" placeholder="Password"><br>
                <input type="email" name="email" placeholder="Email"><br>
                <input type="number" name="age" placeholder="Age"><br>
                <br>
                <input type="submit" value="Sign Up">
            </form>
    </body>
</html>

<!-- <script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("result");

  // prepare fetch options
  const url = "https://csp.nighthawkcodingsociety.com/crud_api/read/";
  const options = {
    method: 'GET', // *GET, POST, PUT, DELETE, etc.
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'omit', // include, *same-origin, omit
    headers: {
      'Content-Type': 'application/json'
      // 'Content-Type': 'application/x-www-form-urlencoded',
    },
  };

  // fetch the API
  fetch(url, options)
      // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          const errorMsg = 'Database response error: ' + response.status;
          console.log(errorMsg);
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.innerHTML = errorMsg;
          tr.appendChild(td);
          resultContainer.appendChild(tr);
          return;
      }
      // valid response will have json data
      response.json().then(data => {
          console.log(data);
          for (let row in data) {
            // tr and td build out for each row
            const tr = document.createElement("tr");
            const name = document.createElement("td");
            const id = document.createElement("td");
            // data is specific to the API
            name.innerHTML = data[row].name; 
            id.innerHTML = data[row].email; 
            // add HTML to container
            tr.appendChild(name);
            tr.appendChild(id);
            resultContainer.appendChild(tr);
          }
      })
  })
  // catch fetch errors (ie ACCESS to server blocked)
  .catch(err => {
    console.error(err);
    const tr = document.createElement("tr");
    const td = document.createElement("td");
    td.innerHTML = err;
    tr.appendChild(td);
    resultContainer.appendChild(tr);
  });
</script> -->
