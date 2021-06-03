## Overview

The Furnishment API allows you to manage consumers, their accounts as well as activity on those accounts for furnishing to the credit bureaus at any configurable interval. This process also incentivizes the consumers to make payments regularly and build their credit.

You provide account statements for each of your consumers over time, and the Furnishment API will aggregate the data allowing you to create furnishment submissions to the credit bureaus. If an account produces more than one statement in a calendar month, the Furnishment API will take the most relevant (latest) statement available within the specified time range.

The following workflow diagram shows the process of creating consumers, accounts, and furnishing statements. 

Organizations create credit products. Organizations may or may not have customers for credit products. When a customer is issued a credit product, a customer record is created and products are linked via the consumer's account. Statements are submitted for each account within a reporting cycle and the payments from the account holders are included within the statement accordingly. Lastly, the organization can create a furnishment to submit to the bureaus, verifying all aggregated data before it's sent.

![image](https://user-images.githubusercontent.com/59159392/119357735-88861580-bcc5-11eb-8347-4b0fe9732704.png)

### Endpoints / Models
During onboarding, Bloom Credit will work with you to set up products within the Furnishment API. After you set up a [credit product](#credit-product), you can create [consumers](#consumer) and [accounts](#accounts).

A credit product is used to create classes of accounts that share common characteristics. Typically a credit product is 
<ul><li>a type of loan</li>
  <li>a specific credit card line</li>
  <li>or a type of mortgage</li> </ul>

A credit product will hold attributes that are common among a group of accounts. Each account must be associated with a credit product. With a credit product and a consumer, you can create an account. Once an account is created, you can start posting the account statements through the Furnishment API.

## Credit Products

A company may offer a variety of products to its customers, each having its own unique characteristics.

When a company signs a customer to one of its products, the outcome is the creation of a new customer ID and its related account(s). An account is an instance of a credit product and its relation to one or more consumers. A credit product can also be thought of as a grouping of accounts that belong to the same class.

For example, a customer has a home loan or a vehicle loan with the organization named: Sunset. When comparing the products, each loan might offer different features, interest rates, and other terms. All these are updated by the organization through Furnishement API. 

When a customer applies for a loan, the credit of the customer is checked to see whether the customer qualifies for a loan and then only the loan is approved. 

Upon the loan being approved, Sunset signs a new customer, and a new account is created under the chosen product. A single customer may hold multiple accounts (i.e. credit cards, loans) at Sunset, each with the same or different credit product.

The customer must pay the based on the terms of the credit product and the payment information is furnished to the bureaus by the credit company through the Furnishment API.

<strong>Note:</strong> Bloom Credit helps you with onboarding by creating a credit product and adding consumers.

Once you have created the product, start with adding consumers and their [accounts](#accounts).

## Consumer
A consumer is someone who holds one or more accounts with a company. For example, John Parker can have two home loans from Sunset bank, but each home loan will have a separate account number associated with it. There will be a single consumer record with the name John Parker and the two loan card accounts are associated with that record.

With the Furnishment API, you can create, update, retrieve, and delete the consumers.

The Furnishment API allows you to create all the required information about the customer. The required fields are:
<ul><li>First name</li>
  <li>Last Name</li>
  <li>Address</li>
  <li>Date of Birth</li>
  <li>SSN</li></ul>  
  
  ![image](https://user-images.githubusercontent.com/59159392/119357728-858b2500-bcc5-11eb-953d-a2b40aca7aef.png)
  
  <strong>Note:</strong> To start using Furnishment API, you must create a consumer. 
  
  Once you have created a consumer, start making accounts.
  
  ## Accounts
  
One consumer can hold multiple accounts. If a consumer has multiple accounts with the same product such as a home loan with the same bank, then all the accounts will have the same Consumer name but a unique account ID that provides consumer loan details, EMI payment history, and principal amount balance details.  
  
  You can push all consumers’ account details separately and their statements.  
  With the Furnishment API, you can create, update, retrieve, and delete the accounts.
  The account details include:
  <ul><li>Credit Product ID</li>
  <li>Primary Consumer ID</li>
  <li>Primary Address</li>
  <li>Primary Designation</li>
  <li>Branch Identifier</li>
  <li>Account Opened Date</li></ul>
  
  Once you create an account, you can start furnishing statements. The statement includes:
  
  <ul><li>Customer details</li>
  <li>Account details</li>
  <li>Payment details</li></ul>
  <strong>Note:</strong> You must create a credit product and a consumer before creating an account. A consumer can have many accounts.
