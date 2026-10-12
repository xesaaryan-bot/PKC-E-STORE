# YourStore — bilingual e-commerce starter

This is a starter template, not a production-ready store. It includes a responsive product grid, cart, checkout form, and a server-side Razorpay order/signature-verification example.

## Files
- `index.html` — storefront and cart
- `api/create-order.js` — calculates totals using server-side prices and creates a Razorpay order
- `api/verify-payment.js` — verifies the checkout signature
- `vercel.json` — deploys the static site and API routes on Vercel

## Important before launch
1. Replace `YOURSTORE` and demo product names, descriptions, prices, and emoji in `index.html`.
2. Update the `catalog` object in `api/create-order.js` to exactly match your products and prices.
3. Add your legal business name, support email/phone, shipping policy, return/refund policy, privacy policy, and terms.
4. Create a Razorpay account and complete any requested business/KYC checks.
5. In Vercel project Settings → Environment Variables, add:
   - `RAZORPAY_KEY_ID` = your Razorpay Key ID
   - `RAZORPAY_KEY_SECRET` = your Razorpay Key Secret
   Use TEST keys first. Never put the secret in `index.html` or expose it to visitors.
6. Deploy to Vercel. Test checkout in Razorpay Test Mode before switching to Live keys.
7. Before taking real orders, add a database to store orders and customer details, verify payment status server-side, and set up Razorpay webhooks. Signature verification alone is not the whole order-management system.

## Deploy (no custom domain required)
1. Create/sign in to GitHub and make a new repository.
2. Upload all files while preserving the `api` folder and `vercel.json`.
3. Create/sign in to Vercel and import the GitHub repository.
4. Add the environment variables above in Vercel settings.
5. Deploy. Vercel will provide a temporary `*.vercel.app` URL.
6. In Razorpay, keep Test Mode keys first and test both success and failure flows.

## Budget
A basic deployment can use a free hosting tier and a free `vercel.app` subdomain. A custom domain, payment gateway fees, packaging, courier, taxes/compliance, and any database over free limits may cost extra. Check current provider terms before launch.

## Limitations
- Demo products only; no database, stock management, automated shipping, refund workflow, or email/SMS notifications are included.
- The sample verification function returns a reference but does not persist the order. Do not ship goods based only on the browser's success message.
- Add rate limiting, server-side payment-status checks/webhooks, order persistence, input validation, privacy controls, and policy pages before accepting real customer payments.
