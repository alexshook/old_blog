---
layout: post
title: "Learn Ruby the Hard Way Ex. 1-5"
date: 2016-01-07 20:24:35 -0500
comments: true
categories: [ruby, learn ruby the hard way]
---
Remember when I said I was going to do the entire [Learn Ruby the Hard Way](http://learnrubythehardway.org/book/) again? I got up to like exercise 18… and then forgot about it.

I’m starting from the first exercise again and tracking my progress here so I actually finish this time. Here are exercises 1-5. No bonuses because too lazy.

``` ruby
puts "ex 1"

puts "Hello World!"
puts "Hello Again"
puts "I like typing this."
puts "This is fun."
puts 'Yay! Printing.'
puts "I'd much rather you 'not'."
puts 'I "said" do not touch this.'

puts "ex 2"

puts "I could have code like this." # and the comment after is ignored.
puts "This will run."

puts "ex 3"

puts "I will now count my chickents:"

puts "Hens", 25 + 30 / 6
puts "Roosters", 100 - 25 *3 % 4

puts "Now I will count the eggs:"

puts 3 + 2 + 1 - 5 + 4 % 2 - 1 / 4 + 6

puts "Is it true that 3 + 2 < 5 - 7?"

puts 3 + 2 < 5 - 7

puts "What is 3 + 2?", 3 + 2
puts "What is 5 - 7?", 5 - 7

puts "Oh, that's why it's false."

puts "How about some more."

puts "Is it greater?", 5 > 2
puts "Is it greater or equal?", 5 >= -2
puts "Is it less or equal?", 5 <= -2

puts "ex 4"

cars = 100
space_in_a_car = 4.0
drivers = 30
passengers = 90
cars_not_driven = cars - drivers
cars_driven = drivers
carpool_capacity = cars_driven + space_in_a_car
average_passengers_per_car = passengers / cars_driven

puts "There are #{cars} cars available."
puts "There are only #{drivers} drivers available."
puts "There will be #{cars_not_driven} empty cars today."
puts "We can transport #{carpool_capacity} people today."
puts "We have #{passengers} passengers to carpool today."
puts "We need to put about #{average_passengers_per_car} in each car."

puts "ex 5"

my_name = 'Zed. A Shaw'
my_age = 35
my_height = 74
my_weight = 180
my_eyes = 'Blue'
my_teeth = 'White'
my_hair = 'Brown'

puts "Let's talk about %s." % my_name
puts "He's %d inches tall." % my_height
puts "He's %d pounds heavy." % my_weight
puts "Actually that's not too heavy."
puts "He's got %s eyes and %s hair." % [my_eyes, my_hair]
puts "His teeth are usually %s depending on the coffee." % my_teeth

puts "If I add %d, %d, and %d I get %d." % [ my_age, my_height, my_weight, my_age + my_height + my_weight ]

```
