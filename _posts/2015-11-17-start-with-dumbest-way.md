---
layout: post
title: 'Dumber is Wiser'
date: 2015-11-17

---

> Being Dumb is good some time

And if one is doing TDD, then being dumb is always good. While solving a problem, we always start by describing problem behaviour in different scenarios. Among all scenarios it is always wise to pick that starting point where the problem's behaviour has least complexity. Write the test for that specific and while write code to make that test pass, try to do in the dumbest way.
Let's us take an example in which we wanted to calculate distance between two points:

1. First behaviour with minimal complexity is when both points are equal

```ruby
describe Point do
  it 'distance between two same points' do
    let(:point1) { Point.new(1, 1) }
    expect(point1.distance(point1)).to eq(0)
  end
end
```
2. Now the dumbest way to add this functionality to our code or in TDD world dumbest way to pass this spec is following :

```ruby
class Point
  def distance(other)
    0
  end
end
```

Now slightly increasing the complexity in behavior for example:

1. Second behaviour could be when both points lies on X axis.

```ruby
describe Point do
  it 'distance between two points on X axis' do
    let(:point1) { Point.new(1, 0) }
    let(:point2) { Point.new(2, 0) }
    expect(point1.distance(point1)).to eq(0)
  end
end
```

2. For this specific behaviour the dumbest possible way to pass this spec is following :

```ruby
class Point
  def distance(other)
    if self.y == other.y && self.y == 0
      1
    else
      0
    end
  end
end
```

Follow these steps until there comes a point when we have a general formula for calculating distance between two points. Then replace that long if-else ladder with that, this process is called refactoring.

The final code should be following :

```ruby
class Point
  def distance(other)
    Math.sqrt(Math.pow((self.x - other.x), 2) + Math.pow((self.y - other.y), 2))
  end
end
```

This refactoring step has nothing to do with specifications, which means they should pass without making any changes.


The above process also known as baby steps, is best way to write a robust code in the easiest way. When applying baby steps every mistake is only a baby mistake that can be noticed early and corrected easily.

The only disadvantage of baby steps additional overhead of frequent verifications, but this overhead add reliability to our system.

So, watch your steps next time you do TDD, and remember smaller is dumber and dumber is wiser.

HAPPY HACKING !!
