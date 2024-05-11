# Sprint 8 project

Prerequisites for the entire project:

1) Node.js is installed on your computer: Make sure you have the latest version of Node.js installed. You can download and install it from the official Node.js website.
2) Required dependencies installed: You must have the required dependencies installed for your project, including fetch, as well as any other dependencies required for the test to run. You can install them by running npm install.
3) The helper.js, wdio.conf.js, page.js files exists: Make sure you have a helper.js, wdio.conf.js, page.js files that exports all  the funktions that you need for successful testing. These files must be in the same directory as your test file.
4) tests are run using the command: npx run wdio

Once these prerequisites are met, you can run the test by following these instructions:


Test name 'should open phone number modal'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This test tests the functionality of opening a modal window to enter a phone number. Await expect(pnoneNumberModal).toBeExisting();: This line checks whether a modal window exists on the page. If the modal window exists, the test will succeed.


Test name 'should save the phone'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This test checks the function of saving the entered phone number. Const phoneNumber = helper.getPhoneNumber("+1");: This calls the getPhoneNumber function from the helper.js module to generate a random phone number with the country code "+1" (USA).
await page.submitPhoneNumber(phoneNumber);: This line calls the submitPhoneNumber function from the page.js module, which submits the entered phone number.

await expect(await helper.getElementByText(phoneNumber)).toBeExisting();: This step checks that the phone number entered is displayed on the page.js. The getElementByText function from the helper.js module is used to search for an element on a page by text. If the phone number is found, the test is considered successful.


Test name 'should setting the address'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This test checks the functionality of setting addresses on a page. await page.fillAddresses('East 2nd Street, 601', '1300 1st St');: This step fills the addresses on the page.js. The fillAddresses function from the page.js module is used to enter the origin and delivery addresses. 
await expect(fromField).toHaveValue('East 2nd Street, 601');: This step verifies that the value of the input field for the originating address is indeed 'East 2nd Street, 601'.

await expect(toField).toHaveValue('1300 1st St');: This step checks that the value of the input field for the shipping address is indeed '1300 1st St'.


Test name 'should selecting supportive plan'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This test tests the action of selecting a supporting plan on a page. await expect(supportivePlanButton).toBeDisplayed();: This step checks that the button to select a supporting plan is actually displayed on the page, in which case the test is considered successful.


Test name 'should adding a credit card'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

To perform this test, a function addPaymentMethodCard was added to the page.js. This addPaymentMethodCard function performs the steps of adding a credit card to the page.
This test checks the action of adding a credit card on a page. Here's how it works:

await page.addPaymentMethodCard();: This step calls the addPaymentMethodCard function from the page.js module, which performs the actions of adding a credit card to the page.

const cardPaymentMethodIcon = await $(page.cardPaymentMethodIcon);: This line finds the credit card icon on the page.

await cardPaymentMethodIcon.waitForDisplayed();: This step waits until the credit card icon is displayed on the page.

await expect(cardPaymentMethodIcon).toBeExisting();: This step checks that the credit card icon actually exists on the page.


Test name 'should write a message for the driver'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This code describes a test that checks whether a driver can write a message on a page.

const messageForTheDriver = await $(page.messageForTheDriver);: Finds a message field for the driver on the page.

await messageForTheDriver.waitForDisplayed();: Waits for the message field to be displayed for the driver.

await messageForTheDriver.setValue('Get some beer');: Enters the message text ("Get some beer") in the message field for the driver.

await browser.pause(3000);: Pauses the test for 3 seconds to allow the user to see what is happening on the page.

await expect(messageForTheDriver).toHaveValue('Get some beer');: Checks that the text "Get some beer" is actually entered in the message field for the driver.


Test name 'should ordering a Blanket and handkerchiefs'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This test checks the functionality of ordering blankets and handkerchiefs on the page.

const blanketAndHandkerchiefsButton = await $(page.blanketAndHandkerchiefsButton);: Finds the button to order blankets and handkerchiefs on the page.

await blanketAndHandkerchiefsButton.waitForDisplayed();: Waits for the blanket and handkerchief order button to be displayed.

await blanketAndHandkerchiefsButton.click();: Clicks the button to order a blanket and handkerchiefs.

await browser.pause(3000);: Pauses the test for 3 seconds to allow the page to refresh and reflect the changes.

await expect ($(page.blanketSwitch)).toBeChecked();: Checks that the blanket switch is checked after clicking the blanket and handkerchiefs order button.


Test name 'should ordering 2 Ice creams'.

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This test tests the functionality of ordering two ice creams on a page.

const iceCreamPlusButton = await $(page.iceCreamPlusButton);: Finds the button to add ice cream to the cart.

await iceCreamPlusButton.waitForDisplayed();: Waits for the ice cream add button to be displayed.

await iceCreamPlusButton.click();: Clicks the add ice cream button once to add one ice cream to the cart.

await iceCreamPlusButton.click();: Clicks the add ice cream button again to add another ice cream to the cart.

const iceCreamValue = await $(page.iceCreamValue);: Finds an element that displays the amount of ice cream in the cart.

const value = await iceCreamValue.getText('2');: Gets the text value from the element, which must match the number "2".

await expect(value).toBe('2');: Checks that the element's text value matches "2", which confirms that two ice creams have been added to the cart.


Test name 'should open car search modal'

1) Open a terminal in VS code.
2) Run the test: Type the following command 'npx run wdio' in a terminal and press Enter.
3) Wait for the test to complete: The test will run and you will see the execution results in your terminal or command line. If the test is successful, you will see a test completion message. If the test fails, you will see an error message to help you understand what went wrong.

This test tests the opening of a car search modal window on a page.

const orderCarButton = await $(page.orderCarButton);: Finds a button to order a car on a page.

await orderCarButton.waitForDisplayed();: Waits for the car order button to be displayed.

await orderCarButton.click();: Clicks the car order button.

await browser.pause(3000);: Pauses the test for 3 seconds, giving enough time for the modal window to open.

const carSearchModal = await $(page.carSearchModal);: Finds the car search modal on the page.

await expect(carSearchModal).toBeExisting();: Checks that a car search modal exists on the page.



In general, these tests check various stages of the order creation process, from filling out addresses and selecting additional options to setting up a contact number and payment. Each test checks a specific functionality or step to make sure everything works correctly.
