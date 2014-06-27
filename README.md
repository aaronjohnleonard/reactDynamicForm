reactDynamicForm
================

An HTML form that is created dynamically from a json file

This page looks for a json file that is located in the same directory. The json file must have a similar format to this:

{
  "id":*number*,
  "fields: [
    {*field*,
     *field*,
        ...  
    }
  ]
}

where a field is either a mapping of a string to a value, or a string to another json object in order to nest another list of fields.

Using this json file, a form will be generated where the id is the title, and each field is an item in the form. A mapping of a string to another string will result in a textfield. A mapping of a string to a boolean will result in a textbox. A mapping of a string to another list of fields will result in a nested list of fields.

Here is an example file:

{
	"id":"00000314159265359",
	"fields":[
		{"firstname":"Tim"},
		{"lastname":"Cash"},
		{"email":"tim@oakleon.com"},
		{"Address":"12345 fake street"},
		{"city": "San Diego"},
		{"state": "CA"},
		{"zipcode": "92119"},
		{"date_created":1392164977880},
		{"tag":"technician"},
		{"tag":"user"},
		{"comment":"This is the first comment about Tim"},
		{"comment":"Here is the second comment about Tim"},
		{"comment":"And a third comment about Tim"},
		{"roles":{
			"sales":{
				"sales1":true,
				"sales2":false
				},
			"admin":false,
			"tech":true,
			"manager":true
			}}
	]
}

In the future, options for a field may be implemented, such as text fields being required or text fields being hidden passwords.
