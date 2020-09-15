# Context in Djanog

Django is python web application framework.
- Battery included : it's quick to have your web page prototype ready, since all functions include.

- More customization in Server side processing: use `function` to implement.
- Quick implementation in Server side processing: use `class` to implement.
	- It's wrap all functions already.
	- It still open the flexibility by using "context".
	
	- To get it :
	```context = super(BookView, self).get_context_data(**kwargs)```
	
	- To add more value to output:
	```context['publishers'] = self.object.publishers.filter(is_active=True)```
			
	- So, it's like setting session variable.
			

