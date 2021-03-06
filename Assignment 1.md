# Assignment 1

### Part 1
 a) A small local catering company provides hot dogs served in buns at local events. The owner has to order the hot dogs and the buns and wants to ensure that however many are ordered, there are the same number of hot dogs and buns. The hot dogs usually come in packages of 8 although this can vary depending on the supplier. The buns usually come in packages of 12 but like the buns this can vary.
 
The owner would like an app that will determine the appropriate number of packages of hot dogs and buns to order, given:
* a specified minimum number of servings that must be catered for
* the number of items per package, if different from usual

Using Euclid's Algorithm in code looks as such:

int a,b,c;

cout << "Please enter the number of hot dogs that come in a single package: ";

cin >> a; 

cout << "Please enter the number of buns that come in a single package: ";

cin >> b;

c=a*b; 

while(a!=b) { 

    if(a>b) 
    
	a=a-b; 
	
    else 
    
	b=b-a; 
	
}

cout << "The minimum number of items per package if different from usual is " << a << endl; 

cout << "The minimum number of servings that must be catered for is " << c/a << endl;

By using this code, we can find out the minimum number of servings must be 24 by working out the LCM of 8 and 12.

To work out the second part, which asks for the number of items per package if different from usual, the HCF of 8 and 12 has to be calculated. The HCF of 8 and 12 is 4, so the appropriate number of items per package if different from usual would be 4.


b) At weekends there are often two events. The owner packs the buns into plastic containers. Each container has the same number of buns. If 288 buns are needed for one event and 660 buns are needed for another, determine the maximum number of buns per container so that a whole number of container can be taken to each event.
(Use Euclid's Algorithm to find the HCF)

660 = (288 x 2) + 84
288 = (84 x 3) + 36
84 = (36 x 2) + 12
36 = (12 x 3) + 0

As the remainder has been reached, the HCF of 660 and 288 is 12.

### Part 2
a) You have decided to save some money during the six week holiday. You save 1p on the first day, 2p on the second day, 3p on the second day, etc. How much will you have at the end of the holiday (42 days)?

![](https://i.imgur.com/5cp8dK4.png)

For this arithmetic sequence, this formula needs to be used, where n is 42 for the number of days/number of terms in the series, and a is 1 for the first number in our series

![](https://i.imgur.com/ZHRhLNM.png)

Once calculated, the answer comes to 903, which works out to be £9.03 saved after the holiday.



b) A friend of yours runs a charity marathon. He manages to run the first mile in 6 minutes but takes 5% longer for each subsequent mile of the 26 mile race. How long does it take him to complete the race? Give your answer to the nearest second.

First we must work out the amount of time taken to complete each mile of the race.
Since the first mile takes 6 minutes to complete and each subsequent mile takes another 5%, we can find a pattern:
Mile 1 - 6 minutes
Mile 2 - 6 x 1.05 minutes
Mile 3 - 6 x (1.05)^2 minutes

As we follow this pattern, the 26th mile should be:
Mile 26 - 6 x (1.05)^25 minutes

To work out the total time, we can put it into a formula that looks as such:

![](https://i.imgur.com/oRw15S4.png)

Once we put the numbers put into formula, it looks as such:

![](https://i.imgur.com/4usLx6f.png)

Once the numbers are in the formula, we can work out that it is 306.68.. minutes. To the nearest second, this is 18400 seconds.

### Part 3
Find a multiplicative inverse modulo 9 of each of the following integers.

(a) 1

1 x 0 = 0  r0

1 x 1 = 1  r1

Answer is 1

(b) 5

5 x 0 = 0  r0

5 x 1 = 5  r5

5 x 2 = 10  r1

Answer is 2

(c) 7

7 x 0 = 0  r0

7 x 1 = 7  r7

7 x 2 = 14  r5

7 x 3 = 21  r3

7 x 4 = 28  r1

Answer is 4

(d) 16

16 x 0 = 0  r1

16 x 1 = 16  r7

16 x 2 = 32  r5

16 x 3 = 48  r3

16 x 4 = 64  r1

Answer is 4

Show that each of the following integers doesn't have a multiplicative inverse modulo 9.

(a) 0

0 cannot have a multiplicative inverse modulo 9 as anything times 0 will always result in 0 and remainder 1 cannot be found.

(b) 6

6 does not have a multiplicative inverse modulo 9 as the numbers 6 and 9 both share a common prime factor - 3.

(c) 18

18 does not have a multiplicative inverse modulo 9 as the numbers 18 and 9 both share common prime factors - 2 and 3.


### Part 4
Produce a detailed report, explaining the importance of prime numbers within the field of computing.

Prime numbers are very important within computing, specificially cryptopgraphy, encryption and security.

Firstly, we need to understand what exactly a prime number is. A prime number is a whole number greater than 1 whose factors are only 1 and itself. For instance, the first few prime numbers are 2, 3, 5, 7, 11 and so on. They are all odd numbers with 2 being the only exception.

Cryptography is essentially all number theory. This is a branch of pure mathematics devvoted to the study of integers. Encryption is converting data into a string that is unrecognisable to read. This is widely used available due to the development of modern computers being able to perform powerful mathematical operations in seconds.

But why exactly are prime numbers important for cryptography? This is because of prime factorization, which is a commonly used mathematical problem that is used to secure public-key encryption systems. Public-key encryption consists of a product of two large prime numbers which is then uses to encrypt a message. As this is largely computer intensive, it is extremely difficult to use the public-key by itself to decrypt any encrypted messages unless you have the private-key.

An example of this is RSA encryption which uses prime numbers to create keys as said above. This system goes through 4 steps: key generation, key distribution, encryption, and decryption. The first step, key generation, takes two distinct and random prime numbers, multiplies them, and that is used as the modulus for both the public and private keys.

As shown below in Figure 1, it shows the rest of the key generation's equations
![Figure 1](https://i.imgur.com/dRmGGah.jpg)

The next part, key distribution, is simply giving someone the public key. This follows on to the last two steps as well, as encryption and decryption go hand in hand. For example, if Archie wanted to send information to Hannah and they wanted to use RSA to secure the information, Hannah would have to send Archie her public key so he can encrypt the information into ciphertext. Archie would then send the ciphertext to Hannah, who then can recover the information from the ciphertext by using her private key. The encryption happens by using an agreed-upon reversible protocol which is known as a padding scheme. The decryption reverses the padding scheme to decrypt the original information.

Prime numbers are an extremely efficient way to manage different specific computing fields such as cryptography and hashing. It is what many people and organisations depend on to keep their information secure, both personally and professionally.


References:

https://learncryptography.com/mathematics/prime-factorization

http://research.microsoft.com/en-us/groups/crypto/firstcrypto.aspx
