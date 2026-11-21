# Signed direction blocks and exact edge general position in rank-two independence cubes

Research No.79, v1.0 Preprint — 2026-11-21 JST

Ryutaro Yonezu (Independent Researcher)

Independent AI mathematical audit of Theorems 1–6: CONDITIONAL PASS; no defect found. Application Appendix A: separate limited independent AI audit of model membership and lower constructions; original upper bounds depend on Nos.75–78. No human peer review or formal proof.

NOVELTY INCONCLUSIVE / REFERENCES PARTIAL / NOT HUMAN PEER REVIEWED / All rights reserved.

## Abstract

We give a shared structural framework for edge general position in isometric hypercube subgraphs, including the Fibonacci-type graphs studied in Research Nos.75–78. Two-arm exclusions imply a star forest, balanced direction relations and an antipodal support restriction across maximal two-connected direction blocks. For independence cubes of rank at most two, we identify domination exactly with one plus the vertex-cover number of the graph of legal pairs. A partition certificate then yields exact edge general position numbers for infinite families, including arbitrary disjoint unions of triangle-free paths and cycles, certain bipartite graphs, and linear/cyclic spacing cubes in explicit ranges. We additionally prove a strict domination-bound gap and an exact formula for double stars with at least two leaves on each side. A finite catalogue covers all labelled triangle-free legal-pair graphs on at most six labels. The unrestricted spacing-cube formula and a single derivation of all previous Fibonacci-type formulas are not claimed. Finite tests do not serve as premises of the analytic theorems.

## 1. Shared structural framework

Let G be a finite isometric induced subgraph of Q_n. An edge general position set (EGP set) S contains no three distinct edges on one geodesic; gp_e(G) is the maximum cardinality. A coordinate direction class Theta_i contains all edges flipping bit i; B2 is the sum of the largest two class sizes (pad with zero if necessary). Every geodesic flips its differing coordinates exactly once. For any subset J of directions, the union of its complete classes is EGP if and only if the Hamming diameter of the projection of V(G) onto J is at most two: if larger, a geodesic between witnessing vertices contains three selected edges; conversely at most two selected directions are flipped on any geodesic. In particular B2 is always a lower bound. In a down-set of Boolean words, shortest paths through intersection show isometry. On active coordinates and for |J|>=3, the projection diameter condition holds precisely when no legal pair of ones lies inside J: such a pair and a third active singleton have projected distance three; otherwise the projection consists of zero and singletons.

**Lemma 1 (projection exclusion).** If two selected edges of directions i,j share center c, any selected edge of another direction l has fixed bits x_i XOR x_j=c_i XOR c_j. Otherwise its projection on i,j matches exactly one leaf of the two-arm star. Orient the third edge so that its initial endpoint w has l-bit equal to c_l. Starting at the opposite leaf, traverse the two arms through c to the matching leaf z, then a shortest z-w path, then the third edge. The intervening path flips neither i,j nor l. All the coordinates flipped by the concatenation are distinct, so it is a geodesic, a contradiction.

**Lemma 2 (star forest).** If S uses at least three directions, the spanning selected subgraph is a disjoint union of stars and isolates. A simple three-edge selected path with distinct directions would be a geodesic. The only possible repetition pattern is i,j,i; the two overlapping two-arm stars then have opposite parity in (i,j), which excludes every selected third-direction edge by Lemma 1. There is therefore no simple three-edge path. As G is bipartite, every connected selected component is a star or isolate.

**Theorem 1 (signed blocks).** Suppose S uses at least three directions and has a star of degree at least three. Form R on its active directions, putting an edge ij if they co-occur at a selected star center, labelled sigma_ij=c_i XOR c_j. This is well defined by Lemma 1 and the existence of a third active direction. Every cycle has label XOR zero: any cycle omitting an active direction is tested by a selected edge of that direction, and the XOR telescopes. A cycle with a chord reduces to its two shorter cycles. A chordless spanning cycle of length >=4 is impossible because R has a triangle from a selected star. A spanning triangle has its three labels from that star, so its XOR is zero. Consequently each connected component admits a bit potential p with sigma_ij=p_i XOR p_j, by propagation along paths.

