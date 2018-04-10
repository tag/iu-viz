# D3.js  andDynamic Elements

- [ ] The function used to load data has [changed significantly in D3 v5.0](https://github.com/d3/d3/blob/master/CHANGES.md#changes-in-d3-50)
  The new way is better, but know that when we copy other scripts, we may have to make some changes.
  
  ```javascript
  d3.csv('worldcup.csv')
  .then(function(data) {
      // Do stuff here ...
  });
  ```
- [ ] The function [`d3.csv`](https://github.com/d3/d3-fetch#csv) is built in. CSV stands for "comma separated values". There is a similar function for tab separated values (unsurprisingly, [`d3.tsv()`](https://github.com/d3/d3-fetch#tsv)), and several other import functions.
  
- [ ] The big change in D3.js v5.0 is that the call to `d3.csv()` now returns what's called a "promise". For our purposes, just know we can chain `.then()` and `.catch()` functions to handle success and error conditions.

  