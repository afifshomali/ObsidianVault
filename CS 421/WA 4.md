---
tags:
  - CS421
---
---
=> [[x > 2]] (FN a -> IF a THEN [[3]] _k ELSE [[x + 3]] _k).
=> [[x > 2]] (FN a -> IF a THEN _k 3 ELSE [[x+3]] _k).
=> [[x > 2]] (FN a -> IF a THEN _k 3 ELSE [[3]] (FN a -> [[x]] (FN b -> _k (b + a)))).
=> [[x > 2]] (FN a -> IF a THEN _k 3 ELSE [[3]] (FN a -> (FN b -> _k(b + a)) x)).
=> [[x > 2]] (FN a -> IF a THEN _k 3 ELSE (FN a -> (FN b -> _k(b + a)) x) 3).
=> [[2]] (FN a -> [[x]] (FN b -> (FN a -> IF a THEN _k 3 ELSE (FN a -> (FN b -> _k(b + a)) x) 3)(b > a))).
=> (FN a -> [[x]] (FN b -> (FN a -> IF a THEN _k 3 ELSE (FN a -> (FN b -> _k(b + a)) x) 3)(b > a)) 2).
=> (FN a -> (FN b -> (FN a -> IF a THEN _k 3 ELSE (FN a -> (FN b -> _k(b + a)) x) 3)(b > a)) x) 2.

----------

=> [[fun y -> x + y]] (FN plus_x -> [[plus_x x]] _k).
=> (FN plus_x -> [[plus_x x]] _k) (FUN y _k -> [[x + y]] _k).
=> (FN plus_x -> [[plus_x x]] _k) (FUN y _k -> [[y]] (FN a -> [[x]] (FN b -> _k (b + a)))).
=> (FN plus_x -> [[plus_x x]] _k) (FUN y _k -> (FN a -> [[x]] (FN b -> _k (b + a))) y).
=> (FN plus_x -> [[plus_x x]] _k) (FUN y _k -> (FN a -> (FN b -> _k (b + a)) x) y).
=> (FN plus_x -> [[x]] (FN a -> [[plus_x]] (FN b -> (b a _k)))) (FUN y _k -> (FN a -> (FN b -> _k(b + a)) x) y).
=> (FN plus_x -> (FN a -> [[plus_x]] (FN b -> (b a _k))) x) (FUN y _k -> (FN a -> (FN b -> _k(b+a)) x) y).
=> (FN plus_x -> (FN a -> (FN b -> (b a _k)) plus_x) x) (FUN y _k -> (FN a -> (FN b -> _k(b + a)) x) y).