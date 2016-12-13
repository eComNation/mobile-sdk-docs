## 11. Contact Us

###Files/Classes

1. ContactUsActivity

###Description

The contact us screen has three sections,

* Support phone number for the store is mentioned in the first section, with an option to make a call from the app by tapping the phone icon.

* Second section displays Store’s support email address, a tap on the mail icon opens the default mail composer.

* The third section is a form which accepts different inputs from the customer like Name, Email, Phone and Comments. This info can then be submitted with a POST request to **SUBMIT FEEDBACK URL**.

>SUBMIT FEEDBACK URL:

```API
https://abcd.my39shop.com/api/v1/store/contact_us?email={email_value}&subject=Feedback&fields[name]={name_value}&fields[phone]={phone_value}&fields[note]={comments_value}
```
