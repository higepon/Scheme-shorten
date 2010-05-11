## What is this?
This library provides a short alias for lambda expression written in pure R6RS.
The idea come from "Gauche Devlog - Shorter names http://blog.practical-scheme.net/gauche/20100428-shorter-names" by Shiro.

## Example
    (import (rnrs)
            (shorten))
    (map (^(x y) (+ x y)) '(1 2 3 4) '(1 2 3 4)) ;; (map (lambda (x y) (+ x y)) '(1 2 3 4) '(1 2 3 4))
    (map (^a a) '(1 2 3 4))                      ;; (map (lambda (a) a) '(1 2 3 4))
    (map (^a* a*) '(1 2 3 4))                    ;; (map (lambda a* a*) '(1 2 3 4))


## Expansion rules
    (^(a b c ...) body ...) => (lambda (a b c ...) body ...)
    (^a body ...) => (lambda (a) body ...)
    (^b body ...) => (lambda (b) body ...)
    ...
    (^z body ...) => (lambda (z) body ...)
    (^_ body ...) => (lambda (_) body ...)

    (^a* body ...) => (lambda a* body ...)
    (^b* body ...) => (lambda b* body ...)
    ...
    (^z* body ...) => (lambda z* body ...)


## Author
OKUMURA Yuki
Taro Minowa(Higepon)

## License
New BSD License

