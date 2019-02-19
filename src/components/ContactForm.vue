<template>
  <div>
    <h3>Contact Form</h3>
    <div class="row">
      <form @submit.prevent="sendEmail" class="col s12">
        <div class="row">
          <input type="text" v-model="name" required>
          <label>Name</label>
        </div>
        <div class="row">
          <input type="email" v-model="email" required>
          <label>Email</label>
        </div>
        <div class="row">
          <input type="text" v-model="subject" required>
          <label>Subject</label>
        </div>

        <div class="row">
          <input type="text" v-model="message" required>
          <label>Message</label>
        </div>
        <button type="submit" class="btn">Create</button>
        <router-link to="/" class="btn grey">Cancel</router-link>
      </form>
    </div>
  </div>
</template>

<script>
// const sgMail = require("@sendgrid/mail");
// sgMail.setApiKey("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");
// const nodemailer = require("nodemailer");
// var transporter = nodemailer.createTransport({
//   service: "gmail",
//   auth: {
//     user: "GerJTolan@gmail.com",
//     pass: "TYD24gmailTWO"
//   }
// });
// const send = require('gmail-send')({
// //var send = require('../index.js')({
//   user: 'GerJTolan@gmail.com',
//   // user: credentials.user,                  // Your GMail account used to send emails
//   pass: 'TYD24gmailTWO',
//   // pass: credentials.pass,                  // Application-specific password
//   to:   ['GerJTolan@gmail.com', 'tolangerard@gmail.com'],
//   // to:   credentials.user,                  // Send to yourself
//                                            // you also may set array of recipients:
//                                            // [ 'user1@gmail.com', 'user2@gmail.com' ]
//   // from:    credentials.user,            // from: by default equals to user
//   // replyTo: credentials.user,            // replyTo: by default undefined
//   // bcc: 'some-user@mail.com',            // almost any option of `nodemailer` will be passed to it
//   subject: 'test subject',
//   text:    'gmail-send example 1',         // Plain text
//   //html:    '<b>html text</b>'            // HTML
// });

export default {
  name: "ContactForm",
  data() {
    return {
      name: null,
      email: null,
      subject: null,
      message: null
    };
  },
  methods: {
    sendEmail() {
      console.log("send email");
      const mailOptions = {
        from: "sender@example.com",
        to: "Gerard Tolan <tolangerard@gmail.com>, gjtolan@gmail.com",
        subject: `hello world sendgrid ${this.subject}`,
        html: "<h1>`hello world sendgrid ${this.message}`</h1>"
      };
      //   const msg = {
      //     from: "sender@example.com",
      //     to: "Gerard Tolan <tolangerard@gmail.com>, gjtolan@gmail.com",
      //     subject: `hello world sendgrid ${this.subject}`,
      //     html: "<h1>`hello world sendgrid ${this.message}`</h1>"
      //   };
      //   sgMail.send(msg);
    //   transporter.sendMail(mailOptions, function(err, info) {
    //     if (err) console.log(err);
    //     else console.log(info);
    //   });
      console.log("send email", msg);
    }
  }
};
</script>

<style scoped>
</style>