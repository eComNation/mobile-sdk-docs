## 9. Contact Us

###Files/Classes

1. ContactUsController

###Description

The contact us screen has three sections,

1.	Support phone number for the store is mentioned in the first section, with an option to make a call from the app by tapping the phone icon.

2.	Second section displays Store’s support email address, a tap on the mail icon opens the default mail composer.

3.	The third section is a form which accepts different inputs from the customer like Name, Email, Phone and Comments. This info can then be submitted with a POST request to **SUBMIT FEEDBACK URL**.

<aside class="notice">
SUBMIT FEEDBACK URL:<br/>
https://abcd.my39shop.com/api/v1/store/contact_us?email={email_value}&subject=Feedback&fields[name]={name_value}&fields[phone]={phone_value}&fields[note]={comments_value}
</aside>