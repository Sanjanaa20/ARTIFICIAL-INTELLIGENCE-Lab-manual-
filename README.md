# ARTIFICIAL-INTELLIGENCE-Lab-manual-

EX.NO.1

STUDY OF PROLOG

AIM:
To Study about Prolog
STUDY:
symbolic, non-numeric computation. suited for solving problems that involve objects and relations
between objects

Tom is a parent of Bob can be written in Prolog as:
parent(tom, bob).
parent as the name of a relation; tom and bob are its arguments.
The whole Family Tree
parent(pam, bob).
parent(tom, bob).
parent(tom, liz).
parent(bob, ann).
parent(bob, pat).
parent(pat, jim).
This program consists of six clauses.
Prolog can be posed some questions about the parent relation

6

OUTPUT:
?- parent(bob,pat).
true.
?- parent(liz,pat).
false.
?- parent(tom,ben).
false.
?- parent(X,liz).
X = tom.
?- parent( bob, X).
X = ann .
?- parent( bob, X).
X = ann ;
X = pat.
?- parent(X, Y).
X = pam,
Y = bob ;
X = tom,
Y = bob ;
X = tom,
Y = liz ;
X = bob,
Y = ann ;
X = bob,
Y = pat ;
X = pat,
Y = jim.

The GRANDPARENT relation expressed as a
composition of two parent relations.

(1) Who is a parent of Jim? Assume that this is
some Y.
(2) Who is a parent of Y? Assume that this is
some X.
?- parent( Y, jim), parent( X, Y).
Y = pat,
X = bob
̍?- parent( tom, X), parent( X, Y).
X = bob,
Y = ann ;
X = bob,
Y = pat ;
Adding grandparent relation to the existing
program
grandparent(X,Y):-parent(X,Z),parent(Z,Y).
?- grandparent(pam,pat).
true.
?- grandparent(pam,ann).
true.
?- grandparent(tom,ann).
