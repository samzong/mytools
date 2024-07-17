# Auto Active GV Number

## Use Case

create an script with [script.google.com](https://script.google.com), and paste the code below.

```javascript
function auto_reply() {
    const subject = 'GoogleVoice Keep Alive';
    const my_phone = '123 456 7890'; // 1st, Your Google Voice Number
    const my_email = Session.getActiveUser().getEmail();
    const target_phone = '098 765 4321'; // 2nd, The Number you want to send to

    // From the first number to the second number's email address
    // You need to enable the forward to email feature in Google Voice
    // After receiving a message, you will be able to see this address
    const target_email = '1234567890.0987654321.Tgm-CmsDkJ@txt.voice.google.com';

    const html_body = `
        <h1>Google Voice Keep alive</h1>
        <p>My email is:${my_email} </p>
        <p>My phone number is:${my_phone}</p>
        <p>This is from ${my_phone} send to ${target_phone} message</p>
        <p>Send weekly, keep alive once</p>
    `;

    // text content
    const text_body = `Google Voice Keep Alive, my email is: ${my_email}, my phone number is: ${my_phone}. This is a message sent from ${my_phone} to ${target_phone}, sent weekly to keep alive.`;

    MailApp.sendEmail({
        to: target_email,
        subject: subject,
        htmlBody: html_body,
        body: text_body,
    });
}
```

Then, set a trigger to run this function every week.

## Special Instructions

This script is from the internet, but I forgot the original author. If you are the original author, please contact me, and I will credit you.
