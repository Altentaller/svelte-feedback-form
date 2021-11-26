Feedback form with sending data to email (built with Svelte + PHPMailer). 


## Getting Started

```bash
npm install
```

Then, start Rollup:

```bash
npm run dev
```

## Function for sending data
Sendind POST data using XMLHttpRequest.

<a href="https://github.com/PHPMailer/PHPMailer">PHPMailer</a> is used to send data to email.

Upload PHPMailer library to your server and change link on handler in file -> src/Block/Form.svelte

```bash
XHR.open( "POST", "https://your-domain.com/mailer/smart.php" );
```

## Screenshot
![alt text](https://raw.githubusercontent.com/Altentaller/svelte-feedback-form/master/screen.png "screenshot")