# Medicos_final
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login </title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:ital@1&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="loginWCE.css">
    <script src="https://kit.fontawesome.com/3dc4137c7c.js" crossorigin="anonymous"></script>

</head>
<body>
    <div class="container">
        <div class="form-box">
            <h1 id="title">Login</h1>
            <form>
                <div class="input-group">
                   <div class="input-field"id="nameField">
                    <i class="fa-solid fa-user"></i>
                    <input type="text"  placeholder="Name">

                 </div> 

                    <div class="input-field" id="emailField">
                        <i class="fa-solid fa-envelope"></i>
                     <input type="email" placeholder="Email">
                    </div> 

                    <div class="input-field" id="passwordField">
                        <i class="fa-solid fa-lock"></i>
                        <input type="Password" placeholder="password">
                    </div> 
                    <p>Lost password      <a href="#">Click Here!</a></p>
                </div>
                <div class="btn-field">
                   <button type="button"id="loginBtn">Login</button>
                   <button type="button"id="signinBtn"class="disable">Sign in</button>
                  
                </div>

            
                
                 
            </form>
        </div>
     
    </div>
    <script>
        let loginBtn = document.getElementById("loginBtn");
        let signinBtn = document.getElementById("signinBtn");
        let nameField = document.getElementById("nameField");
        let title = document.getElementById("title");
    
    
        signinBtn.onclick = function(){
          nameField.style.maxHeight="0";
          title.innerHTML ="Sign In";
          loginBtn.classList.add("disable");
          signinBtn.classList.remove("disable")
    
           }
        loginBtn.onclick = function(){
          nameField.style.maxHeight="60px";
          title.innerHTML ="Login";
          loginBtn.classList.remove("disable");
          signinBtn.classList.add("disable")
    
           }

    </script>
     <script type="module">
        // Import the functions you need from the SDKs you need
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.9.0/firebase-app.js";
        import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.9.0/firebase-analytics.js";
        import{ getDatabase} from "https://www.gstatic.com/firebasejs/10.9.0/firebase-analytics.js";
        import { getAuth, createUserWithEmailAndPassword } from "https://www.gstatic.com/firebasejs/10.9.0/firebase/auth";
    
    
        // TODO: Add SDKs for Firebase products that you want to use
        // https://firebase.google.com/docs/web/setup#available-libraries
      
        // Your web app's Firebase configuration
        // For Firebase JS SDK v7.20.0 and later, measurementId is optional
        const firebaseConfig = {
          apiKey: "AIzaSyD45neTheAV2cklFtVNOZhEmLIowemhfsg",
          authDomain: "medicos-ad801.firebaseapp.com",
          databaseURL: "https://medicos-ad801-default-rtdb.firebaseio.com",
          projectId: "medicos-ad801",
          storageBucket: "medicos-ad801.appspot.com",
          messagingSenderId: "320471309071",
          appId: "1:320471309071:web:d5cc5ffec7bc755accfc7a",
          measurementId: "G-M9X54ZBTE3"
        };
      
        // Initialize Firebase
        const app = initializeApp(firebbaseaseConfig);
        const database=getDatabase(app);
        const analytics = getAnalytics(app);
        const auth = getAuth();
        loginBtn.addEventListener(click,(e)=>{
            var username=document.getElementById('nameField').value;
            var email=document.getElementById('emailField').value;
            var password=document.getElementById('passwordField').value;
            
            createUserWithEmailAndPassword(auth, email, password)
      .then((userCredential) => {
        // Signed up 
        const user = userCredential.user;
        alert('user created')
        // ...
      })
      .catch((error) => {
        const errorCode = error.code;
        const errorMessage = error.message;
        alert(errorMessage)
        // ..
      });
    
    
        });
      </script>
        
</body>

  </html>
</html>
