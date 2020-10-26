# auth

OAuth is better, but BAuth is better for brunozhon.github.io domains.

- [OAuth way](https://www.google.com/search?q=oauth&safe=strict&prmd=vin&sxsrf=ALeKk02Ys1JacXzP0ncyM1rdBU5uPoEtkA:1603754180535&source=lnms&tbm=isch&sa=X&ved=2ahUKEwiAlPPxsdPsAhWNbs0KHfnWCeQQ_AUoAnoECCUQAg&biw=1112&bih=707#imgrc=-GtIMrTEtSuwtM)

- BAuth way:
  1. Comfirm resource
  2. Add it to local storage using JavaScript
  3. Turn to an array when acsessing it
     1. Get data
     2. `JSON.parse()` the data
         1. Check status
            1. If it completes, head over to the next step
            2. If it fails, throw an error using `throw`
            
            
```
|----------------|   1. Confirm rescorce
|                |<--------------------------------- ...
|                |   2. Sends data as local storage
|  BAuth server  |--------------------------------- ... >
|                |   3. Acsess resource
|                |<--------------------------------- ...
|                |   4. Sends data as JSON arrays
|                |--------------------------------- ... >
|----------------|

```

The BAuth server can be the same if it is <https://brunozhon.github.io>.

```
HTTP part

1. Unknown server sends reqeust
<------------------------------
2. HTTP protocol sends "200 OK"
------------------------------>

Brunozhon.github.io part

3. Redirects user there
<------------------------------
4. User confirms resource and is redirected to a page
-----------|
           |
<----------|
5. Data is sent in local storage but may be lost
------------------------------->
or
---------------     ???????    >
6. User leaves and comes back
------------------- ... |
                        |
<------------------ ... |
7. Server gets data
------------------------------->
```

Lets assume that the server is *example.com* and the BAuth server is brunozhon.github.io.

1. *example.com* connects to brunozhon.github.io
2. *example.com* gets 200 OK
3. User gets redirected
4. brunozhon.github.io returns data like ["*Server list*"]
5. *example.com* gets data
6. User leaves and returns back
7. *example.com* gets the **SAME** data is step 2

Still 7 steps, see?

OAuth is 7 steps but requires a token.

*example.com*'s OAuth request may be like *example.com?token=**YOURTOKEN***
