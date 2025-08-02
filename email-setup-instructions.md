# Email Setup Instructions for Contact Form

## Option 1: Formspree (Recommended - Free)

1. Go to [Formspree.io](https://formspree.io) and create a free account
2. Create a new form
3. Copy your form endpoint URL (it will look like `https://formspree.io/f/xqkoyqkq`)
4. Replace `YOUR_FORM_ID` in the `index.html` file with your actual form ID

**In index.html, line ~540, change:**
```html
<form id="contactForm" class="space-y-6" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```
**To:**
```html
<form id="contactForm" class="space-y-6" action="https://formspree.io/f/xqkoyqkq" method="POST">
```

## Option 2: EmailJS (Alternative)

1. Go to [EmailJS.com](https://www.emailjs.com) and create a free account
2. Set up an email service (Gmail, Outlook, etc.)
3. Create an email template
4. Get your User ID, Service ID, and Template ID
5. Replace the placeholders in `script.js`

## Option 3: Current Fallback (No Setup Required)

The current implementation will:
1. Try to submit to Formspree if configured
2. If Formspree fails or isn't configured, it will open the user's default email client
3. Pre-fill the email with the form data

## Testing the Contact Form

1. Fill out the contact form on your website
2. Click "Send Message"
3. If Formspree is configured, you should receive an email
4. If not configured, your default email client should open with a pre-filled email

## Troubleshooting

- **Form not submitting**: Check that the form action URL is correct
- **Email client not opening**: Some browsers block popups, allow popups for your site
- **No email received**: Check your spam folder or verify the Formspree configuration

## Security Notes

- Formspree is a trusted service used by many websites
- The fallback mailto method is completely client-side and secure
- No sensitive data is stored on your website 