Let D be an inclusion-maximal vertex set containing a maximum star's clique in R and inducing a two-vertex-connected graph; write d=|D|>=3. For an exterior selected edge of direction l not in D, all constraints of R[D] hold, so its projection is p or its complement q. For a selected edge in direction l in D, the constraints of the connected R[D-{l}] force its other bits to match p or q, so it is a radial edge incident to p or q. An outside direction has at most one neighbor in D in R: otherwise adjoining that direction would preserve connectivity after deletion of any single vertex, contrary to maximality. These conclusions follow solely from isometry and EGP, not from any recurrence or density formula. They apply to all four earlier Fibonacci-type models, which are down-sets.

## 2. Antipodal support and capacity

For any D of size d>=3 and any p,q complementary on D, call vertices projecting to p or q cores. Available radial edges flip a D bit from a core. Their other endpoints are private leaves in this support: a one-bit neighbor of one antipode is not a one-bit neighbor of the other, and the unchanged outside coordinates identify the unique core. Exterior edges join cores; the support includes only these two types. Write C for the number of cores, a(v) for the radial degree at a core v, L=sum_v a(v), and Z for the number of zero-radial-degree cores. The full radial family is EGP. In a projected geodesic a core pattern, once left by a D flip, cannot be revisited. If both antipodes are visited, all D flips are between those visits and only the first and last can be radial; if just one is visited, at most two edges incident with it can be radial. Thus there are at most two radial edges on any geodesic.

For an S supported here with at least three active directions, orient each selected star from its center to its leaves. Every selected exterior edge has a core leaf without any selected radial arm. Charge it to an omitted radial edge at that leaf if a(v)>0, or to that leaf if a(v)=0. All charges are distinct, proving |S|<=L+Z. In particular, if Z=0 the best possible supported EGP size is L. If the maximum selected degree is <=d, the star-forest vertex count also gives |S|<=floor(d(C+L)/(d+1)). These bounds include the signed-block support of Theorem 1. The frozen v0.2–v0.4 supplements supply further conditional matching, packing and weighted bounds; those are relaxations, not assertions of universal equality. They are not needed for the analytic exact theorems below.

## 3. Rank-two domination and a partition certificate

Let K be any simple triangle-free graph with n>=1 labels and m edges. Define G_K as the cube induced by the cliques of K (equivalently, independent sets of its complement). Its vertices are empty, n singletons and m pairs. Its edges are spokes empty–singleton and incidence edges pair–singleton. Thus N=1+n+m and |Theta_i|=1+deg_K(i). Write tau(K) for minimum vertex-cover size, alpha(K)=n-tau(K) for independence number, and gamma(G_K) for domination number.

**Theorem 2.** gamma(G_K)=1+tau(K), and gp_e(G_K)<=max(B2,m+alpha(K)).

Proof. Empty together with the singleton vertices of a minimum vertex cover dominates G_K. For a dominating set of any size, let T be the chosen singleton labels, U=V(K)\T, and P its chosen pair vertices viewed as edges of K. Each edge of K[U] must lie in P. Choosing T and one endpoint per such edge yields a cover of size at most |T|+|E(K[U])|. If empty is chosen or P contains an extra edge beyond E(K[U]), the dominating set has at least 1+tau vertices. Otherwise empty is not chosen and P=E(K[U]); T is nonempty because empty needs a neighbor. If two edges of K[U] share an endpoint, cover those two by one vertex and every remaining edge by one, giving tau<=|T|+|P|-1. In the remaining case K[U] is a matching. Every u in U is incident with a chosen pair because its singleton must be dominated. Choose t in T. Retain T\{t}, and select one endpoint per matching edge, taking the endpoint adjacent to t if one exists. Triangle-freeness prevents both endpoints being adjacent to t. This covers all edges of K, including those incident to t; the cover has size |T|+|P|-1. This completes the domination proof.

By Lemma 2, an EGP set using >=3 directions has star components and isolates; one center per component is a dominating set in G_K. If there are c components then |S|=N-c<=N-gamma=m+alpha. Sets using at most two directions have size <=B2. QED.

