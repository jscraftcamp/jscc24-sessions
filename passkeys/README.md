# Passkeys

- Hosted by [Clemens Hübner](https://github.com/jscraftcamp/website/blob/main/participants/clemens.json)

## The problem of passwords

- Passkeys try to solve the problem of passwords (think of user + password login mask)
- Passwords are not really usable (users):
  - Leaks, phising
  - Passwords too long
  - Different passwords required for each website
  - Password managers yet another annoying piece of software to use
  - We all hate 2 Factor Authentication (2FA)
    - 2FA still vulnerable to phising
- Passwords are a problem for devs:
  - Hashing & encryption
  - Ensure that they are not read in traffic
  - We need to do 2FA nowadays

## Authentication methods

- Things that you know (e.g. a password) vs things that you possess (the key of your car, a yubikey, your phone, some biometric data, etc)

## WebAuthn

- [Web](https://webauthn.io/)
- Do not auth with a password but with a biometric feature or some piece of hardware
- The dev should not have to implement these things but use WebAuthn instead
- Uses public key authentication, so there is no need to transfer a symmetric key through the wire
- WebAuthn is not that cool any more, the cool new guy in the block is `Passkeys`

### Tech details of WebAuthn

- WebAuthn is a browser API that sits between the browser and the application
  - Meaning that WebAuthn is basically installed in every modern browser!
- WebAuthn defines two ceremonies
  - Registration ceremony: new user needs to be registered and presents their hardware key
  - Authentication ceremony: existing user comes back and presents their hardware key
    - The server sends a challenge to the client, the client needs to sign it with the private key of the user that wants to authenticate

## PassKey

- WebAuthn introduced in 2016, Apple in 2020
- Virtually perfect coverage
- BUT it did not really take off... not that many wbesites did implement it
  - There was still some usage of WebAuthn as a second factor -- that's just not the idea of WebAuthn!
  - Passwords are bad and all, but everyone understands them and are easy to use.
  - Who has a YubiKey? Can you eat a YubiKey?
  - Understandable WebAuthn (based on biometric data) are not really portable, since the private key exists just in the machine where it was created (think Apple Touch ID)
- Under the hood, Passkeys are still WebAuthn
  - They just add **usability** improvements to basic WebAuthn!
  - e.g. they are stored in your google account and are synced across devices
    - Google & Apple already do the syncing across devices,
    - Microsoft is not there yet
  - **Privacy concerns** are valid, but the usability gains are undeniable
- Very fast, widespread adoption of Passkeys (as opposed to WebAuthn, which never got going)
- Importantly: the website that offers authentication via Passkeys (e.g. [shopify.com](shopify.com)) **does not care about which Passkey implementation/manager you use**.
  Depending on how the user has configured their Passkey manager (is it google, apple, bitwwarden, etc), they will be prompted to use one or another.

## Implementing it

- There are already a few providers for Passkeys
  - [Corbado](https://corbado.com/#signup-init)
  - [Ory](https://www.ory.sh/)
  - etc

## Other Topics

### Are YubiKeys a passkey?

- They are never synced, so they cannot be Passkeys.
  They are WebAuthn by definition: if they cannot be synced, they are not PassKeys.

### Are PassKeys 2FA?

- Yes, they are considered 2FA by themselves.
  They are implemented in such a way that you must have (1) the device and (2) the access to the device (e.g. via some biometric data)
