# Bookmarks - social website

A social app that allow users share images they find on the internet

## Table of Contents

- [Example](#example)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Features](#features)
- [Deployment](#deployment)

## Example

```python
@login_required
def edit(request):
    if request.method == 'POST':
        user_form = UserEditForm(instance=request.user, data=request.POST)
        profile_form = ProfileEditForm(instance=request.user.profile,
                                       data=request.POST,
                                       files=request.FILES)
        if user_form.is_valid() and profile_form.is_valid():
            user_form.save()
            profile_form.save()
            messages.success(request, 'Profile updated successfully')
        else:
            messages.error(request, 'Error updating your profile')
    else:
        user_form = UserEditForm(instance=request.user)
        profile_form = ProfileEditForm(instance=request.user.profile)
    return render(request,
                  'account/edit.html',
                  {'user_form': user_form,
                   'profile_form': profile_form})
```

### Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

## Prerequisites

What things you need to install the software and how to install them

- Python 3
- Pip install packages

## Installation

To get a development env running:

> clone this repo to your local machine

```shell
git clone https://github.com/JohnJohnsonOkah/bookmarks.git
```

> install requirements

```shell
pip install -r requirements.txt
```

> setup database

```shell
python manage.py migrate
```

> create superuser

```shell
python manage.py createsuperuser
```

> run development server

```shell
python manage.py runserver
```

... 👯 Now development server is up and running...

## Features

- Register a user account
-

## Deployment

Additional notes about how to deploy this on a live system
