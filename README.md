# Macros and Abstraction

## Objectives

1. Learn the definition of a macro.
2. See how macros can abstract away the explicitly defined setter and getter methods in a Ruby class. 

## What is a Macro?

A macro is any code that writes code for you. The implementation of macros is considered metaprogramming––the writing of programs that operate on other programs. 

Implement macros to abstract away the manual, explicit definition of setter and getter methods in a Ruby class. 

## Attribute Readers and Writers

In object-oriented Ruby, there is a strong convention to have a setter and a getter method that pertain to the same attribute. For example, a `.name` getter and a `.name=` setter on our Person class. Because this pattern is so common, we find ourself making this manual setter and getter definitions again and again. As Rubyists, we are lazy, and this is a virtue. If we can achieve the same result with less code, we'll do it. 

Check out the example below: 

```ruby
class Person

  attr_reader :name
  attr_writer :name
  
end
```

The `attr_reader` macro, followed by the attribute name `:name`, *created a getter method for us*. 

The `attr_writer` macro, followed by the attribute name `:name`, *created a setter method for us*. 

We can now do the following, without explicitly defining a `.name` or `.name=` method ourselves: 

```ruby
jay_z = Person.new
jay_z.name = "Shawn Carter"
jay_z.name 
  => "Shawn Carter"
```

The usage of macros is preferred over the explicit definition of setter and getter methods, unless you need to customize the implementation of a method, like in our previous lesson when we defined `.name` as returning and first and last name variable combined. 

