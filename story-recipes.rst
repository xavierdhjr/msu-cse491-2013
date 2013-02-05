Story: Recipes, round 1
=======================

Summary:

We want to support storing mixed-drink recipes and integrating them
with our inventory to figure out what we need to buy to make a particular
mixed drink.

We also want to be able to ask, given an inventory, what drink recipes could
be made.

Group: Titus B., Cait P.

Stories
-------

A. Timmy is hosting a party, and has several favorite recipes for
mixed drinks.  He wants to know what he's missing if he wants to make
a given number and type of mixed drinks, so that he can go buy it.

B. Suzy is hosting a party, and has several favorite recipes for mixed
drinks.  She wants to know which mixed drinks (and how many of each)
she can make with the current contents of her liquor cabinet.

Features
--------

1. Store named recipes.

2. Given a recipe, find out what we don't have in inventory.

3. Given an inventory and a list of recipes, find out which recipes we
   can make.

Data storage functionality
--------------------------

Recipes will consist of lists of ingredients (liquor type, amount).
They will also have a free text name.

We will need to be able to add them individually.

We will need bulk input functionality, to load multiple recipes.

We will need to be able to retrieve recipes (name & ingredients) individually.

More complex queries
--------------------

We will want to be able to get all recipes that can be made with a given
set of ingredients.
