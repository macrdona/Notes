**Data Types**

- Numbers(Integers and floats)
- Strings
- Symbols
- Boolean

**Numbers**

```ruby
2 ** 2 #=> 4 //exponents

# To convert an integer to a float:
13.to_f   #=> 13.0

# To convert a float to an integer:
13.0.to_i #=> 13

6.even? #=> true //check if odd or even
7.odd? #=> true 
```

**Strings**

```ruby
name = "Odin"
puts "Hello, #{name}" #=> "Hello, Odin" //string interpolation

#substrings
"hello"[0]      #=> "h"
"hello"[0..1]   #=> "he"
"hello"[0, 4]   #=> "hell"
"hello"[-1]     #=> "o"

#include
"hello".include?("lo")  #=> true
```

**Symbols**

Symbols, on the other hand, are stored in memory only once, making them faster in certain situations.

```ruby
#create symbol
:my_symbol
```

**Boolean**

```ruby
nil #is null in Ruby
```

**Variables**

```ruby
age = 18 #=> 18
```

**Output**

```ruby
print "Learning to code is FUN!"
puts "Learning to code is cool!!" #adds a newline at the end
```

**Input**

```ruby
new_string = gets.chomp #removes the new line
```

**Conditionals**

```ruby
if attack_by_land == true
  puts "release the goat"
elsif attack_by_sea == true
  puts "release the shark"
else
  puts "release Kevin the octopus"
end
```

**Case Statements(Switch)**

```ruby
grade = 'F'

did_i_pass = case grade #=> create a variable `did_i_pass` and assign the result of a call to case with the variable grade passed in
  when 'A' then "Hell yeah!"
  when 'D' then "Don't tell your mother."
  else "'YOU SHALL NOT PASS!' -Gandalf"
end
```

**Unless**

It only processes the code in the block if the expression evaluates to `false`.

```ruby
age = 19
unless age < 18
  puts "Get a job."
end
```

**Loop loop**

```ruby
#loop do is a loop that will run infinitely unless specifically told to stop   
i = 0
loop do
  puts "i is #{i}"
  i += 1
  break if i == 10
end


```

**While loop**

```ruby
i = 0
while i < 10 do
 puts "i is #{i}"
 i += 1
end

#use while loops to repeatedly ask a question of the user until they give the desired response
while gets.chomp != "yes" do
  puts "Will you go to prom with me?"
end

```

**Until loop**

```ruby
#until loop continues for as long as the condition is false.
i = 0
until i >= 10 do
 puts "i is #{i}"
 i += 1
end

until gets.chomp == "yes" do
  puts "Will you go to prom with me?"
end
```

**For loop**

```ruby
for i in 0..5
  puts "#{i} zombies incoming!"
end
```

**Times loop**

```ruby
#If you need to run a loop for a specified number of times
5.times do
  puts "Hello, world!"
end
```

**Arrays**

```ruby
num_array = [1, 2, 3, 4, 5]
str_array = ["This", "is", "a", "small", "array"]

Array.new               #=> []
Array.new(3)            #=> [nil, nil, nil]
Array.new(3, 7)         #=> [7, 7, 7]

#Arrays use push and pop
num_array.push(3, 5)      #=> [1, 2, 3, 4, 5]
num_array.pop             #=> [1, 2, 3, 4]

#The methods #shift and #unshift are used to add and remove elements at the beginning of an array
num_array = [2, 3, 4]
num_array.unshift(1)      #=> [1, 2, 3, 4]
num_array.shift          #=> [2, 3, 4]

#Concat and Remove from arrays
a = [1, 2, 3]
b = [3, 4, 5]
a + b         #=> [1, 2, 3, 3, 4, 5]
a.concat(b)   #=> [1, 2, 3, 3, 4, 5]

[1, 1, 1, 2, 2, 3, 4] - [1, 4]  #=> [2, 2, 3]

#Array methods
[1, 2].empty?           #=> false
[1, 2, 3].length        #=> 3
[1, 2, 3].reverse       #=> [3, 2, 1]
[1, 2, 3].include?(3)   #=> true
[1, 2, 3].join("-")     #=> "1-2-3"
```

**Hashes**

```ruby
#like dictionaries in python
my_hash = Hash.new

shoes = {
  "summer" => "sandals",
  "winter" => "boots"
}

shoes.fetch("hiking")   #=> KeyError: key not found: "hiking"

#Alternatively, this method can return a default value instead of raising an error if the given key is not found.
shoes.fetch("hiking", "hiking boots") #=> "hiking boots"

#add data
shoes["fall"] = "sneakers"

#delete data
shoes.delete("summer")    #=> "sandals"

#Methods
books = {
  "Infinite Jest" => "David Foster Wallace",
  "Into the Wild" => "Jon Krakauer"
}
books.keys      #=> ["Infinite Jest", "Into the Wild"]
books.values    #=> ["David Foster Wallace", "Jon Krakauer"]

#Merging
hash1 = { "a" => 100, "b" => 200 }
hash2 = { "b" => 254, "c" => 300 }
hash1.merge(hash2)      #=> { "a" => 100, "b" => 254, "c" => 300 }

# 'Symbols' syntax
japanese_cars = {
  honda: "Accord",
  toyota: "Corolla",
  nissan: "Altima"
}
```

**Methods**

```ruby
def greet(name = "stranger")
  "Hello, " + name + "!"
end

puts greet("Jane") #=> Hello, Jane!
puts greet #=> Hello, stranger!
```

**Debugger**

 Pry-byebug adds step-by-step debugging and stack navigation.

```ruby
#add at top of file
require 'pry-byebug'
```

**Enumerable**

```ruby
friends = ['Sharon', 'Leo', 'Leila', 'Brian', 'Arun']
invited_list = []

for friend in friends do
  if friend != 'Brian'
  invited_list.push(friend)
  end
end

#the code above can be done like this 
friends.select { |friend| friend != 'Brian' }
#or
friends.reject { |friend| friend == 'Brian' }

#Mapping
salaries = [1200, 1500, 1100, 1800]
salaries.map { |salary| salary - 700 }
#=> [500, 800, 400, 1100]

```

****

**Nested Arrays**

```ruby
#Accessing Elements
teacher_mailboxes[0][0]

#Creating 2D array
immutable = Array.new(3) { Array.new(2) }
#=> [[nil, nil], [nil, nil], [nil, nil]]

#Adding
test_scores[0].push(100)

#removing
test_scores[0].pop
```

**Nested Hashes**

```ruby
vehicles = {
  alice: {year: 2019, make: "Toyota", model: "Corolla"},
  blake: {year: 2020, make: "Volkswagen", model: "Beetle"},
  caleb: {year: 2020, make: "Honda", model: "Accord"}
}
vehicles[:alice][:year]
#=> 2019
```

**Classes**

```ruby
class Language
  def initialize(name, creator)
    @name = name
    @creator = creator
  end
 end

ruby = Language.new("Ruby", "Yukihiro Matsumoto")
ruby.description
```

**Calling Classes in other files**

```ruby
#file: foo.rb
class Foo
  def initialize
    puts "foo"
  end
end

#file: bar.rb
require 'foo'

Foo.new
```