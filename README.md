# refactor

X: It seems a good written code I will give 9/10. 
What it makes a good code. 
1. Controller is doing what is should do like dealing requests. 
2. Class/functions/variables names are according to php naming conventions. variables written with under scores but I prefer with camel case.
3. All Functions are written with their approperiate definations.
4. Access modifiers are used properly.
5. Functions length (in terms of lines in a function) is perfect and new function made/called in case function get larger.
6. Code indentation is good at most places. At very few places its needs little bit refactoring.  
7. Logically, its looking good. 
8. Functino parameters are okay but can be better if We can add parameter type (where nessesary) like string, int, array with return type eg: function setName (string $name) : string

9. Commented code should be removed if not required. 
10. The only classes which are being used, are imported not any extra classes are imported which are not being used 
10. Variables are defined very near to their use and its good practice. 

SUGGESTIONS: 
1. Some functions I see written in BookingRepository 
Which could be moved to their corresponding models instead doing the stuff in same class e.g: ignoreThrottle() updating Throttles model.

2. I see the user_type == env('ADMIN_ROLE_ID'), hope there is only one to one relationship between user and role but in most projects there is always many to many relationship between "users", "roles". to achive it (if required) we can use spatie/laravel or github.com/paxha/lararole (which I use mostly), provides a beautiful scafolding to manage users, their roles and modules assigned to roles. 

3. At few places, I see $job->save(); $tr->save(); which saving/updating translatorJobRel() and jobs which are dependent on each other so 
it would be better to use db transations (laravel built in methods to handle database related exceptions) which ensures every thing saving as expected, in case of error in many model while saving, it revert all operations which ensures that the correct data inserted/updated into database. 



