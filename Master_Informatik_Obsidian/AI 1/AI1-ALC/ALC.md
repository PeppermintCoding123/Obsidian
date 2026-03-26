= Automated Language Computation

#### Roles
= binary relation
`has_child, has_weel, ....

#### Grammar
$F_{\mathcal{ALC}}::= C|\top|\bot|\overline{F_{\mathcal{ALC}}}| F_{\mathcal{ALC}}\sqcap F_{\mathcal{ALC}} |F_{\mathcal{ALC}}\sqcup F_{\mathcal{ALC}}|\exists R. F_{\mathcal{ALC}}|\forall R. F_{\mathcal{ALC}}$

concept definition
$mother = woman \sqcap (\exists has\_child.person)$

Identities
$\overline{\exists R.\varphi} = (\forall R. \overline{\varphi})$
$\overline{\forall R.\varphi} = (\exists R. \overline{\varphi})$
$\forall R.(\varphi \sqcap \psi) = \forall R. \varphi \sqcap \forall R.\psi$
$\exists R.(\varphi \sqcup \psi) = \exists R. \varphi \sqcup \exists R.\psi$
[[NNF of ALC]]

#### ALC Assertions
if $[\![a]\!] \in [\![\varphi]\!]$ => $[\![a:\varphi]\!] = \top$
if $([\![a]\!], [\![b]\!] )\in [\![R]\!]$ => $[\![aRb]\!]=\top$

[[ALC Tableau]]