For an arbitrary D subset of V(K), let T=V(K)\D and select every edge with direction in D incident to a vertex whose projection onto D is zero. This one-core-pattern radial family is EGP even if |D|<3: a projected geodesic can only leave or enter that pattern once each. Its size is |D|+cut_K(D,T), since it includes the |D| spokes and one incidence edge per crossing pair. Write e_K(X)=|E(K[X])| and define

  c(K)=min_{T subset V(K)} (|T|+e_K(T)+e_K(V(K)\T)).

Then tau(K)<=c(K) (T plus one endpoint per uncovered edge is a cover), and the largest one-pattern radial family has n+m-c(K) edges. Theorem 2 yields the exact sandwich

  max(B2,n+m-c(K)) <= gp_e(G_K) <= max(B2,n+m-tau(K)).    (1)

**Theorem 3 (partition certificate).** If there is a partition into T,D with T independent and |T|+e_K(D)=tau(K), then

  gp_e(G_K)=max(B2,m+alpha(K)).    (2)

In fact c(K)=tau(K) if and only if such a certificate exists. For the reverse direction, a partition cost equal to tau satisfies tau<=|T|+e_K(D)<=cost=tau, so e_K(T)=0. Necessarily K[D] is a matching plus isolates: two adjacent uncovered edges permit the cover to save one vertex, contradicting minimality. This is an exact criterion for the partition bound to reach the domination term, not a necessary condition for the latter term to be attained by arbitrary EGP sets.

**Corollary 3a.** If K is triangle-free and max degree <=2, equation (2) holds. Its components are paths (including isolates) or cycles. In a path or an even cycle choose the smaller alternating side as T; it is independent, D is independent, and a matching of size |T| proves minimum cover size |T|. In an odd cycle of length 2r+1>=5, choose r alternate vertices as T; D has exactly one edge. The cycle has cover number r+1 because an independent set has at most r vertices (each selected vertex has a distinct unselected successor) and the construction reaches r. Thus |T|+e(D)=r+1. Combining these certificates over components proves the result by additivity of vertex-cover size. More generally, a disjoint union of bipartite components each having a matching saturating its smaller part has a certificate given by the union of those smaller parts. Both statements allow arbitrarily many coordinate labels.

## 4. Strict domination gap: an exact double-star family

**Theorem 4.** Let K be a double star with adjacent centers a,b, with p>=2 leaves adjacent only to a and q>=2 leaves adjacent only to b. Write s=p+q. Then gp_e(G_K)=2s. The domination term is 2s+1, strictly too large.

Proof. K has n=s+2, m=s+1, tau=2 (the two centers cover K and disjoint edges force at least two cover vertices), and B2=s+4<=2s. Equation (1) gives gp_e<=2s+1. Choose all leaves as D in the radial construction, giving s spokes and s crossing incidence edges, hence 2s edges.

It remains to exclude an EGP set of size 2s+1. Such a set needs >=3 directions because B2<=2s. It is a star forest and has exactly N-(2s+1)=3 components. Any choice of star centers (isolates included) is a dominating triple. We show that the only dominating triple is {empty,{a},{b}}. A dominating triple not containing empty must contain at least one singleton to dominate empty. If it has t>=1 singleton vertices, its remaining 3-t pair vertices can dominate at most 2(3-t) singleton vertices, so at most t+2(3-t)<=5 singleton vertices are dominated. There are s+2>=6. If empty belongs to the triple, pair vertices must be dominated by the other two selected vertices. If {a} is not chosen, the p>=2 pairs consisting of a and an a-leaf each need their own chosen leaf singleton or that pair vertex. Thus both remaining positions must be used for these pairs (or p>2 is already impossible). Neither of these positions can dominate any pair consisting of b and a b-leaf; contradiction. By symmetry {b} must be chosen too. The triple is unique.

