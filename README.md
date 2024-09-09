# E-Wallet-Management-System
  EBSM is an organization, want to develop an application which can be used by citizen for their  day-to-day money transactions without carrying the money physically. They proposed to create  an application named “E-Wallet Management System” which the following requirements:
  1.The customer must register to the application by providing the necessary details and must authenticate by entering the OTP sent to their mobile number and the customer must provide the secured PIN number for further transactions.
2.On successful registration, the customers can perform the below listed tasks:
A)Add Bank – The customers can add multiple bank details.
B)Payment - The customers will choose this option to do the payments by entering the receiver’s mobile number. The transaction will be successful only on entering the valid PIN which they have provided at the time of registration.
C)Transaction History – The customers will be able to view the reports as listed below
I)View all Transactions – The customer can view all the transactions.
II)All transactions by mobile number – The customer can view all the transactions specific to mobile number.
III)Last Month Transactions – The customer can view all the transactions performed in last month.
IV)Current Month Transactions – The customer can view all the transactions performed in the current month

The process for E-Wallet Management System is as following:
a.Accept the customer information via digital form
b.Customer needs to add his/her bank details to any transaction.
c.Once he/she adds the bank details we need to verify him with OTP.
Once verification is done, now the customer can able to perform digital transaction using mobile number.
e.While performing transaction, we are going to verify it using OTP.
f.Before performing the transaction internally, it should check whether balance is available or not.
g.If available balance is less than the transaction amount, the transaction should fail by showing available balance is less.
h.After transactions is done we need to provide some info regarding the previous or current transaction information.

Enhancements:

a.Customer can check balance in his/her account
b.Customer can update his /her profile. Like updating email, mobile number, address. If an email is updated it should be accepted using OTP validation to the new email address
c.Customer can search the transactions between two dates or by providing an amount then list should be displayed where transaction value greater than the value entered.
Customer can also search the transactions using Credit (Deposit) or Debit (Transfer) options

Actors : Customer

Mockup screens

![image](https://github.com/user-attachments/assets/1a65cb2a-b148-40ba-abc0-7cfd02dd6ef0)

![image](https://github.com/user-attachments/assets/9cafbc7c-891d-44eb-aa5f-ea7b27d6dd98)
![image](https://github.com/user-attachments/assets/947c5895-a97c-45fa-8ca8-8dae10e7d77a)
![image](https://github.com/user-attachments/assets/4ee646ff-6816-4f9e-83e8-e1cc4a2f7d92)
![image](https://github.com/user-attachments/assets/14e1da08-43e9-402f-b6a5-614a0a9b791b)

![image](https://github.com/user-attachments/assets/6114b680-a4fd-4569-a70b-091c3981a3c8)
![image](https://github.com/user-attachments/assets/714ce78f-d26f-4c6f-89ac-c4975fdf37a0)


![image](https://github.com/user-attachments/assets/eaacee9c-8034-408f-8e30-2d55a3c74146)


Trigger
Whenever the customer willing to register or to do the payments

Preconditions	
1.Create specific users for the above role
2.Create the required work parties for correspondence.

Post conditions	
1.Change the status at each step in every case type.
2.Transaction Id must be generated automatically with the format “O- XXXXXXX”
3.A correspondence message must be generated automatically once the transaction is completed.
4.Before performing any transaction like Payment / Balance Enquiry, we need to verify the user with a valid PIN.

Normal Flow

![image](https://github.com/user-attachments/assets/40317330-538b-4e84-a93e-b841c406fcab)

This case type has multiple stages

1.Login
2.Create Account
3.Begin Transaction
4.Add Bank Details
5.Payment
6.Transaction History

Login: When the customer/User is already registered with our application they can directly Login using Username and Password.

Create Account: If the Customer/User is new to the application they can register to the application by giving personal details, add Id proof and address proof.

Start transaction: Customer/User must select the type of transaction what they want to perform.

Add Bank Details: User can able to add bank details by providing the information like Bank name, Account number etc...

Payment: User need to enter the mobile number to whom he /she wants to send amount. While sending the amount we need to authenticate with a valid PIN number provided at the time of registration. On successful completion of the transaction the details need to be added into the Local Data source.

Note: Before processing the payment the system must check the available balance from the data stored in local data source.


Transaction History: The user can able to view the transactions based on Current month, Previous month, All transactions and based on mobile number.

Alternate : Flows	NA

Exceptions	
1.The customer must have a provision to update or change the email id optionally if required.

Includes	
1.Create the data types as required.
1.Customer Details
2.Bank Details
3.Transaction Details

Frequency of Use : N/A

Special Requirements

1.The user must authenticate with the OTP sent to the mobile number.
2.The user must enter the PIN while performing the transaction. PIN size must be of 4 digits.
3.Date of payment must be a current system Date and Time.
4.Based on the IFSC code entered by the customer, the bank details like Bank name, Branch, State must be auto populated.
Note: Refer to the below table for sample data to store in local data source.

IFSC Code	Bank Name	Branch	State
HSBC0500002	HSBC	Hyderabad	Telangana
IOBA0000030	Indian Overseas Bank	Bhubaneshwar	Odisha
KKBK0000553	Kotak Mahindra Bank	Chennai	Tamilnadu
INDB0001418	IndusInd Bank	Bengaluru	Karnataka

5.User can update / change PIN number optionally upon authentication.
6.On successful payment transfer the balance must be updated in the local data source.
Maximum amount user can transfer per transaction is 20,000/-.

Future Requirements	
1.  Configuring the application for scanning the QR code for online shopping payments.

Assumptions	N/A

Reporting Requirements	Customer should able to see the reports like
1.Current Month
2.Last Month
3.All Transactions
4.Transactions based on mobile number
	Create a	report	which	can	tell	the	Transaction details.

 Acceptance Criteria	
 1.Configure all mandatory fields
2.Perform Unit testing for all the rules configured
3.Name fields must accept only characters.
4.Transfer amount should not exceed more than 20,000.

Data Types that can be used:
1.Create a data type called “Customer”, create a local source for it and add records.
FirstName, LastName, Full Name, Email address, Mobile Number, Username, Password, PIN
 
![image](https://github.com/user-attachments/assets/eadaab6a-a91f-4057-97d2-7be9dacd97d9)

2.Create a datatype called “Bank Details”, Create a local source for it and add records.
Bankname, Account number, Account holder name, Amount, Dateofbirth, IFSC code, Mobile number, PAN Number, Aadhar number

![image](https://github.com/user-attachments/assets/80e58a02-3729-48ae-bb7a-68c9f8cbcb33)

3.Create a datatype called “Transaction Details”, create a local source for it and add records.
PaidFrom, PaidTo, Status, TransactionID, Amount, Comments, Date of transaction

![image](https://github.com/user-attachments/assets/d6c1510b-b4fc-4656-9063-99bb51942776)


