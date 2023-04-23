---
layout: post
title:  "Enhancing Your Security: Strengthening Azure AD with FIDO2 Keys"
author: plamber
categories: [ Security ]
tags: [Microsoft 365]
featured: false
---
I recently got our hands on the "BioPass FIDO2" USB-C Biometric key from Feitian [from Feitian](https://www.ftsafe.com/products/FIDO/BIO), and I am happy to report that it's an excellent addition to my arsenal of security tools. Therefore, today, I want to talk about a solution that can enhance the security of your organization's digital identity and reduce the risk of cyber attacks – FIDO keys in conjunction with Azure AD.

As we all know, passwords are the most common way to secure our digital identities. However, using passwords as the sole method of authentication can be risky, as they can easily be hacked, stolen or guessed. To overcome this problem, many organizations have turned to multi-factor authentication (MFA), which adds an extra layer of security beyond passwords.

Although MFA is a great solution, it is not bulletproof. In fact, even MFA solutions can be vulnerable to phishing attacks, social engineering and other types of attacks that compromise users' identities. This is where FIDO keys come into play.

Mobile phone-based MFA is a common and convenient MFA technique that involves using a user's mobile phone as a second factor of authentication. This method typically involves sending a one-time passcode (OTP) to the user's phone via SMS or a mobile app, which the user then inputs into the authentication prompt to gain access. While this method is convenient, it can be vulnerable to SIM swapping attacks or attacks on the user's mobile device itself.

Trusted devices with Intune is another MFA technique that leverages Microsoft's Intune mobile device management platform. This method allows users to register their trusted devices, such as their personal mobile phone or laptop, with their organization's Intune platform. Once registered, the user can use these devices to authenticate themselves to access corporate resources. This method is more secure than traditional password-based authentication, as it requires possession of the registered device, but it can be vulnerable to device theft or compromise.

FIDO keys come into play when organizations need an even stronger level of security beyond traditional MFA methods. FIDO keys are physical devices that generate unique cryptographic keys that cannot be replicated. These keys are used as a second factor of authentication, providing an extra layer of security that is not easily compromised. FIDO keys are able to protect against phishing attacks and social engineering attacks, as they require physical possession of the key to authenticate. In addition, FIDO keys are not susceptible to malware attacks or hacking attempts, making them a highly secure form of authentication.

FIDO keys work by utilizing a public-key cryptography protocol that allows for secure and private authentication. When a user inserts their FIDO key into a computer or mobile device, the device generates a cryptographic key pair that is unique to that device. The private key is stored securely on the FIDO key itself, while the public key is registered with the user's online account. When the user attempts to log in to their account, the website or application sends a challenge to the FIDO key, which uses the private key to sign the challenge and send the signed response back to the website or application. The website or application then verifies the response and grants access if it is valid.

### Enabling FIDO Keys for users

To enable the use of FIDO keys for users, Azure AD administrators must configure a few settings. First, they need to enable the use of FIDO keys in the Azure AD tenant.

To do this, navigate to the Azure AD portal and select "Security" from the left-hand menu. From there, select [Authentication methods](https://portal.azure.com/#view/Microsoft_AAD_IAM/AuthenticationMethodsMenuBlade/~/AdminAuthMethods) and then "FIDO2 Security Key." Toggle the option to "On" to allow your users to use FIDO keys.

![](../../assets/images/2023-04-23.png)

### Setting up FIDO as a user

To begin using a FIDO key, the first step is to confirm that the device supports FIDO2 keys. Once confirmed, the user can insert the FIDO key into the USB port and follow the instructions provided by the manufacturer. In our case, we received the BioPass FIDO2 USB-C Biometric key from Feitian, and we followed their setup guide.

To configure the BioPass FIDO2 key, we navigated to the [Security info page](https://mysignins.microsoft.com/security-info) and selected "Security key" as the sign-in method. The wizard then guided us through the necessary steps to finalize the configuration. Once complete, the BioPass FIDO2 key can be used as an additional authentication method or set as the default method.

![](../../assets/images/2023-04-23-2.png)

### Summary

In summary, while traditional passwords and MFA methods can be vulnerable to various types of attacks, FIDO keys provide a highly secure form of authentication that is not easily compromised. They are easy to use and provide an extra layer of security that can protect against a wide range of attacks, making them an excellent solution for organizations of all sizes.

