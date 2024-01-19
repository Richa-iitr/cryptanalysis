# Cryptanalysis
### Affine Cipher
The affine function is defined as ```e(x)=(ax+b) mod 26```, where aa and bb are integers and x is an element in $Z_{26}$​, the set of integers modulo 26.
To determine when this affine function is injective, you are looking at the congruence ax≡y(mod26) and claiming that this congruence has a unique solution for every y if and only if gcd(a,26)=1.

Let's break down the argument step by step:
  - Claim: If ```gcd(a,26)=1```, then the congruence ```ax≡y(mod26)``` has a unique solution for every y.
          Explanation: When ```gcd(a,26)=1```, it implies that a and 26 are relatively prime. This means that there is no integer greater than 1 that divides both a and 26. In this case, a has a modular multiplicative inverse modulo 26. Let $a^{−1}$ be the modular inverse of a modulo 26. The congruence ```ax≡y(mod26)``` can then be multiplied by $a^{-1}$ to obtain x≡ $a^{-1}$y(mod26). This congruence has a unique solution for every y because $a^{-1}$ exists, and the multiplication is well-defined modulo 26.
  - Counterclaim: If ```gcd(a,26)=d>1```, then the congruence ```ax≡y(mod26)``` may not have a unique solution for every y.
        Explanation: When ```gcd(a,26)=d>1```, it implies that aa and 26 have a common divisor greater than 1. In this case, the congruence ```ax≡0(mod26)``` has at least two distinct solutions in $Z_{26}$​: x=0 and x=26/d. Since ax≡0(mod26), multiplying both sides by a will give ax≡0(mod26). This implies that ax is a multiple of 26, and therefore, adding any multiple of 26 to the solutions x=0 and x=26/d will still satisfy the congruence. This lack of unique solutions means that the function e(x)=(ax+b)mod 26 is not injective, and it is not a valid encryption function.
