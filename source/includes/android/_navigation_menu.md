## 4. Navigation Menu

###Files/Classes

1. NavigationDrawerFragment
2. StoreDrawerFragment
3. DrawerFragment

###Description

The Navigation Menu has two sections,

1.	The top section displays all the top level categories for the store. If any category has sub-categories the menu will take the customer to the next level when customer clicks on the top level category and so on. The top level is implemented using the DrawerFragment class. The sub levels are implemented using StoreDrawerFragment class. The levels are switched using a viewflipper.

2.	The bottom section displays static items like Contact Us, Login, and Sign Up when the customer is not logged in. When the customer is logged in Login and Sign Up are replaced by My Account and Log Out. We can add a few other items to this section provided their content is a web page (external as well as internal).
