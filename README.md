# Huawei SMS forwarding
A python CLI program that allows you to forward SMS received by your Huawei router to a phone number.

**Why ?** <br />
I always wanted to use my router phone number but going on the router local website to check my SMS is not really convenient, so I needed to find a way to forward SMS that also allows me to filter some of them.

**Note:** <br />
This program uses the [Huawei LTE API](https://github.com/Salamek/huawei-lte-api) created by [Salamek](Salamek).


## Features:
- **Forwarded SMS format**: Forwarded SMS contains the date and the sender's phone number/contact.
- **Contacts**: To replace raw phone numbers by contact names inside the forwarded SMS.
- **Whitelist**: Only SMS received by phone numbers in this list are forwarded.
- **History**: A JSON file that contains all the forwarded SMS with their date and their content.


## The .env file:
All the parameters used by this program are stored inside a single .env file (in the same directory as `app.py`).

This file is created when the program is launched for the first time or if the program don't find the .env file,
the program will then terminate and ask you to fill the needed info inside of it.

You can find an example for the .env file inside `.env.sample`.

**Note:** <br />
As you see, the account username and password is needed to connect to the router, it is not a big deal because these can
only be used by someone connected to your local network, but don't hesitate to check my code to be sure that
never send them anywhere.


## History:
Here's an example of a forwarded SMS inside the history.

![](https://github.com/yoratoni/huawei-router-sms-forwarding/blob/main/doc/History.png "History example")

**Details**: <br />
- "40086" corresponds to the SMS ID (used by the router to identify every SMS).
- "Phone" is the phone number (not impacted by the contact names).
- "Content" is simply the content of the SMS
- "Date" is the date when the SMS has been received, not forwarded.
- "ContactName" is the contact name that you added to the .env file or "NONE" if not added to the list.


## Compatibility:
**Note**: Tested only on a B525s-65a but it should work with the routers listed inside the [Huawei API](https://github.com/Salamek/huawei-lte-api#tested-on) doc.

#### 3G/LTE Routers:
* Huawei B310s-22
* Huawei B315s-22
* Huawei B525s-23a
* Huawei B525s-65a
* Huawei B715s-23c
* Huawei B528s
* Huawei B535-232
* Huawei B628-265
* Huawei B818-263
* Huawei E5186s-22a
* Huawei E5576-320
* Huawei E5577Cs-321
* SoyeaLink B535-333

#### 3G/LTE USB sticks:
(Device must support NETWork mode aka. "HiLink" version, it wont work with serial mode)
* Huawei E3131
* Huawei E3372
* Huawei E3531

#### 5G Routers:
* Huawei 5G CPE Pro 2 (H122-373)

(probably will work for other Huawei LTE devices too)

#### Will NOT work on:
* Huawei B2368-22 (Incompatible firmware, testing device needed!)
* Huawei B593s-22 (Incompatible firmware, testing device needed!)
