
**Salting** is a security technique used when storing passwords to make them much harder to crack.

### The simple idea

Instead of storing a password (or even just its hash) by itself, you:

1. Take the password
    
2. Add a **random value** called a _salt_
    
3. Hash the combination
    
4. Store the **salt + hash**
    

So even if two users have the **same password**, their stored hashes will be different.