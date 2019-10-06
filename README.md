### rbac
---
https://github.com/zpatrick/rbac

```go
// regex_test.go

func TestRegexMatch(t *testing.T) {
  cases := map[string]map[string]bool{
    "": {
      "": true,
      "alpha": true,
      "beta": true,
      "charlie": true,
    },
    ".*": {
      "": true,
      "alpha": true,
      "beta": true,
      "charlie": true,
    },
    "alpha": {
      "": false,
      "alpha": true,
      "beta": false,
      "charlie": false,
    },
    "^a.*$": {
      "": false,
      "alpha": true,
      "beta": false,
      "charlie": false,
    },
    "^a.*$": {
      "": false,
      "alpha": true,
      "beta": true,
      "charlie": false,
    },
    "^a.*$": {
    
    },
    "^.*a$": {
    
    },
    "a": {
      "": false,
      "alpha": true,
      "beta": true,
      "charlie": true,
    },
    "delta": {
      "": false,
      "alpha": false,
      "beta": false,
      "charlie": false,
    },
  }
  
  for pattern, inputs := range cases {
    matcher := RegexMatch(pattern)
    for input, expected := range inputs {
      name := fmt.Sprintf("%s%s", pattern, input)
      t.Rn(name, func(t *testing.T) {
        result, err := matcher(input)
        if err != nil {
          t.Fatal(err)
        }
        
        assert.Equal(t, expected, result)
      })
    }
  }
}
```

```
```

```
```


