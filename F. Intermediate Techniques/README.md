# Intermediate Techniques - Exercises

1. Write a function that prints all the even numbers between 1 and 10,000.

2. Write a function that returns a list of the numbers between 1 and 10,000 that are divisible by 3.

3. The same as 2, but use Python list comprehensions

4. Write a function `get_max` that takes a list of numbers and returns the max of those numbers, don't use the builtin `max()` function. Afterward,  try using `max()`

5. Write a function `is_odd_or_div_by_7` that returns True if a number is odd or divisble by 7 and False otherwise.

6. Use `is_odd_or_div_by_7` and list comprehensions to write a function `get_sublist_of_numbers_odd_or_div_by_7` that takes in a list and returns a sublist of those numbers that are either odd or divisible by 7.

7. Write a division function `divide(a, b)` that catch exceptions and return an error string if the arguments do not make sense.

8. Given a list of food orders, e.g. ```["burger", "fries", "burger", "tenders", "apple pie"]```, write a function `get_aggregate_order_counts` that takes the list and returns a dictionary with the different dishes as keys and the number of times they appear in the list as the values. For example, it takes ```["burger", "fries", "burger", "tenders", "apple pie"]``` and outputs ```
{
   "burger": 2,
   "fries": 1,
   "tenders": 1,
   "apple pie": 1
}```

9. Write a function `get_most_popular_order_data` that takes a list of orders but instead of returning a dictionary with the counts, it just outputs a tuple: the dish that appears the most in the list and the number of times it appears in the list. So the output given the example would be ```("burger", 2)```
