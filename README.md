Open Financial Technologies (India) Internet Payment Gateway Module for Magento 2.4x
=====================================================================================

Install using SSH
```
cd /opt/bitnami/magento
composer require dravasp/openmoneypaymentgatewaymagento:dev-master
sudo magento-cli setup:upgrade
```

Login to Magento Admin > Configuration > Sales > Payment Methods

Instructions:
==================

[] Fill up Open Financial Technologies (India) integration form - Ref. to https://app.open.money/register?ref=https://open.money/products/payment-gateway Click Here for Merchant Onboarding Requisites - `https://open.money/tnc`
  - Login to your Open Financial Technologies (India) Account Dashboard and Go to My Account > Developer Settings > Security > API Keys > Enable TEST/LIVE Mode Accordingly
  - Connect with your Designated Account Manager at Open Financial Technologies (India)
  - Complete KYC and Request Approval for Compliance Check
  - Compliance Check requires valid About Us, Contact Us, Product Catalogue, Acceptable Terms and Conditions, Privacy Policy and Return, Refund & Cancellation Policy
  - Optionally, you may also set Security Policy with Customer Support Method clearly defined > Tollfree Phone / SMS / WhatsApp / Email
  - TLS 1.3 with HTTP2.Quic Enabled

[] Changes for going Live.
  - Insert your (variables) `ACCESS KEY` + `SECRET KEY` for Production Environment in Stores > Configrations > Sales > Payment Methods > Layer by Open Financial Technologies (India)

[] Enabling the module and configuring it with your Open Financial Technologies (India) Merchant credentials
  - Login to your Magento Admin and go to Store > Configuration.
  - On the left side bar, scroll down and click on "Payment Method" under the Sales section.
  - Scroll down the page and "Enable" the Open Financial Technologies (India) IPG Layer module.
  - On the same page, click on "Payment Methods" on the sidebar under the section "SALES".
  - On this page, a "Open Financial Technologies (India)" section will appear. Click on it if its not already open.
  - Add your `ACCESS KEY` + `SECRET KEY`  here. Also specify sandbox to "NO" Always. 
    click "Save Config".
    Additionally, if you want that only buyers from particular country or countries should be able to use Open Financial Technologies (India),  
    against the "Payment Applicable From" field, select "Specific Countries" and then select the countries in the box
    that opens up. In order to select more than one country, you will need to click on the countries with ctrl key of the 
    keyboard pressed. Sort Order field determines in which order Open Financial Technologies (India) will be displayed to the buyer during checkout.
   
[] Testing Open Financial Technologies (India) Internet Payment Gateway
  - Make sure that sandbox mode is on and all details are entered in the Open Financial Technologies (India) configuration
  - Go to your store and place an order. 
  - If you configured Open Financial Technologies (India) IPG Layer correctly in the previous step, it should appear as an option under payment methods during checkout.
  - When you click on checkout, it should redirect you to Open Financial Technologies (India) payment gateway and show credit card and netbanking form. 
  - Use Netbanking to complete a test payment. On Live Mode, your preferred Acceptance Modes will be Visible - CC, DC, Wallets, Netbanking
  - All banks netbanking are not activated by default - Usually takes 48-76 hours to activate all preferred partner banks.
  - VAS Team along with Designated Account Manager will email list of available banks for Netbanking

[] Checking the status of payment transaction at Open Financial Technologies (India) Dashboard from your Magento Admin
  - Login to admin and under Sales, click on Orders
  - Click on the first order in the data grid. This should be the order that you just placed
  - When the order details page opens up, look for "Payment Information" block. 
    Inside the block, you can see the latest status of the transaction on Open Financial Technologies (India) end. 

You will now be able to integrate Open Financial Technologies (India) with your existing Merchant Services Account of choice where you host your Merchant Account

Merchant Account or Cash Collection Service Account with Innovative ```Banking Partners``` allows high order value or high frequency volume (recurring trxns.)

