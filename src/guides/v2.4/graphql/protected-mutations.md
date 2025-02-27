---
group: graphql
title: Protected mutations
---

If CAPTCHA or reCAPTCHA is enabled on pages requiring shopper input, then in most cases, the corresponding mutations that send requests to the Magento server must include an HTTP header that contains a value entered by the shopper (for CAPTCHA) or generated by the Google API (for reCAPTCHA). However, if you specify an integration authorization token in the header of the mutation, then you do not supply a header specific to CAPTCHA or reCAPTCHA.

The HTTP `X-Captcha` and `X-ReCaptcha` headers:

*  Cannot be received by an automated script or a non-UI API call. They are captured and returned by the UI Web form only.
*  Are optional in protected mutation API calls that provide **_integration authorization_** tokens only. They cannot be skipped when you provide an Admin or Bearer token.

## CAPTCHA

The following table lists the forms that can be configured to require CAPTCHA. Go to **Stores** > **Configuration** > **Customers** > **Customer Configuration** > **CAPTCHA** > **Forms** to enable or disable CAPTCHA on these forms.

The mutation that corresponds to a CAPTCHA-enabled form must include the HTTP `X-Captcha` header, along with the text the shopper entered in response to the CAPTCHA challenge.

Form name | Mutation
--- | ---
Add Gift Card Code | `applyGiftCardToCart`
Applying Coupon Code | `applyCouponToCart`
Change password | `changeCustomerPassword`
Checkout/Placing Order | `setPaymentMethodOnCart`, `setPaymentMethodAndPlaceOrder`
Contact Us | Not applicable
Create company | Not applicable
Create user | `createCustomer`
Forgot password | Not applicable
Login | `generateCustomerToken`
Payflow Pro |  `setPaymentMethodOnCart`, `setPaymentMethodAndPlaceOrder`
Send to Friend Form | `sendEmailToFriend`
Share Wishlist Form | Not applicable

## reCAPTCHA

The following table lists the forms that can be configured to require reCAPTCHA. Go to **Stores** > **Configuration** > **Security** > **Google reCAPTCHA Storefront** > **Storefront** to enable or disable reCAPTCHA on these forms. If reCAPTCHA is enabled, unless an integration token is provided, always specify the HTTP `X-ReCaptcha` header and the value generated by the Google API.

Field name | Mutation
--- | ---
Enable for Customer Login | `generateCustomerToken`
Enable for Forgot Password | `changeCustomerPassword`
Enable for Create New Customer Account | `createCustomer`, `createCustomerV2`
Enable for Edit Customer Account | `updateCustomer`, `updateCustomerV2`
Enable for Contact Us | Not applicable
Enable for Product Review | `createProductReview`
Enable for Newsletter Subscription | `subscribeEmailToNewsletter`
Enable for Send To Friend | `sendEmailToFriend`
Enable for PayPal PayflowPro payment form | `createPayflowProToken`
Enable for Braintree payment form | Not applicable
Enable for Checkout/Placing Order | `setPaymentMethodOnCart`, `setPaymentMethodAndPlaceOrder`
Enable for Coupon Codes | `applyCouponToCart`

{:.ref-header}
Related topics

[Construct a request]({{page.baseurl}}/get-started/gs-web-api-request.html)
