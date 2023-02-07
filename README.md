# fundamental-of-javascrips

## sort() methods

Array of Strings
Let's start with strings:

const teams = ['Real Madrid', 'Manchester Utd', 'Bayern Munich', 'Juventus'];

When we use the sort( ) method, elements will be sorted in ascending order (A to Z) by default:

teams.sort(); 

// ['Bayern Munich', 'Juventus', 'Manchester Utd', 'Real Madrid']
If you prefer to sort the array in descending order, you need to use the reverse( ) method instead:

Array of Numbers
    Sorting numbers is unfortunately not that simple. If we apply the sort method directly to a numbers array, we will see an unexpected result:


const numbers = [3, 23, 12];

numbers.sort(); // --> 12, 23, 3

Why the sort( ) method isn't working for numbers
    Actually it is working, but this problem happens because JavaScript sorts numbers alphabetically. Let me explain this in detail.
    
solution

All we need to is using the compare function inside the sort( ) method:

const numbers = [3, 23, 12];

numbers.sort(function(a, b){return a - b}); // --> 3, 12, 23


If we want to sort the numbers in descending order, this time we need to subtract the second parameter (b) from the first one (a):

const numbers = [3, 23, 12];

numbers.sort(function(a, b){return b - a}); // --> 23, 12, 3
