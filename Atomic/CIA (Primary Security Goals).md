### Confidentiality

Confidentiality means only authorized people or systems can access certain information.

**Why it matters:**

- Legal requirements, such as GDPR, require organizations to protect personal data.
- It prevents attackers from gaining access to sensitive information.
- It's often the property people care about most instinctively (e.g., not wanting private messages read by strangers).

We're usually protecting either personal data or organizational data that shouldn't reach the public. For example, when you message a friend, you don't want anyone else to read it. This is why apps like WhatsApp use end-to-end encryption: only the sender and receiver can read the message, not even the app provider.

Confidentiality builds trust: people use a system because they believe it keeps their data away from anyone not authorized to see it.

**Tools used to achieve confidentiality:**

_Encryption_ You can't trust a network, since anyone can intercept traffic on it. Encryption protects a message by scrambling it mathematically so that anyone who intercepts it can't understand it. The recipient uses a matching key or algorithm to reverse the process and recover the original message.

_Access Control_ Restricting who can access specific data, based on permissions, roles, time of access, or other conditions. For example, only HR staff can view salary records, and only during working hours.

_Authentication_ The process of verifying that someone is who they claim to be, before granting access. Common methods include passwords, biometrics, and security tokens.

_Authorization_ Once someone is authenticated, authorization determines what they're allowed to do. Authentication answers "who are you?", authorization answers "what can you do?"

_Physical Security_ Protecting the physical hardware and premises where sensitive data lives, so that confidentiality can't simply be bypassed by walking up to a machine. Examples:

- TPM (Trusted Platform Module) chips and other secure hardware that store cryptographic keys.
- Biometric locks like fingerprint or face recognition.
- Security guards, alarms, and locked server rooms at facilities storing sensitive data.

### Integrity

Integrity means preventing unauthorized modification of information or resources.

- **Data integrity** concerns the content of information: has it been changed without permission?
- **Origin integrity** concerns the source of information: did it really come from who it claims to come from? This overlaps with authenticity, since verifying the origin requires authenticating the source.

In many commercial systems, integrity matters more than confidentiality. A bank cares more about nobody tampering with account balances than about those balances staying secret.

**Hashing** When sending a file, you can generate a hash: a fixed-length string produced by running the file through a mathematical function (like SHA-256). Even a tiny change to the file produces a completely different hash. The hash acts as a fingerprint you can use to confirm the file wasn't altered.

When a file is downloaded or transferred, you hash the received copy and compare it to the original, known hash. If they match, the file wasn't tampered with in transit.

Performance also matters. Hashing large files or doing it constantly costs processing time, so systems often use hybrid approaches, such as hashing only chunks of data or combining hashing with lighter checks, to balance security and speed.

**Prevention vs. detection mechanisms:**

- _Prevention mechanisms_ stop unauthorized modification before it happens, for example, preventing a bank's janitor from editing account records. They don't stop someone with legitimate access from misusing it, like a bank manager transferring funds to their own account.
- _Detection mechanisms_ don't stop unauthorized changes, but they catch them after the fact, so both scenarios above can be identified and corrected.

### Availability

Availability means systems and information are accessible to authorized users whenever they need them.

Attacks that target availability are called **Denial-of-Service (DoS)** attacks. A well-known example was Xbox Live going down on Christmas morning due to an attack, disrupting the day for millions of users.

Availability is one of the hardest properties to guarantee, and most security research historically has focused on confidentiality and integrity instead, largely because those two are comparatively easy: simply unplug the system and lock it in a vault, and both are guaranteed (at the cost of making the system useless). Availability doesn't have that shortcut, since the whole point is that the system stays usable.

**Why it's difficult:**

- It's hard to distinguish a real DoS attack from a normal spike in legitimate traffic.
- Availability can be affected by factors outside the security model entirely, for example, a construction crew accidentally cutting a power or network cable.

**Load balancing** is one common defense: distributing incoming traffic across multiple servers so no single machine is overwhelmed. This helps absorb both legitimate traffic spikes and some attack traffic, and it also means a failure in one server doesn't take the whole system down.

## Other Commonly Listed Security Goals

### [[AAA Security Framework]]
* **Assurance:** Establishing and maintaining trust that a system is secure and users are who they claim to be.
* **Authenticity:** Verifying that a statement or action genuinely originated from its claimed source without alteration.
* **Anonymity:** Ensuring that actions, requests, or transactions cannot be traced back to a specific individual.

### [[Privacy]]
The right of individuals to control how their personal information is collected, used, and shared.