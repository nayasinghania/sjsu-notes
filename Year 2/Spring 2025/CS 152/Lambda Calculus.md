---
tags:
  - cs152
---
- See the [lambda calculus handout](Attachments/Lambda%20Calculus%20Handout.pdf)
- See the [lambda calculus tutorial](Attachments/Lambda%20Calculus%20Tutorial.pdf) 

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