Benefits of Merchant Services as opposed to standard Integration - 
```
Get an integrated, rules-based, proactive risk management system that is supported by industry standard security
Enjoy 99.9% uptime and a 24-hour helpdesk support
Get customised MIS solutions for your business needs
```

You can apply for a Merchant Account with Open Financial Technologies (India) + Kotak Mahindra Bank / SBM Bank (India) / Bank of Baroda / HDFC Bank / ICICI Bank / YES Bank (Any One) for unprecedented scale

```
Account Reconciliation / Revenue Insights + Affordable Pricing for Growth - Scale
````

[] Corporate Office Address  - India's Accelerated Payment Gateway
```
  - Open Financial Technologies Private Limited (India - IN) 
    - 91 Springboard Business Hub Pvt Ltd Plot No. D-5, Road No. 20, Marol MIDC Andheri East, (MUMBAI) MAHARASHTRA - 400093
	- Awfis Space Solutions Pvt Ltd Cabin No. 77, 4th Floor Shree Manjari Building, Near Vardaan Market (KOLKATA) - 700071
		- Direct Connect 18602586633 - Wait for Operator Assistance - Ask for Open Financial Technologies
	- Head Office - 3rd floor, Tower 2, RGA Techpark, Carmelaram, Sarjapur Road (BENGALURU KARNATAKA) - 560035
```	
	Opens : 10 AM to 6 PM Everyday - 10 AM to 6 PM IST Saturday  Closed : 2nd & 4th Saturday and every Sunday
  
  - Technical Documentation Usage - `https://docs.bankopen.com/docs/integration-sdk#magento-plugin`
  
  - Customer Care at `letstalk@bankopen.co` (Mon-Fri 10am to 6pm IST) / Raise a Ticket via `Web Chat` or Designated Account Manager
  
[] Important Emails for Corporate Communications and Risk Assessment
	- Corporate Communications https://in.linkedin.com/company/bankwithopen / `https://open.money/about-us`
	- Risk Alert - https://open.money/responsible-disclosure-policy / Vuln. Report `security@bankopen.co`
	
[] Install using `composer require dravasp/openmoneypaymentgatewaymagento:dev-master`
  - Please Do Not Run composer with sudo or install in project root directory / Please Do Not Upload Static Files to Webserver.
  - Request Integration Support or Seek Guidance from Repo Maintainers
   
```
  - BASE_URL_UAT - https://icp-api.bankopen.co/api
  - BASE_URL_SANDBOX - https://sandbox-icp-api.bankopen.co/api
  - SHA256
  - const ALLOWED_CURRENCIES = ['INR']
```
	Check Trxn. Details via Bitnami Magento 2.4x Admin Order Dashboard `Login` - `Sales > Orders > Select Latest Order` > Transaction ID with Details - `CAPTURE`

  - Support and Documentation - Forum - `https://discuss.open.money`

  - For Testing UAT run 
		md5 <filename>

  - Example
	```
	md5 /opt/bitnami/magento/var/log/system.log
	```
	inside SSH Terminal to provide verification to VAS Team
	
  - One-page Checkout Enabled for Magento Commerce OS - Bitnami
  
  Uninstall
```	
	sudo magento-cli module:disable Open_Layerpg
	composer remove dravasp/openmoneypaymentgatewaymagento
	sudo magento-cli setup:upgrade
	sudo magento-cli module:status
```	

  Hard Delete an Plugin / Extension
```
	sudo nano /bitnami/magento/app/etc/config.php
	Page Down to Open_Layerpg
	Delete and make sure there are no trailing spaces
	CTRL/CMD + X and Click Y to Save without Renaming the file
```
```	composer dump-autoload
	sudo magento-cli setup:upgrade
```
```	Wait for a few minutes RUN command
	sudo /opt/bitnami/ctlscript.sh restart
	Wait for a few minutes and Re-check
```	
New Registration for Merchants - https://app.open.money/register?ref=https://open.money/products/payment-gateway