Every noncenter vertex now has to attach to an adjacent center in its star. Each leaf singleton must attach to empty, and each center–leaf pair must attach to its corresponding center singleton. The bridge pair {a,b} attaches either to {a} or {b}. In the former case, at {a} the bridge direction b and an a-leaf direction i are selected arms, with center parity zero on b,i. At {b} any b-leaf direction j is a third selected direction; its fixed bits have b=1,i=0. This contradicts Lemma 1. Attachment to {b} is symmetric. No EGP set reaches the domination term, and the constructed lower bound is exact. QED.

## 5. Spacing cubes: exact ranges and limits

Let G(n,h) be the cube of binary words of length n whose ones have pairwise index distance >=h+1. Let A_m^(h)=1 for m<=0 and A_m=A_(m-1)+A_(m-h-1) for m>=1. Let G_c(n,h) use the analogous cyclic distance. These models are known generalized Fibonacci/Lucas cubes; the run-avoidance model of earlier Nos.77–78 differs.

**Theorem 5 (linear rank-two range).** For h>=2 and 2<=n<=2h+2, gp_e(G(n,h))=A_(n-1)^(h).

If n<=h+1 the graph is an n-edge star. Otherwise put t=n-h-1, with 1<=t<=h+1. Legal pairs connect left positions 1..t and right positions h+2..n. These parts are disjoint, the graph is bipartite (other labels isolated), and pairs (i,i+h+1) form a matching of size t saturating both sides. Thus tau=t, m=t(t+1)/2, N-gamma=n+m-t=A_(n-1). Each coordinate class has at most 1+t edges. B2<=2(1+t)<=n+m-t: the difference is h-1-2t+t(t+1)/2 = h-2+(t-1)(t-2)/2, nonnegative for h>=2,t>=1. Taking the first h+1 coordinate classes selects every word meeting those positions, each exactly once, so yields A_n-A_(n-h-1)=A_(n-1). This also follows from the partition certificate. QED.

**Theorem 6 (cyclic rank-two range).** For h>=1, gp_e(G_c(n,h))=n for 2<=n<=2h+2 and gp_e(G_c(2h+3,h))=3h+4.

When n<=2h+1 the legal-pair graph is empty; at n=2h+2 it is a perfect matching with tau=h+1. At n=2h+3 it is a cycle on n labels with step h+1, since gcd(h+1,2h+3)=1. No three ones fit cyclically because the sum of three gaps would have to be >=3(h+1)>2h+3 for h>=1. Apply Corollary 3a: for the matching, m+alpha=n and B2=4<=n; for the cycle, m+alpha=(2h+3)+(h+1)=3h+4 and B2=6<=3h+4. This includes the previously known Lambda_5 value 7, not a new claim for that instance. QED.

The frozen v0.2 proof gives the analytic lower bound A_(n-1) for every h>=2,n>=2 and bounds all complete coordinate unions and pure antipodal radial families by that number. The v0.3–v0.4 supplements report coincident computational bounds for 42 spacing models: h=2,n=2..16; h=3,n=2..15; h=4,n=2..14. These finite results are inherited working results, not necessary for Theorems 1–6; their earlier verifiers have not been fully replayed in v0.6. The frozen v0.5 also identifies a barrier: for n>=2h+3 the domination number is <=A_(n-h-1)-1, so the domination bound alone cannot settle the all-n linear conjecture. This is a limitation of the method, not a counterexample to that conjecture.

## 6. Finite catalogue and boundary of scope

The new verifier enumerates all labelled simple triangle-free graphs K for 1<=n<=6 (6,228 in total, including isolated labels), checks vertex-cover and partition costs by direct enumeration, and finds 6,138 with c=tau. Every remaining graph (90) is isomorphic to the double star p=q=2: its degree multiset is (1,1,1,1,3,3), the degree-three vertices adjacent, and it has five edges. These facts force the asserted isomorphism. Theorem 4 covers all 90. Hence the catalogue is exhausted by a finite classification and the analytic theorems. As supplementary checks, the code computes actual BFS distances and forbidden triples by all orientations/orders in 51 models on at most four labels and in the remaining representative double star (optimum 8, 92 forbidden triples); it also checks unique dominating triples for 25 double stars p,q=2..6. This is author-side corroboration, not independent review. The infinite theorems do not depend on this catalogue.

