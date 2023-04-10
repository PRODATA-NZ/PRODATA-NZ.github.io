---
title:  How to Create a Generic Class-Based Django View for Create and Update Functions
date:   2022-05-14 17:24:35 +0800
categories: django
---

How to Create a Generic Class-Based Django View for Create and Update Functions
===============================================================================

Django is a powerful web framework for building web applications quickly and easily. One of the most useful features of Django is its built-in support for generic class-based views. In this article, we will show you how to create a generic class-based Django view that performs both create and update functions so it can be used as a single class-based view instead of creating two separate view classes.

The Problem with Creating Separate Views
----------------------------------------

Traditionally, when building a Django application, you would create two separate views: one for creating new objects and one for updating existing objects. This can lead to a lot of duplicated code, and it can make your application more difficult to maintain over time. Fortunately, Django's generic class-based views offer a solution to this problem.

Using CreateView and UpdateView Together
----------------------------------------

Django's generic class-based views are built on top of Python's class-based views, which allow you to define your views as classes instead of functions. This can make your views more organized and easier to read. To create a generic class-based view that performs both create and update functions, we can use Django's `CreateView` and `UpdateView` views together in a single class.

{% highlight python %}

from django.views.generic.edit import CreateView, UpdateView
from django.urls import reverse_lazy
from myapp.models import MyModel

class CreateUpdateView(CreateView, UpdateView):
    model = MyModel
    fields = ['field1', 'field2', 'field3']
    template_name = 'myapp/my_template.html'
    success_url = reverse_lazy('myapp:success_url')

    def get_object(self, queryset=None):
        obj = super().get_object(queryset)
        if obj:
            # if object exists, it is an update
            self.success_url = reverse_lazy('myapp:update_success_url', args=[obj.pk])
        else:
            # if object does not exist, it is a create
            self.success_url = reverse_lazy('myapp:create_success_url')
        return obj

{% endhighlight %}

In this example, the `CreateUpdateView` class inherits from both the `CreateView` and `UpdateView` generic views. It specifies the `MyModel` model as the model to be used for both creating and updating objects, and lists the fields that should be displayed in the form.

The `get_object` method is overridden to determine whether the view should perform a create or update operation. If an object exists, it is an update operation, and the success URL is set to a URL that includes the object's primary key. If an object does not exist, it is a create operation, and the success URL is set to a URL that indicates that a new object has been created.

Conclusion
----------

By using Django's generic class-based views, we can create more organized and easier to maintain views in our Django applications. By combining the `CreateView` and `UpdateView` views together in a single class, we can create a generic view that performs both create and update functions, reducing duplicated code and making our application more maintainable over time.

