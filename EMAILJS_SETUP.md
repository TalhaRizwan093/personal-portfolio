# EmailJS Setup Instructions

Your contact form is now configured to work with EmailJS! Follow these steps to complete the setup:

## 1. Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

## 2. Add Email Service

1. In EmailJS dashboard, go to **Email Services**
2. Click **Add New Service**
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the setup instructions for your provider
5. **Copy the Service ID** - you'll need this later

## 3. Create Email Template

1. Go to **Email Templates**
2. Click **Create New Template**
3. Use this template content:

**Template Name:** Contact Form Template

**Subject:** New Contact Form Message from {{from_name}}

**Content:**
```
Hello {{to_name}},

You have received a new message from your portfolio contact form.

From: {{from_name}}
Email: {{from_email}}

Message:
{{message}}

---
This message was sent from your portfolio website contact form.
```

4. **Copy the Template ID** - you'll need this later

## 4. Get Your Public Key

1. Go to **Account** → **General**
2. Find your **Public Key**
3. **Copy the Public Key**

## 5. Update Your Code

Open `assets/js/script.js` and replace these placeholders:

```javascript
// Replace this line:
emailjs.init("YOUR_PUBLIC_KEY");
// With:
emailjs.init("your_actual_public_key_here");

// Replace this line:
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
// With:
emailjs.send('your_service_id_here', 'your_template_id_here', templateParams)
```

## 6. Test Your Form

1. Open your website
2. Fill out the contact form
3. Submit it
4. Check your email for the message
5. Verify the success message appears on the form

## Features Added:

✅ **Email Integration:** Messages sent directly to your email
✅ **Success/Error Messages:** User feedback after form submission
✅ **Loading State:** Button shows "Sending..." during submission
✅ **Form Validation:** Required fields must be filled
✅ **Auto-hide Messages:** Status messages disappear after 5 seconds
✅ **Form Reset:** Form clears after successful submission

## Free Plan Limits:

- 200 emails per month
- Perfect for a personal portfolio
- No credit card required

## Troubleshooting:

1. **Form not sending:** Check your Service ID and Template ID
2. **Not receiving emails:** Check your email service configuration
3. **Console errors:** Verify your Public Key is correct

## Security Note:

Your EmailJS keys are safe to use in frontend code - they're designed for client-side usage and have built-in rate limiting and domain restrictions.

---

**Need help?** Check the EmailJS documentation at https://www.emailjs.com/docs/