#lang racket/gui
(define p-score 0)
(define c-score 0)
(define options '("Rock" "Paper" "Scissors"))
(define phrase "")
(define frame (new frame% [label "Rock, Paper, Scissors!"]
                          [min-height 150]
                          [min-width 400]))

(define root (new vertical-panel%
                  [parent frame]))

(define score-panel (new horizontal-panel%
                         [parent root]
                         [alignment '(center top)]
                         [min-width 400]))

(define score-message (new message%
                           [parent score-panel]
                           [label "YOU: 0   COMPUTER: 0"]))
(send score-message auto-resize #t)
                           
(define player-panel (new horizontal-panel%
                 [parent root]
                 [alignment '(center center)]))

(define result-panel (new horizontal-panel%
                          [parent root]
                          [alignment '(center bottom)]))
(define result-msg (new message%
                        [parent result-panel]
                        [label ""]))
(send result-msg auto-resize #t)
;The default label sets the permanent min size, have to declare this outside to keep message centered once reassigned
(send result-msg set-label "Chose either rock, paper, or scissors from the menu and hit shoot to play.\n\t\t\tFirst to 5 wins!")

(define choice (new choice%
                         [label "Your move: "]
                         [parent player-panel]
                         [choices (list "Rock" "Paper" "Scissors")]))

(define start-button (new button%
                          [label "Shoot!"]
                          [parent player-panel]
                          [callback (lambda (button event)
                                      (define c-choice (random 0 3))
                                      (define p-choice (send choice get-selection))
                                      (cond
                                        ;rock
                                        [(= 0 p-choice)(cond
                                                         [(= 1 c-choice)(begin
                                                                          (set! c-score (+ 1 c-score))
                                                                          (set! phrase "You lost."))]
                                                         [(= 2 c-choice)(begin
                                                                          (set! p-score (+ 1 p-score))
                                                                          (set! phrase "You won!"))]
                                                         [else (set! phrase "It's a tie!")])]
                                        ;paper
                                        [(= 1 p-choice)(cond
                                                         [(= 0 c-choice)(begin
                                                                          (set! p-score (+ 1 p-score))
                                                                          (set! phrase "You win!"))]
                                                         [(= 2 c-choice)(begin
                                                                          (set! c-score (+ 1 c-score))
                                                                          (set! phrase "You lost."))]
                                                         [else (set! phrase "It's a tie!")])]
                                        ;Scissors
                                        [(= 2 p-choice)(cond
                                                         [(= 0 c-choice)(begin
                                                                          (set! c-score (+ 1 c-score))
                                                                          (set! phrase "You lost."))]
                                                         [(= 1 c-choice)(begin
                                                                          (set! p-score (+ 1 p-score))
                                                                          (set! phrase "You won!"))]
                                                         [else (set! phrase "It's a tie!")])]
                                        [else ""])
                                      (send score-message set-label (string-join (list "YOU:" (number->string p-score) "   COMPUTER:" (number->string c-score))))
                                      (send result-msg set-label (string-join (list "Computer chose" (list-ref options c-choice) ", " phrase)))
                                      (if(or(= p-score 5) (= c-score 5))(end-game p-score c-score)(display ""))
                                      )])
                          )

(define (start-game)
  (for ([k (length (send root get-children))])
    (send root delete-child (list-ref (send root get-children) (- (- (length (send root get-children)) 1) k))))
  (send root add-child score-panel)
  (send root add-child player-panel)
  (send root add-child result-panel)
  (set! p-score 0)
  (set! c-score 0)
  (send score-message set-label "YOU: 0   COMPUTER: 0")
  (send result-msg set-label "Chose either rock, paper, or scissors from the menu and hit shoot to play.\n\t\t\tFirst to 5 wins!")
  )


(define (end-game p-score c-score)
  ;This ensures entire message is printed before sleeping
  (sleep 0)
  (sleep 1.5)
  (send root delete-child score-panel)
  (send root delete-child player-panel)
  (send root delete-child result-panel)
  (define result "")
  (if(= p-score 5)(set! result "You won, Congratulations!")(set! result "Computer won, better luck next time!"))
  (define panel (new vertical-panel%
       [parent root]
       [alignment '(center center)]))
  (new message%
       [parent panel]
       [label result])
  (new button%
       [parent panel]
       [callback (lambda (button event) (start-game))]
       [label "Click here to play again"])
  )

(send frame show #t)