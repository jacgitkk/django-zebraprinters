# django-zebraprinters
Print ZPL to Zebra Printers

This is a beta app I am using in an inventory system.  It was written for Django 1.9x and intended for sending the ZPL TCP from the server to the network Zebra printer.

Use/Modify at your own risk.  There is currently no resending/logging of data sent.

**Requires Celery !!**

## Installation
- Add the app to your project.
- Run a migration to create the database tables.
- Create a Printer(name and ip of Zebra Printer, default port is 9100)
- Create a Document_Template(using Django template formatting to inject variables into your ZPL string).

## How To Use
```
from zebraprinters import models as zebraprinters

context_dict = {
	'property': 'value',
}

zebraprinters.print_label('printer_slug','doc_slug',context_dict)
```

## Wishlist
- Allow non-celery print jobs with a settings variable