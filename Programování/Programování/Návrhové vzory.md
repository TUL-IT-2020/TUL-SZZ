# Návrhové vzory
- Factory
- Dekorátor
- Observer
- Chain of responsibility

``` Python
class Request():

class Handler():
	limit: Request
	
	def __init__(handler: Request):
		self.next_handler = handler
	
	def Request handle (req: Request):
		if req < self.limit:
			# Do something
		else:
			return self.next_handler.handle(req)
```


