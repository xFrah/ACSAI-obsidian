![](../z_images/Pasted%20image%2020240113142942.png)


The following is an example of acces control matrix, so we can rule it off:

![](../z_images/Pasted%20image%2020240113145356.png)

The following is an example of access control list:

![](../z_images/Pasted%20image%2020240113145542.png)

The access control list are per-file.
The clearances are basically roles. So what remains is capability list, which list the capabilities for each subject, and not per-file:

![](../z_images/Pasted%20image%2020240113145725.png)

---

![](../z_images/Pasted%20image%2020240113150211.png)

The following is DAC, which lets specific entities access other specific entities through an access control matrix.

![](../z_images/Pasted%20image%2020240113150559.png)

ABAC is based on attributes of the subjects, RBAC is based on the roles of the subjects and MAC.

MAC stands for Mandatory Access control and this is its definition:

![](../z_images/Pasted%20image%2020240113151210.png)

MAC differs from RBAC because MAC is hyerarchical, while RBAC is more specific.


> [!faq]
> Think of MAC like a simplified version of the US Government classification system -- you have Confidential, Secret, Top Secret for example. If one only has a Confidential clearance, they may not access secret or top secret, but when one has a Top Secret clearance they may receive access to documents on all levels. One key element of MAC though is that it's handled centrally and enforced by the computer system -- so users, sysadmins etc cannot escalate privileges on their own without approval by the central authority of the organization.
>
> In contrast, a role-based access control would be more granular. For example, if using role-based access control, someone working for the US Government in Human Relations would have access to memos, dossiers and other information on employees as their position requires. However, they wouldn't have access to other information at the same classification level that is outside of their scope of work -- like, financials for equipment purchases. So, role-based access control limits the scope of information.

---

![](../z_images/Pasted%20image%2020240113195756.png)


These are the properties and their name:

![](../z_images/Pasted%20image%2020240113200002.png)

in other words:
- One way or preimage resistant: Computationally infeasible to find original code from the hash.
- Second preimage resistant: For any original code y, its computationally infeasible to find another original code with the same hash.
- Collision resistant: Computationally infeasible to find any pair of original codes with the same hash.

---

![](../z_images/Pasted%20image%2020240114113557.png)


These are the countermeasures

![](../z_images/Pasted%20image%2020240114115544.png)

I think DOM is object oriented sql programming in the server side, so that the programmer or code is not exposed to raw SQL, thus preventing mistakes and providing strong type checking and sanitization for input.

---

![](../z_images/Pasted%20image%2020240114121425.png)


![](../z_images/Pasted%20image%2020240114122138.png)


This is the algorithm:

![](../z_images/Pasted%20image%2020240114141447.png)


The first two answers are a description of RSA. The other two are correct. Diffie-Hellman involves computing logarithms, not factoring large prime numbers.

---
## RSA explanation

Based on the notion that a product of two large prime numbers cannot be easily factored to determine the two prime numbers.
That is, going from results (the product of prime numbers) to inputs (prime numbers) is a nearly impossible task.

The server chooses two prime numbers, p and q. Let N be p * q.
Then the server computes $e$ and $d$, which are basically the public and private keys.

What we want is to let the client encrypt the data using this formula:

$$\large\text{cypher} = \text{message}^e \;\% \;N$$
So server sends N and $e$ to the client.
Then the server can decrypt using this formula:

$$\large\text{message} = \text{cypher}^d \;\%\; N$$

The security comes from the fact that we only share N and e and its difficult to compute d without knowing p and q.

> [!tldr]
> **Encryption for Confidentiality**:
> 
> - **Sender**: Encrypts the data with the recipient's public key.
> - **Recipient**: Decrypts the data with their own private key.
> 
> 
> **Digital Signature for Authentication**:
> 
> - **Sender**:
>     - Generates a hash (fixed-size value) of their message.
>     - Encrypts the hash with their own private key, creating a digital signature.
> - **Recipient**:
>     - Decrypts the signature with the sender's public key to recover the hash.
>     - Generates a new hash from the received message and compares it with the decrypted hash.
>     - If the hashes match, it confirms that the message was signed by the sender and has not been tampered with.

![](../z_images/Pasted%20image%2020240114202016.png)

---

![](../z_images/Pasted%20image%2020240114214052.png)


HMAC stands for **Hash-based Message Authentication Code**.
We use a secret key and a cryptographic hash function to create a message authentication code.
HMAC can be used to verify both the data integrity and the authenticity of a message.

Basically we combine the key with the message and we hash it.
The thing is that if both parties know the secret key, then one can know that the message has **not been modified** and that the certification comes from the **right client**.

> [!note]
> Has been chosen as the mandatory-to-implement MAC for IP security.

---

![](../z_images/Pasted%20image%2020240114215501.png)

**Blind SQL injection:**

1. **BENCHMARK**: This is a MySQL function that can be used to measure the time it takes to execute an expression a certain number of times. In the context of Blind SQLi, an attacker could use it to cause a deliberate delay in the database response. This delay can indicate a 'true' condition when the attacker is probing the database with yes/no questions.
    
2. **SLEEP**: Similar to BENCHMARK, the SLEEP function is used to delay the response from the database. It's a clearer indication since it pauses for a specific amount of time. If the attacker receives a delayed response, they know that the SQL query executed successfully.
    
3. **IF**: This is a control flow function that returns a value based on a condition. In Blind SQLi, the IF function can be used to test for true or false conditions in the database, triggering different behaviors that the attacker can observe.
    
4. **SUBSTRING**: The SUBSTRING function is used to extract a portion of a string (like a piece of data from the database). In Blind SQLi, an attacker can use SUBSTRING to systematically retrieve information one piece at a time by changing the position (pos) and length (len) parameters.

**Tautology:**

![](../z_images/Pasted%20image%2020240114221908.png)


**UNION operator:**
We use union to get access to other tables, other than the legitimate one.
The attacker uses the UNION operator to combine the results of the original query with another SELECT query from another table.


**Second-order inject:**
We legitimately insert shit in the db that enables us to do injection later with another legitimate query. For example a crafted name in the registration of the account.

---

## Cross-site shit

**Cross site request forgey**: since when we make a request to a website, the credentials or token gets sent automatically, another malicious website could make us do a request to the other website using our authentication.

**Reflected cross-site scripting**