# es6katas-templatestring-basic
// 1: template strings - basics
// To do: make all tests pass, leave the asserts unchanged!

describe('a template string, is wrapped in ` (backticks) instead of \' or "', function() {

  describe('by default, behaves like a normal string', function() {
    
    it('just surrounded by backticks', function() {
      var str = `like a string`;
      //var str did not have a value
      assert.equal(str, 'like a string');
    });
    
  });

  var x = 42;
  var y = 23;
  
  describe('can evaluate variables, which are wrapped in "${" and "}"', function() {
    
    it('e.g. a simple variable "${x}" just gets evaluated', function() {
      var evaluated = `x=${x}`;
      //replaced expression
      assert.equal(evaluated, 'x=' + x);
    });
    
    it('multiple variables get evaluated too', function() {
      var evaluated = `${ x }+${ y }`;
      //template literals enclosed by backticks instead of quotes, removed spaces
      assert.equal(evaluated, x + '+' + y);
    });
    
  });

  describe('can evaluate any expression, wrapped inside "${...}"', function() {
    
    it('all inside "${...}" gets evaluated', function() {
      var evaluated = `${x+y}`;
      //removed extra brackets and spaces
      assert.equal(evaluated, x+y);
    });
    
    it('inside "${...}" can also be a function call', function() {
      function getDomain(){ 
        return document.domain; 
      }
      var evaluated = `${ getDomain() }`;
      assert.equal(evaluated, 'tddbin.com');
    });
    
  });
  
});
