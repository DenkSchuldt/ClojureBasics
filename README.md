# Clojure Basics :squirrel:


## Requirements:
- **Leiningen**. Download it [here](http://leiningen.org/).

<br/>

```clojure
;; Creating a new project:
=> lein new project-name
```

#### Basics
Integers, Strings, Booleans, Characters, Decimals, Keywords, Ratios.

```clojure
=> (+ 1 2)
   ;; 3

=> (- 3 4)
   ;; -1

=> (* 5 6)
   ;; 30

=> (/ 7 8)
   ;; 7/8
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
   ;; '(2 "a" 1 :foo-bar)

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
=> (zipmap [:vampire :monster :zombi] ["dracula" "frankie" "wilson"])
   ;;{:zombi "wilson", :monster "frankie", :vampire "dracula"}

;; Sets:
=> #{1 2 3 4}
=> (clojure.set/union #{1 2 3} #{3 4 5})
   ;; #{1 2 3 4 5}
=> (clojure.set/intersection #{1 2 3} #{3 4 5})
   ;; #{3}
=> (clojure.set/diference #{1 2 3} #{3 4 5})
   ;; #{1 2}
=> (contains? #{1 2 3 4} 4)
   ;; true
=> (get #{1 2 3 4} 4)
   ;; 4
=> (:red #{:yellow :blue :red :white}) ;; Keywords
   ;; :red
=> (set [1 2 3 4])
   ;; #{1 4 3 2}
=> (set {:a 1, :b 2})
   ;; #{[:b 2] [:a 1]}
=> (conj #{1 2 3} 4)
   ;; #{1 4 3 2}
=> (disj #{1 2 3} 1)
   ;; 1#{3 2}
```

#### Symbols & Binding
```clojure

;; Global var
=> (def user "Dexter")
   ;; #'user/user

;; Temporary binding
=> (let [first-name "Dexter" last-name "Slim"] [first-name last-name])
   ;; ["Dexter" "Slim"]
```

#### Functions
```clojure
=> (defn not-using-parameters [] "Dexter") ;; "Dexter" -> default
   ;; #'user/the-name-is

=> (defn using-parameters [first-name last-name] {
      :param1 first-name
      :param2 last-name
    })
   ;; #'user/using-parameters

=> (def using-anonymous-functions (fn [] (str "" 1234)))
   ;; #'user/using-anonymous-functions

=> (def shorter-anon-function #(str "" 1234))
   ;; #'user/shorter-anon-function

=> (def shorter-anon-function-with-params (#(str "Hello, I am " %1 %2 %3) "Dexter" " " "Slim"))
   ;; #'user/shorter-anon-function-with-params
```

#### Namespaces
```clojure
=> (ns object.attribute)
=> %ns%
=> (def function-in-namespace "Function in namespace")
   ;; #'object.attribute/function-in-namespace
=> object.attribute/function-in-namespace
   ;; "Function in namespace"
```

#### Libs
```clojure
=> (require 'clojure.set)
=> (require '[object.attribute :as obj]) ;; obj/functions
=> (ns objects
    (:require [object.attribute :refer :all])) ;; Could cause naming conflicts

```


> # Code is data