We deliberately stop generalization here. The paper provides a common structural mechanism rather than a single fresh exact formula subsuming Nos.75–78. The full linear spacing conjecture, the cyclic range n>2h+3, arbitrary rank-two legal graphs not covered by the certificate/double-star theorem, and higher-rank independence cubes remain open within this work. No global novelty or priority claim is made. Theorems 1–6 received a conditional independent AI mathematical audit PASS. The unrestricted cases remain open.

## References (partial)

- P. Manuel, R. Prabha, S. Klavžar, The edge general position problem, Bull. Malays. Math. Sci. Soc. 45 (2022), 2997–3009, DOI 10.1007/s40840-022-01319-8. The two-Theta-class construction in partial cubes is prior work (Lemma 3.1).
- J. Tian, S. Klavžar, E. Tan, Extremal Edge General Position Sets in Some Graphs, Graphs Combin. 40 (2024), article 40, DOI 10.1007/s00373-024-02770-z.
- P. Manuel, R. Prabha, S. Klavžar, Generalization of edge general position problem, Art Discrete Appl. Math. 8 (2025), #P1.02, DOI 10.26493/2590-9770.1745.5f4.
- Z. Hamed-Labbafian, M. A. Henning, M. Tavakoli, Edge general position in graphs: Graph products, integer linear programming and some applications, Discrete Appl. Math. 386 (2026), 1–8, DOI 10.1016/j.dam.2026.01.008. An ILP approach is prior work.
- V. Ullas Chandran S. V., S. Klavžar, J. Tuite, The General Position Problem: A Survey, arXiv:2501.19385 (2025), Section 3.6.

- S. Klavzar and E. Tan, Edge General Position Sets in Fibonacci and Lucas Cubes (2023), DOI 10.1007/s40840-023-01517-y, https://arxiv.org/abs/2304.10114. Prior two-class constructions and Fibonacci/Lucas EGP context.
- P. Codara and O. M. D'Antona, Generalized Fibonacci and Lucas cubes arising from powers of paths and cycles, Discrete Mathematics 339 (2016), 270–282, DOI 10.1016/j.disc.2015.08.012. Prior graph model and enumeration.
- Author's earlier research Nos.75–78: related constructions and proofs. Their claimed exact formulas are not re-proved or claimed as new results here.

Targeted preliminary searches for edge general position with daisy cubes, independence cubes, domination, and generalized Fibonacci cubes did not identify a direct matching theorem. Search-result/abstract scope only; full-text/citation survey remains incomplete. NOVELTY INCONCLUSIVE / REFERENCES PARTIAL.


\newpage

# Research No.79 v0.6 — Application Appendix A: Nos.75–78

**Editorial Appendix A — 2026-11-21 JST.** This appendix received a separate limited independent AI audit of its down-set assumptions, construction counts and selected finite cases. The earlier independent audit of Theorems 1–6 did not cover it. Upper bounds and equality claims remain dependent on Nos.75–78. NOVELTY INCONCLUSIVE / REFERENCES PARTIAL / NOT HUMAN PEER REVIEWED / All rights reserved.

## A1. The exact distinction between applicability and a unified proof

No.79, Lemmas 1–2 and Theorem 1 are shared **structural** results for isometric induced subgraphs of a hypercube; the complete exact formulas of Nos.75–78 do **not** follow from those structural results alone. No.79, Theorems 2–6, are **rank-two** theorems and cannot be applied automatically to every dimension of Nos.75–78. Individual *upper bounds and equality classifications* below are imported from the respective earlier mathematical manuscripts, not re-proved independently here. No claim of a new unified derivation of all four formulas is made.

## A2. One proof of isometry for each of the four graph families

Each family has as vertices a set of binary words closed under changing any 1 to 0:

1. No.75: length-`n` words avoiding adjacent ones, n>=2;
2. No.76: length-`n` cyclic words avoiding cyclically adjacent ones, n>=3;
3. No.77: length-`n` words avoiding `k` consecutive ones, k>=3 and n>=2;
4. No.78: length-`n` cyclic words avoiding cyclic runs of `k` ones, n>=k>=3.

