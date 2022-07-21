# v8-randomness-predictor

Using [z3](https://github.com/Z3Prover/z3) to predict `Math.random` in [v8](https://v8.dev)

## YouTube video

<p>
  <a href='https://www.youtube.com/watch?v=-h_rj2-HP2E'>
    <img src="https://user-images.githubusercontent.com/19750782/178938498-371e69b9-1182-427a-86c3-dca3e769e7ef.png" alt="PwnFunction YouTube Video" width="600">
  </a>
</p>

Watch the [✨ YouTube Video](https://www.youtube.com/watch?v=-h_rj2-HP2E)

## Run Instructions

Get a few Random numbers from v8, run to following code in [d8](https://v8.dev/docs/d8), [nodejs](https://nodejs.org/) or [chrome](https://www.google.com/chrome/).

```js
Array.from(Array(5), Math.random)
```

Optionally you can set the random seed in nodejs so you'd get the same numbers as shown below.
```js
/*
* Run nodejs with `--random_seed` flag like
* node --random_seed=1337
*/
Array.from(Array(5), Math.random)
// [0.9311600617849973, 0.3551442693830502, 0.7923158995678377, 0.787777942408997, 0.376372264303491]
```

Next we feed these random numbers into the python script (line 23).

```py
sequence = [
  0.9311600617849973,
  0.3551442693830502,
  0.7923158995678377,
  0.787777942408997,
  0.376372264303491,
]
```

Run the script.

```sh
$ python3 main.py

# Outputs
{'se_state1': 6942842836049070467, 'se_state0': 4268050313212552111}
#0.23137147109312428
#0.19307439497737655
#0.05294192203272163
#0.9562008120870276
#0.6770843658906902
#0.23644761978912543
#0.28755186139827904
#0.7729262936726293
#0.8850642958738326
#0.10122671660065197
#0.7642286088638273
#0.3433463041008338
#0.7759639410727457
#0.19678326096654364
#0.4584155686301481
```

## Resources
- [Learn z3 by solving simple challenges](https://github.com/PwnFunction/learn-z3)
- [There’s Math.random(), and then there’s Math.random()](https://v8.dev/blog/math-random)
- [Further scramblings of Marsaglia’s xorshift generators](https://vigna.di.unimi.it/ftp/papers/xorshiftplus.pdf)
- [(V8 Deep Dives) Random Thoughts on Math.random()](https://apechkurov.medium.com/v8-deep-dives-random-thoughts-on-math-random-fb155075e9e5)
- [Hacking the JavaScript Lottery](https://blog.securityevaluators.com/hacking-the-javascript-lottery-80cc437e3b7f)
