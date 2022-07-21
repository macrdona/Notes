**Read File Contents**

```ruby
#open file
contents = File.read('event_attendees.csv')

#check if file exists
File.exist? "event_attendees.csv"

#Read file line by line
lines.each do |line|
  puts line
end

#Split each line into columns
lines.each do |line|
  columns = line.split(",")
end

#Skip headers
lines.each_with_index do |line,index|
  next if index == 0 #if row = 0 then skip
  columns = line.split(",")
  name = columns[2]
end
```

**CSV Parser**

```ruby
require 'csv'
puts 'EventManager initialized.'

contents = CSV.open('event_attendees.csv', headers: true)
contents.each do |row|
  name = row[2]
end

#Accessing columns by converting headers to symbols
contents = CSV.open(
  'event_attendees.csv',
  headers: true,
  header_converters: :symbol
)

contents.each do |row|
  name = row[:first_name]
  zipcode = clean_zipcode(row[:zipcode])
end
```

**Storing strings with multiple lines**

```ruby
string = %{string content}
```

**Ruby's ERB**

ERB provides an easy to use but powerful templating system for Ruby. Using ERB, actual Ruby code can be added to any plain text document for the purposes of generating document information details and/or flow control.

```ruby
require 'erb'

require 'erb'

meaning_of_life = 42

question = "The Answer to the Ultimate Question of Life, the Universe, and Everything is <%= meaning_of_life %>"

#this creates an ERB template with the 'question' string
template = ERB.new question

#An instance of binding knows all about the current state of variables and methods within the given scope. In this case, binding knows about the variable 'meaning_of_life'
results = template.result(binding)
puts results
```

```html
<!--Example of how to apply ERB in HTML doc. This file should use (.erb) extension instead of (.html)-->
<html>
<head>
  <meta charset='UTF-8'>
  <title>Thank You!</title>
</head>
<body>
  <h1>Thanks <%= name %></h1>
  <p>Thanks for coming to our conference.  We couldn't have done it without you!</p>
</body>
</html>
```

**Serialization**

Serialization is the process of converting an object into a stream of bytes to store the object or transmit it to memory, a database, or a file.

**YAML File Format**

```yaml
name: "David"
height: 124
age: 28
children:
  "John":
    age: 1
    height: 10
  "Adam":
    age: 2
    height: 20
  "Robert":
    age: 3
    height: 30
traits:
  - smart
  - nice
  - caring
```

```ruby
#Open YAML file in Ruby
require 'yaml'

YAML.load File.read('test.yaml')

#Formatted results
{"name"=>"David",
 "height"=>124,
 "age"=>28,
 "children"=>{"John"=>{"age"=>1, "height"=>10},
             "Adam"=>{"age"=>2, "height"=>20},
             "Robert"=>{"age"=>3, "height"=>30}},
 "traits"=>["smart", "nice", "caring"]}
```

**Create output folder**

```ruby
Dir.mkdir('output') unless Dir.exist?('output')

filename = "output/thanks_#{id}.html"

#save data to file
File.open(filename, 'w') do |file|
    file.puts form_letter
end
```

**Yield**

Allows you to output something with what ever format you want

```ruby
def awesome_method
  hash = {a: 'apple', b: 'banana', c: 'cookie'}

  hash.each do |key, value|
    yield key, value
  end
end

awesome_method { |key, value| puts "#{key}: #{value}" }
#output
#=> a: apple
#=> b: banana
#=> c: cookie
```

**Lambdas vs Procs**

Difference is Procs do not care if you pass the correct amount of arguments, while Lambdas will raise an error if you pass the incorrect number of arguments

```ruby
my_name = ->(name) { puts "hello #{name}" }
my_name.call("tim")
#=> hello tim

a_proc = Proc.new { |a, b| puts "a: #{a} --- b: #{b}" }
a_proc.call("apple")
# => a: apple --- b:
```