## karma (javascript test runner)

command line

```bash
$ npm install -g karma

# Start Karma.
$ karma start
```

config file

```
module.exports = function(config) {
  config.set({
    // base path, that will be used to resolve files and exclude
    basePath: "../..",

    frameworks: ["jasmine"],

    // list of files / patterns to load in the browser
    files: [
      "test/client/mocks.js",
      "static/karma.src.js",
      "test/client/*.spec.js"
    ],

    // list of files to exclude
    exclude: [],

    // use dots reporter, as travis terminal does not support escaping sequences
    reporters: ["progress"],

    // web server port
    port: 9876,

    // cli runner port
    runnerPort: 9100,

    // enable / disable colors in the output (reporters and logs)
    colors: true,

    // level of logging
    logLevel: config.LOG_INFO,

    // enable / disable watching file and executing tests whenever any file changes
    // CLI --auto-watch --no-auto-watch
    autoWatch: true,

    // Start these browsers, currently available:
    browsers: ["Chrome"],

    plugins: [
      'karma-jasmine',
      'karma-chrome-launcher',
      'karma-firefox-launcher',
      'karma-junit-reporter'
    ]
  });
};
```

## mocha (bdd and tdd testing framework)

synchronous code

```javascript
var assert = require("assert");

describe("Array", function() {
  describe("#indexOf()", function() {
    it("should return -1 when the value is not present", function() {
      assert.equal(-1, [1, 2, 3].indexOf(5));
      assert.equal(-1, [1, 2, 3].indexOf(0));
    })
  })
})
```

asynchronous code

```javascript
describe("User", function() {
  describe("#save()", function() {
    it("should save without error", function(done) {
      var user = new User("Luna");
      user.save(function(err) {
        if (err) throw err;
        done();
      });
    })
  })
})
```

bdd style

```javascript
describe("Array", function() {
  before(function() {
    // ...
  });

  describe("#indexOf()", function() {
    it("should return -1 when not present", function() {
      [1, 2, 3].indexOf(4).should.equal(-1);
    });
  });
});
```

tdd style

```javascript
suite("Array", function() {
  setup(function() {
    // ...
  });

  suite("#indexOf()", function() {
    test("should return -1 when not present", function() {
      assert.equal(-1, [1, 2, 3].indexOf(4));
    });
  });
});
```

## chai (bdd and tdd assertion library)

expect style

```javascript
var expect = chai.expect;

expect(foo).to.be.a("string");
expect(foo).to.equal("bar");
expect(foo).to.have.length(3);
expect(tea).to.have.property("flavors")
  .with.length(3);
```

assertion style

```
var assert = chai.assert;

assert.typeOf(foo, "string");
assert.equal(foo, "bar");
assert.lengthOf(foo, 3)
assert.property(tea, "favors");
assert.lengthOf(tea.flavors, 3);
```
