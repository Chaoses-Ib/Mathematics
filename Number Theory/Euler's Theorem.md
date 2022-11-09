# Euler's Theorem
**Euler's theorem (Fermat-Euler theorem, Euler's totient theorem)** states that, if $n$ and $a$ are coprime positive integers, and $\phi(n)$ is Euler's totient function, then $a$ raised to the power $\phi(n)$ is congruent to $1$ modulo $n$, i.e.

$$a^{\phi(n)}\equiv 1 \pmod n$$

where **Euler's totient function (Euler's phi function)** counts the positive integers up to a given integer $n$ that are relatively prime to $n$.

For example, $2^{\phi(63)}=2^{36}\equiv 1 \pmod{63}$.

If $p$ is a prime number and is coprime to $q$, then
$$\phi(pq)=(p-1)(q-1)$$

## Fermat's little theorem
**Fermat's little theorem** states that if $p$ is a prime number, then for any integer $a$, the number $a_p-a$ is an integer multiple of $p$, i.e.
$$a^p\equiv a \pmod p$$
If $a$ is coprime to $p$, Fermat's little theorem is equivalent to the statement that $a^{p-1}-1$ is an integer multiple of $p$, i.e.
$$a^{p-1}\equiv 1 \pmod p$$
For example, $2^6 \equiv 1 \pmod 7$, $2^{60}\equiv 1 \pmod {61}$.