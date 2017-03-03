# APEX CODE CONVENTIONS

## 1. Class naming

* CamelCase starting from uppercase letter only.
* Singular nouns combinations only.
* Keep classes named using the full name of the object they primarily affect and postfix with class type.
  Class types:
  * Batch
  * Controller
  * Extension
  * Schedule
  * WebService
  * Exception
  * Interface
  * Test
  * TriggerHandler
* Test class names are the exact copies of tested class names postfixed with “Test”.
* Controller class names are the exact copies of its pages names postfixed with “Controller”.

|Bad :(                     |Good!                       |
|---------------------------|----------------------------|
|HomePageCtrl               |HomePageController          |
|OppTriggerHandler          |OpportunityTriggerHandler   |
|PopulateOrders_Batch       |OrderPopulationBatch        |
|TestAccountsWebServices    |AccountWebServiceTest       |


## 2. Variable naming

* CamelCase starting from lowercase letter only. Exceptions are:
  * Loop variables (postfix with “_i”);
  * Custom Object fields (start with capital letter, split words with underscores).
* No abbreviations. No acronyms.
* Always include full class name in instance variables.
* Postfix collections with collection type. Use singular noun forms.
* Use “To” between key and value descriptions in map names (unnecessary for standard maps from object primary key Id to object).
* Use clear, meaningful names.

|Bad :(                     |Good!                       |
|---------------------------|----------------------------|
|InsertAccount              |accountToInsert             |
|test_opp1                  |firstTestOpportunity        |
|PopulateOrders_Batch       |OrderPopulationBatch        |
|TestAccountsWebServices    |AccountWebServiceTest       |
|opportunitiesToUpdate      |opportunityToUpdateList     |
|fieldsMapping              |jsonFieldToInternalFieldMap |
|opportunitiesMap           |triggeredOpportunityMap     |
|uniqueData                 |orderSet                    |


## 3. Method naming

* CamelCase starting from lowercase letter only.
* Prefer using verbs in method names.
* Leave “get” and “set” prefixes for getters and setters only. Use “obtain” and “specify” instead.
* Postfix method names returning non-primitive types with corresponding class name.

|Bad :(                     |Good!                       |
|---------------------------|----------------------------|
|getOpportunities           | obtainWonOpportunityList   |


## 4. Constants naming

* Constants (i.e. variables defined as static final) should be in uppercase with words separated by underscores:
```java
public static final String PAYPAL_LOGIN_URL = 'https://login.paypal.com/';
```

## 5. SOQL and SOSL queries

* SOQL and SOSL commands should be in uppercase:
```SQL
SELECT Id, Name, Custom_Field__c
  FROM Contact
 WHERE Name != null
```

## 6. Comments

All methods must have a comment. Depending on the number of lines of code within a method comment as much as possible. Note that someone else will be maintaining the code. Use Javadoc commenting style (http://www.oracle.com/technetwork/java/javase/documentation/index-137868.
html) which can then be consumed by ApexDocs (https://gitlab.com/StevenWCox/sfapexdoc) to generate documentation easily.

``` java
// Classes should be commented as follows:
/**
* Description of class
* 1.0 Name DD/MM/YYYY Description
*
* @author yourname
* @date 02/08/2013
*
*/
public class SomeClass {
    // Methods should be commented as follows:
    /**
    * Descriptionoffunction
    * @author YourName
    * @date 11/27/2012
    * @param param1: Description of param1
    * @param param2: Description of param2
    * @see AnotherClass
    * @return void
    */
    public static void someFunction(
        String param1,
        String param2
    ){
        // Method body goes here..
    }
}
```
