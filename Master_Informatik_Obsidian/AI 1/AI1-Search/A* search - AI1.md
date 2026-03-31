evaluation function :  $f(n) = g(n) + h(n)$
$g(n)$ = path cost for $n$
$h(n)$ = estimated cost to nearest goal from n


| [[Complete]]                                     | [[time complexity]]                                               | [[space complexity]]                                              | [[optimality]] |
| ---------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | -------------- |
| Yes                                                  | Exponential in (relative error in h $\times$ lenth of solution n) | Exponential in (relative error in h $\times$ lenth of solution n) | Yes            |
| No if infinetely many nodes $n$ with $f(n)\leq f(0)$ |                                                                   |                                                                   |                |
expands nodes with $f(n)< h*(n)$

[[AI1-overview.canvas]]
[[Search Problems Math]]