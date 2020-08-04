---
layout: page
title: dynamic
permalink: /dynamic/
---

<div class="mermaid">
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
</div>

<br/>

<div class="mermaid">
gantt
dateFormat  YYYY-MM-DD
title Project plan
excludes weekdays 2020-08-01
section Admin App
Initial Storyboard        :done,    des1, 2020-08-01, 2020-08-09
Screens 1 - 6             :active,  des2, 2020-08-09, 3d
Screens 7 - 12            :         des3, after des2, 5d
Screens 12 - 18           :         des4, after des3, 3d
Screens 19 - 24           :         des5, after des3, 4d
</div>

Functions are combined by nesting them in lists. They are evaluated from the inside out:

<pre><code class="klipse" data-loop-msec="3000">
    (+ 10001 (rand 10))
</code></pre>

In this case the rand function returns a number (from 0-9) and the + function then evaluates. This [browser based evaluator Klipse](https://github.com/viebel/klipse) has a magic trick where it can be put on a loop - your edits will be in the loop too :)

<pre><code class="klipse" data-loop-msec="3000">
    (map (fn [n] (rand n)) (range 1 4))
</code></pre>

**map** is an example of combining functions over a sequence. **map** takes a function followed by a sequence, on which that function will apply to each element of the sequence in turn. Evaluation occurs from *the deepest nested list and then from right to left*. Reading from right to left the **range** function is evaluated and produces a list of numbers from 1 to 3.

The anonymous function `(fn [n] (rand n))` is invoked by map for each element and a radom number up to each value of `n` is produced. By default map produces a *lazy sequence* of all of its results. This means that when **map** is composed with other functions, the dependent function is fluid: it can operate on the next output element as soon as it is produced.
