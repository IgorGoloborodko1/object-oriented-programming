# Using Properties
## Properties
As a part of encapsulation, you should consider using properties in your class files. Properties enable you to permit users, of the class, a means of getting and setting values for the private member data fields within your class. Properties provide access to the member data while hiding implementation or verification code that you may have written inside the property. For example, you may want to validate a birth date that has been passed in to ensure it is in the proper format or that it is in the correct range for the application's usage. Setting your member variables to private is known as a form of data hiding. Some also consider data hiding to be part of encapsulation.

Properties also present an "interface" to your class by exposing a way to get or set the members of the class that the user can trust. In other words, if you have a property called public Birthdate(date birth), that accepts a birth date from a user, you can implement the validation code in anyway you see fit, such as using regular expressions to validate or perhaps some custom logic to verify the date range, and then later change that validation logic without impacting the use of the property. Users still just pass in a birth date in date format.

The following code shows an example of properties being declared in the DrinksMachine class:
```
public class DrinksMachine
{
   // private member variables
   private int age;
   private string make;


   // public properties
   public int Age
   {
      get
      {
         return age;
      }
      set
      {
         age = value;
      }
   }
   public string Make
   {
      get
      {
         return make;
      }
      set
      { 
         make = value;
      }
   }
   
   // auto-implemented property
   public string Model { get; set; }

      // Constructors
   public DrinksMachine(int age)
   {
      this.Age = age;
   }
   public DrinksMachine(string make, string model)
   {
      this.Make = make;
      this.Model = model;
   }
   public DrinksMachine(int age, string make, string model)
   {
      this.Age = age;
      this.Make = make;
      this.Model = model;
   }
}
```
The properties are Age, Make, and Model. These properties would be backed by private member variables called age, make, and model.

### Property Types

You can create two basic types of properties in a C# class. Read only or read-write: (Technically you can also create a write-only property but that is not common.

* A get property accessor is used to return the property value

* A set accessor is used to assign a new value. (Omitting this property makes it read only)

* A value keyword is used to define the "value" being assigned by the set accessor.

* Properties that do not implement a set accessor are read only.

* For simple properties that require no custom accessor code, consider the option of using auto-implemented properties.

Auto-implemented properties make property-declaration more concise when creating simple accessor methods (getter and setter). They also enable client code to create objects. When you declare a properties this way, the compiler will automatically create a private, anonymous field in the background that can only be accessed through the get and set accessors.

The following example demonstrates auto-implemented properties:
```
// Auto-implemented properties 
public double TotalPurchases { get; set; }
public string Name { get; set; }
public int CustomerID { get; set; }
```
