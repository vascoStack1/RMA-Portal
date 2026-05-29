# MultiSafepay RMA Portal

A self-service portal for merchants and partners to submit RMA (Return Merchandise Authorization) requests for POS terminals.

## Live
[https://craigymaster.github.io/RMA-Portal/](https://craigymaster.github.io/RMA-Portal/)

## What it does
- Merchant enters a serial number → terminal type is automatically detected via SN prefix
- Multi-step form: Devices → Contact details → Summary → Submit
- CSV upload supported for bulk RMA requests
- On submit: EmailJS automatically sends a formatted email to pos-support@multisafepay.com
- Jitbit helpdesk picks up the email and creates a support ticket automatically

## Supported terminals
| Prefix | Terminal |
|--------|----------|
| PA | P3 Air |
| P3 | P3H |
| PK | P3KH |
| PD | P2 SmartPads |
| PN | P2 Mini |
| P2 | P2 Pro |
| PC | P2 Lite SE |
| TJ | P2 SE |
| PF | P3 Mix |

Serial numbers must be exactly 13 characters long.

## Tech stack
- HTML / CSS / JavaScript (no framework)
- EmailJS for email sending
- Hosted on GitHub Pages

## Configuration
To update EmailJS credentials, edit these values in `index.html`:
```javascript
emailjs.init('YOUR_PUBLIC_KEY');
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams);
```

## Adding a new terminal type
Find the `SN_MAP` object in `index.html` and add a new entry:
```javascript
const SN_MAP = {
  'XX': 'New Terminal Name',
};
```

## Developed by
Vasco Huijsman — internship project at MultiSafepay (2026)