Deleting ones cannot create a forbidden all-ones pattern. For two allowed words x,y, first delete each bit in x\y, reaching x AND y; then insert each bit in y\x, remaining within the support of y. Every intermediate word is legal. This path has Hamming length |x XOR y|, so every family is an isometric induced subgraph of Q_n. Thus for every EGP set S in any of the four models:

- No.79's two-arm projection exclusion, Lemma 1, applies.
- If S uses >=3 coordinate directions, the selected subgraph is a star forest (Lemma 2).
- If S uses >=3 directions and has a selected star of degree >=3, the signed direction relation, balanced potentials, maximal 2-connected block, and antipodal radial/exterior support conclusion of Theorem 1 apply **subject to its stated hypotheses**.
- A complete union of at most two coordinate classes is always EGP.

This is a direct analytic check of every model's hypotheses, not just an assertion based on titles.

## A3. No.75 — linear Fibonacci cube Gamma_n

**Construction by the general two-direction principle.** For n>=2, both endpoint classes have |Theta_1|=|Theta_n|=F_n, hence the union is EGP with exactly 2F_n edges. The size identity follows from the legal word count on the remaining n-1 positions after imposing a 1 at the endpoint.

**Specific optimality still needed.** No.75 v0.10, §§2–5, supplies the upper bound by (i) star-forest density for maximum degree <=3, (ii) projection exclusion and Fibonacci base/recurrence certificate for degree 4, and (iii) a five-arm exclusion count for larger degrees. Its equality classification singles out the two boundary coordinate classes. Theorem 1 of No.79 explains the same star/projection mechanism, but does not by itself verify those numerical inequalities or uniqueness.

**Bridge:** structural hypothesis PASS; lower construction PASS; final upper bound/uniqueness CONDITIONAL ON No.75 proof, not newly proved here.

## A4. No.76 — cyclic Lucas cube Lambda_n: the key three-direction application

The coordinate classes have |Theta_i|=F_(n-1). For n>=5, their largest two-class union has only 2F_(n-1) edges, strictly fewer than the No.76 optimum F_n+F_(n-2) by F_(n-4)>0. Therefore a proof that only considers complete coordinate-class unions **cannot** explain this model.

**Construction by No.79 antipodal radial support.** Fix three consecutive cyclic directions D={0,1,2}. Select every direction-D edge whose other two D bits are zero. Equivalently these are radial edges at the 000 core in each fixed outside-coordinate fiber. No.79 §2 proves that the full radial family is EGP. Counting the middle-direction edges gives F_(n-1); each outer direction contributes F_(n-2), for a total

    F_(n-1) + 2 F_(n-2) = F_n + F_(n-2).

For n=3 this is the three-edge star; for n=4 it equals the two-class bound; for n>=5 it strictly beats that bound. The selected three-arm center with all other bits zero generates a signed relation triangle on D and has potential 000, exactly as in No.79 Theorem 1.

**Specific optimality still needed.** No.76 v0.1–v0.3 supplies the substantial cyclic gap and local star-pair capacity arguments, including finite recurrence bases and the exceptional n=6 relaxation case. No.79's structural theorem alone does not replace those checks. No.76 does not claim full equality-set uniqueness.

**Bridge:** structural hypothesis PASS; explicit application of No.79 radial family PASS; construction cardinality PASS; upper bound CONDITIONAL ON No.76 proofs, not independently reproduced by this appendix.

## A5. No.77 — higher-order linear run-avoiding cube Q_n(1^k)

For k>=3,n>=2, let A_n^(k) count the legal words. The two endpoint classes have size A_n-A_(n-1) each. The No.79 two-class principle yields an EGP set of size

    2 (A_n - A_(n-1)).

All models are down-sets, so the generic star/projection/signed-block framework applies to other candidate extremizers. The No.77 proof additionally needs its density inequality B>=10A_n/11 and the six-separated-direction exclusion for large stars; these yield the **strict** upper bound for any EGP set using >=3 directions. The original equality classification then gives the endpoint union for n>=k+1 and any two complete classes for 2<=n<=k.

