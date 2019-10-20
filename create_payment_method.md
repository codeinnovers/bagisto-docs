---
title: Creating Payment method-Bagisto
layout: default
---

# Payment Method

![](assets/images/icons/Icon-Pencil-Large.svg){:.pencil-icon}
[edit on github](https://github.com/bagisto/bagisto-docs/blob/master/create_payment_method.md){:.edit-github target="\_blank"}

I hope that you know how to create package, if not(refer [Package development](create_package.md){: target="\_blank"}), and I will skip package development step

Bagisto ease the task of creation of payment method so novice developer or professional developer can easily create payment methods. As diversity of payment methods provide the options to customer for payment when they proceed to checkout. On another perspective, multiple payment methods is a great strategy to reach out the global marketplace.

In this article, we will understand how to create payment method by own with just following steps:

### Steps to create payment method

- Following the module development process, firstly, you must create '**Config**', '**Database**', '**Resources**', '**Providers**', '**Models**', '**Payment**', '**Repositories**', '**Http**', '**Listeners**' folders under src folder of your company's namespace.

- Within **Config** folder, contains all of your application's configuration files. Let's just create two files as _system.php_ and _paymentmethod.php_

  **system.php**

  - Inside the file, you can include the below code as shown in image

    ![system-configuration](assets/images/Bagisto_Docs_Images/payment-config-1.png){: .screenshot-dimension .center}

##### Explanation for the keys:

1. **key** : these values provided are unique and concatenated with '.' (dot) operator. After creation of two nested, other keys written are display in browser in form of accordian

2. **name** : these keys accept the value as placeholder of your configuration. Generally, in bagisto, we consider writing it using translation.

3. **sort** : these key accept the sort position for the configuration menu.

4. **fields** : these key accepts the array for the value of custom configuration.


    **paymentmethod.php**

    ![payment-method-configuration](assets/images/Bagisto_Docs_Images/payment-config-2.png){:  .screenshot-dimension .center}

##### An Explanation For These Parameters:

1.  **code** : a text to represent payment method

2.  **title** : in this field, the name of payment method is specified

3.  **description** : a brief description of payment method.

4.  **class** : this field includes the class namespace where all functions of payment method is written

5.  **sandbox** : this is a custom option of boolean type

6.  **active** : this field accepts true/false to enable or disable module.

- Within **Database** folder, the migration and seeder(if needed) files are stored.

- Within **Resources** folder, contains your views as well as your raw, un-compiled assets such as SASS, or JavaScript. This directory also houses all of your language files.

- Within **Providers** folder, contains all of the service providers for your application. Service providers bootstrap your application by binding services in the service container, registering events, or performing any other tasks to prepare your application for incoming requests.

  Here, in our case we have created two providers files i.e.,

  1. **_EventServiceProvider_** : In this file, events included with your application provides a convenient place to register all of your application's event listeners.

  2. **_PaymentServiceProvider_** : In this file, you may register all your configuration, language and routes within register and boot methods.

* Within **Models** folder, the models are stored for the application.

* Within **Payment** folder, write the code needed to operate your payment method

* Within **Repositories** folder, create a file as _HelloWorldRepository.php_ which must extends repository class

* Within **Http** folder, define your routes and controller application.

* Within **Listeners** folder, this folder includes listener files to listen respective events.
