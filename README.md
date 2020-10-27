# BAuth

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
            
            