**Bridge:** structural hypothesis PASS; construction cardinality PASS; final upper bound/equality CONDITIONAL ON No.77 proof.

## A6. No.78 — higher-order cyclic run-avoiding cube H(n,k)

For n>=k>=3, all coordinate classes have size C_n^(k)-A_(n-1)^(k). The No.79 two-class principle yields

    2 (C_n - A_(n-1))

selected EGP edges for any pair of distinct directions. The down-set/isometry, projection exclusion and star forest requirements hold verbatim. The No.78 proof's missing case k=3 relies on a separate transfer-matrix certificate (1,296 four-gap/center bases) and a finite n=4 equality-classification computation. For k>=4 it uses the original analytic density and excluded-projection arguments. The uniqueness of maxima is imported from No.78, not deduced from No.79's general structure alone.

**Bridge:** structural hypothesis PASS; construction cardinality PASS; final upper bound/equality CONDITIONAL ON No.78 proof and its numerical certificate.

## A7. Summary and closure recommendation

| Model | Fits No.79 structural framework | A No.79 construction reaches its reported optimum | No.79 alone reproves upper bound |
| --- | --- | --- | --- |
| No.75 Gamma_n | Yes, all n>=2 | Yes, two complete endpoint classes | **No** |
| No.76 Lambda_n | Yes, all n>=3 | **Yes, three-direction 000-core radial family** | **No** |
| No.77 Q_n(1^k) | Yes, k>=3,n>=2 | Yes, two endpoint classes | **No** |
| No.78 H(n,k) | Yes, n>=k>=3 | Yes, any two complete classes | **No** |

**Proposed claim for the final paper:** “Theorem 1 applies individually to all four earlier run-avoiding and Fibonacci/Lucas cube families; its two-direction and antipodal radial constructions recover their corresponding lower-bound mechanisms. Their exact upper bounds and extremizer classifications remain separate model-specific consequences proved in Nos.75–78, not new corollaries of Theorem 1 alone.”

This is a stronger, accurately scoped application statement than merely listing the four graph names. It does not justify advertising a complete unified independent proof of all four prior theorems.

## A8. Local spot-check scope

Run `python -B No79_V06_APPLICATION_CHECK_75_78.py`. It uses **only Python's standard library** and exhaustively enumerates legal vertices and construction edges over 49 selected parameter instances: 7 (No.75), 6 (No.76), 21 (No.77), and 15 (No.78). For each, the verifier checks downward closure, exact construction count, and computes the maximum number of selected edges on any shortest path by an independently written shortest-path DAG DP. It does **not** check arbitrary EGP upper bounds, all dimensional parameters, or uniqueness. The analytic arguments above, not these finite tests, establish the model membership and lower constructions for all stated parameters.

## A9. Source identity and editorial discipline

The consulted mathematical source texts, exact SHA256:

- `No79_UNIFIED_V06_CLOSURE/MANUSCRIPT_V06.md` — `eadbe8ca533cd7dfafac9dfad37781088af3f8e95f7140b785c8937e087123cf`
- `No75_V010/RESULTS.md` — `d9af8c385e3c67cec908a8dde821878b8d95805f207826d89282f572481a14aa`
- `No76_LUCAS_V03/RESULTS.md` — `3aec6fd5cb5f77469743a136ade8c86d0f9decdac916f121bea4753b7bd9b092` (references nested v0.1/v0.2 originals)
- `No77_GENERAL_K_V01/MANUSCRIPT.md` — `83caf0c565d5f81e9adf96b4cff21245dc962353c8b4bb04f74fd7c68dea49a9`
- `No78_CYCLIC_K_V02/MANUSCRIPT_V02.md` — `cee2fc12ba41b2569eaa39e5b6b1e1912f1d778e055883222faed6ed34708a9c` (references nested v0.1 original)

The above texts are the available frozen research-source materials consulted for this appendix, not an independent cross-audit of the currently public repository PDFs. No original byte or mathematics is changed. A targeted limited application audit was performed for this v1.0 preprint. It is not a full independent re-audit of Nos.75–78 or publication authorization.
