# Conditional Access, MFA, and SSO in Microsoft Entra

This lesson covers how to secure access to organizational resources using Conditional Access, enforce strong authentication through Multi-Factor Authentication (MFA), and provide a seamless user experience with Single Sign-On (SSO).

---

## What is Conditional Access?

Conditional Access is a policy-based system in Azure AD that allows or denies access to applications based on specific conditions.

### Core Components:
- **Conditions**: Define who, where, and how access is attempted.
- **Controls**: Specify what must be met to grant access (e.g., MFA, compliant device).

---

## How Conditional Access Works

1. **Target Users & Applications**:
   - Target all or specific users, groups, or roles.
   - Apply policies to all or selected cloud applications.

2. **Define Conditions**:
   - Location (IP ranges, GPS, countries)
   - Device platform and state
   - Client application (browser, mobile app, etc.)
   - Sign-in risk level (requires Azure AD Premium P2)

3. **Access Controls**:
   - Require multi-factor authentication (MFA)
   - Require compliant devices (managed via Intune)
   - Require hybrid Azure AD join
   - Enforce password changes or Terms of Use acceptance
   - Restrict access to approved applications only

4. **Enforcement**:
   - Grant or block access based on whether conditions and controls are met.
   - Choose whether **all** or just **one** control must be satisfied.

---

## Multi-Factor Authentication (MFA)

### What is MFA?
A security mechanism requiring two or more types of verification:
- Something you know (e.g., password, PIN)
- Something you have (e.g., phone with authenticator app, token)
- Something you are (e.g., fingerprint, face scan)

### Supported MFA Methods:
- Authenticator app (Microsoft Authenticator)
- SMS messages
- Phone calls
- Hardware tokens
- Windows Hello for Business

### Licensing:
- **Free**: Limited to Authenticator app via security defaults
- **Premium (P1/P2)**: Full Conditional Access control and broader method support

### Best Practices:
- Apply MFA based on risk, not on every login
- Avoid user fatigue with targeted MFA prompts
- Combine with device compliance and user roles

---

## Single Sign-On (SSO)

### What is SSO?
A capability that enables users to authenticate once and access multiple applications without re-entering credentials.

### Key Concepts:
- SSO uses tokens issued at login to grant access to other applications.
- Each app access still goes through Conditional Access policies.
- Reduces repeated logins while maintaining security compliance.

---

## Conditional Access + MFA + SSO Workflow

1. User authenticates with Azure AD
2. Conditional Access policies are evaluated:
   - Is MFA needed?
   - Is the device trusted and compliant?
   - Is the sign-in risk acceptable?
3. If required, user completes MFA
4. User receives authentication and access tokens
5. Access to multiple apps is enabled via SSO
6. MFA or other requirements may be re-applied if policy demands it

---

## Summary Table

| Feature              | Purpose                                         | Licensing                   |
|----------------------|-------------------------------------------------|-----------------------------|
| Conditional Access   | Control access based on user, device, and risk  | Azure AD Premium P1 or P2   |
| MFA                  | Ensure strong user authentication               | Free (limited) or P1/P2     |
| SSO                  | Seamless access across trusted applications     | Built-in with Azure AD      |

---

## Key Takeaways

- Conditional Access is used to define policies that govern access.
- MFA adds a second (or more) layer of identity verification.
- SSO improves user experience without reducing security.
- Premium licensing (P1/P2) enables fine-grained control and advanced security features.

---

This concludes the lesson on Conditional Access, MFA, and SSO in Microsoft Entra.
