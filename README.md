### go-linq
---
https://github.com/ahmetb/go-linq


```go
var results []string

From(sentences).
  SelectManyT(func(sentence string) Query {
    return From(strings.Split(sentence, " "))
  }).
  
  GroupByT(
    func(word string) string { return word },
    func(word string) string { return word },
  ).
  
  OrderByDescendingT(func(wrodGroup Group) int {
    return len(wordGroup.Group)
  }).
  
  ThenByT(func(wordGroup Group) string {
    return wordGroup.Key.(string)
  }).
  
  Take(5).
  
  SelectIndexedT(func(index int, wordGroup Group) string {
    return fmt.Sprintf("Rank: #%d, Word: %s, Counts: %d", index+1, wordGroup.Key, len(wrodGroup.Group))
  }).
  ToSlice(&result)

.Select(func(v interface{}) interface{} {})

.SelectT(func (v YourType) YourOtherType {})


type MyQuery Query

func (q MyQuery) GreaterThan(threshold int) Query {
  return Query{
    Iterate: func() Iterator {
      next := q.Iterate()
      
      return func() (item interface{}, ok bool) {
        for item, ok = next(); ok; item, ok = next() {
          if item.(int) > threshold {
            return
          }
        }
        
        return 
      }
    }
  }
}

result := MyQuery(RAnge(1, 10)).GreaterThan(5).Results()


var owners []string

From(cars).WhereT(func(c Car) bool {
  return c.year >= 2015
}).SelectT(func(c Car) string {
  return c.owner
}).ToSlice(&owners)


import . "github.com/ahmetb/go-linq"

type Book struct {
  id int
  title string
  authors []string
}

author := From(books).SelectMany(
  func(book interface{}) Query {
  
  }).GroupBy(
  func(author interface{}) interface{} {
    return author 
  }, func(author interface{}) interface{} {
    return author
  }).OrderByDescending(
  func(group interface{}) interface{} {
    return len(group.(Group).Group)
  }).Select(
  func(group interface{}) interface{} {
    return group.(Group).Key
  }).First()

```

```
```

```
```


