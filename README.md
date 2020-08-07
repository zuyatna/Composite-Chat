# Composite
Composite is a structural design pattern that lets you compose objects into tree structures and then work with these structures as if they are were individual objects.

# Problem
For example, imagine that you have two types of objects: Products and Boxes. A Box can contain several Products as well as a number of smaller Boxes. These little Boxes
can also hold some Products or even smaller Boxes, and also so on.

Say you decide to create an ordering system that uses these classes. Orders could contain simple products.. and other boxes. How would you determine the total price of such
an order?

You could try the direct approach: unwrap all the boxes, go over all the products and then calculate the total. That would be doable in the real world; but in a program,
it's not as simple as running a loop. You have to know the classes of Products and Boxes you're going through, the nesting level of the boxes and other nasty details beforehand.
All of this makes the direct approach either too awkward or even impossible.

# Solution
The Composite pattern suggests that you work with Products and Boxes through a common interface which declares a method for calculating the total price.

How would this method work? For a product, it'd simply return the product's price. For a box, it'd go over each item the box contains, ask its price and then return a total
for this box. If one of these items were a smaller box, that box would also start going over its contents and so on, until the prices of all inner components were calculated. 
A box could even add some extra cost to the final price, such as packaging cost.

The greatest benefit of this approach is that you don't neet to care about the concrete classes of objects that compose the tree. You 