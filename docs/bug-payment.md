User story
- As a customer, I want to complete a payment with a valid payment method so that my order is confirmed and I receive a receipt without delays.

Acceptance criteria
- [ ] Given a valid payment method and a successful authorization from the PSP, when the user confirms checkout, then the API responds 200/201 within 3s and the order status becomes "paid" (or equivalent) with a payment_id recorded.
- [ ] A payment confirmation page is shown with order number and receipt details; a confirmation email is sent (if applicable).
- [ ] Invalid/declined cards return 402/400 with a generic error (no sensitive details) and the order remains unpaid.
- [ ] Idempotency is enforced: retrying the same checkout request does not create duplicate charges or orders.
- [ ] Webhooks are verified (signature/secret) and update order/payment status exactly once; failed webhook deliveries are retried safely.
- [ ] If 3-D Secure/SCA is required, the challenge flow completes and the user is returned to the app with the payment finalized.
- [ ] Errors are logged with correlation IDs; sensitive PAN/CVV never logged.

Optional
- Affected envs:
- Steps to reproduce:
- Logs/screenshots:
