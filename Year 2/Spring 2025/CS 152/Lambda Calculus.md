---
tags:
  - cs152
---
- See the [lambda calculus tutorial](Attachments/Lambda%20Calculus%20Tutorial.pdf) 
-  See the [lambda calculus handout](Attachments/Lambda%20Calculus%20Handout.pdf)

>[!definition]
>The smallest universal programming language of the world
## Common Functions
### Identity
>[!definition]
>$$id=\lambda x.x$$

>[!example]
>$$(\lambda x.x)M=M$$
### Selection
>[!definition]
>$$fst=\lambda x.\lambda y.x$$
>$$snd=\lambda x.\lambda y.y$$

>[!example]
>$$(\lambda x.\lambda y.x)MN=(\lambda x.M)N=M$$
>$$(\lambda x.\lambda y.y)MN=(\lambda x.N)M=N$$

## Substitutions
## Arithmetic
zero
suc(zero) = 1
suc(suc(zero)) = 2 = suc(1)
>[!definition]
>$$0\equiv\lambda s.(\lambda z.z)\equiv\lambda sz.z$$
>$$1\equiv\lambda sz.s(z)$$
>$$2\equiv\lambda sz.s(s(z))$$
### Addition
- e.g. $2S3 \equiv SS3 \equiv S4 \equiv 5$
	- You can keep the z in to simplify the substituting
### Multiplication
>[!definition]
>$$(\lambda xyz.x(yz))$$

>[!example]
>$$(\lambda xyz.x(yz))22 \equiv (\lambda z.2(2z)) \equiv 4$$
