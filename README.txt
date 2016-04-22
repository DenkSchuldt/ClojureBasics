# Clojure Basics :squirrel:


## Requirements:
- **Leiningen**. Download it [here](http://leiningen.org/).

<br/>

```clojure
;; Creating a new project:
=> lein new project-name
```

#### Basics
```clojure
;; Addition:
=> (+ 1 2)

;; Subtraction:
=> (- 3 4)

;; Multplication:
=> (* 5 6)

;; Division:
=> (/ 7 8)
```

#### Collections
Useful functions: **first**, **rest** (first complement), **last**, **count**.
```clojure
;; Vectors:
=> [1 "a" :foo-bar]
=> (nth [1 "a" :foo-bar] 1)
   ;; "a"
=> (conj ["a" 1 :foo-bar] 2)
   ;; ["a" 1 :foo-bar 2]

;; Lists:
=> '(1 "a" :foo-bar)
=> (conj '("a" 1 :foo-bar) 2)
   ;; '(2 "a" 1 :foo-bar 2)

;; Maps:
=> {:fisrt-name "Dexter", :last-name "Slim"}
=> (get {:first-name "Dexter", :last-name "Slim"} :first-name)
   ;; "Dexter"
=> (get {:first-name "Dexter", :last-name "Slim"} :middle-name "default")
   ;; "default"
=> (:first-name {:first-name "Dexter", :last-name "Slim"})
   ;; "Dexter"
=> (:middle-name {:first-name "Dexter", :last-name "Slim"} "default")
   ;; "default"
=> (keys {:first-name "Dexter", :last-name "Slim"})
   ;; (:first-name :last-name)
=> (vals {:first-name "Dexter", :last-name "Slim"})
   ;; ("Dexter" "Slim")
=> (merge {:first-name "Dexter"}
          {:last-name "Slim"})
   ;; {:first-name "Dexter", :last-name "Slim"}
=> (assoc {:first-name "Dexter", :last-name "Slim"} :first-name "Denny")
   ;; {:first-name "Denny", :last-name "Slim"}
=> (dissoc {:first-name "Dexter", :last-name "Slim"} :first-name)
   ;; {:last-name "Slim"}
```
