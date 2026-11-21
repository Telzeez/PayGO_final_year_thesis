**PAYGO Prototype: Test Procedures**

This document lists every test planned for the PAYGO prototype\. For each test it states what to do, what you should expect, and what to record\. It is organised by the four project objectives, supports Section 3\.13 \(methodology\) and supplies the data for Chapter Four\. Change the numbers, equipment and wording to match what you actually have\.

# 1\. Before you start

**Safety**

- Mains voltage is dangerous\. Work only with the supply isolated while wiring, and have an experienced person supervise the first power-up\.

- House the circuit in an insulated enclosure, use a fused supply or a circuit breaker with earth leakage protection, and never touch exposed terminals\.

- Use resistive test loads of known rating and stay well below the rated current of the relay and the PZEM-004T\.

- Do not leave the circuit powered and unattended\.

**Set-up record \(fill in once\)**

| **Item** | **Details** |
| --- | --- |
| Date and place |  |
| Firmware version |  |
| Backend address and version |  |
| Tariff p \(₦ per kWh\) |  |
| Reference instrument \(make, model, accuracy\) |  |
| Test loads and ratings |  |
| Wi-Fi network used |  |
| AC source | Grid supply |



**General rules**

- Repeat each measurement at least three times and record every value, including bad ones\.

- Take screenshots, serial output or log extracts as evidence \(for Chapter Four\)\.

- Set the acceptance limits \(for example the percentage error\) before you test, not afterwards\.

- Report failures honestly\. A failed test with an explanation is acceptable; a hidden failure is not\.

- Tests T5 and T6 depend on how your firmware receives credit over HTTPS\. Do them in the way your system really works\.

# 2\. Project objectives and the tests that cover them

The tests are organised around the implemented project objectives:

1\. Implement an ESP32-based prepaid metering unit using the PZEM-004T to measure single-phase electrical parameters, calculate consumption and maintain a local balance with relay-based load control.

2\. Implement HTTPS communication between the embedded meter and backend for heartbeat reporting and prepaid balance synchronisation.

3\. Develop a web platform for payment processing, user and device management, transaction history, consumption reporting and CSV export, together with a location-aware marketplace.

4\. Evaluate the prototype through available functional hardware and software tests, while identifying tests that could not be completed.

| **No\.** | **Test** | **Level** | **Objective covered** |
| --- | --- | --- | --- |
| T1 | Measurement comparison against a calibrated reference | Component | Objective 1 |
| T2 | Local energy accounting and prepaid balance deduction | Component | Objective 1 |
| T3 | Physical relay cut-off and reconnection | Component | Objective 1 |
| T4 | HTTPS heartbeat and balance synchronisation | Integration | Objective 2 |
| T5 | Verified payment and HTTPS balance synchronisation | Integration | Objective 3 |
| T6 | Recovery after network interruption | Operational | Objective 2 |
| T7 | Payment initiation and webhook verification | Integration | Objective 3 |
| T8 | Energy-credit calculation | Component | Objective 3 |
| T9 | Duplicate payment prevention | Integration | Objective 3 |
| T10 | Marketplace location matching and service radius | Integration | Objective 3 |
| T11 | Web platform functions and reporting/export | Integration | Objective 3 |
| T12 | Integrated functional evaluation | Operational | Objective 4 |
| T13 | Automated backend tests | Software | Objective 4 |

The procedures below describe methods that can be used to evaluate the prototype. A procedure in this document is not, by itself, evidence that the test was completed. Chapter Four reports only results supported by actual observations or available software evidence.

# 3\. Test procedures

## Objective 1: Embedded prepaid metering unit

*Design and implement an embedded prepaid smart metering unit using the PZEM-004T sensor module, ESP32 microcontroller, and automated relay control to measure single-phase electrical parameters, deduct consumed energy credit in real time, and automatically disconnect or reconnect the load based on available balance\.*

### T1: Energy measurement accuracy \(PZEM-004T against a reference\)

**Objective of the test**

To find out how closely the PZEM-004T readings of voltage, current, active power and energy agree with a reference measuring instrument\.

**What you need**

- PAYGO meter powered from the grid supply, with the relay on

- Reference instrument connected in the same circuit \(a calibrated power or energy meter, or a clamp meter plus voltmeter\)

- At least four resistive loads of different known ratings \(for example a lamp, a fan heater element, a kettle\)

- Stopwatch or the device timestamps; a notebook or spreadsheet

**Procedure**

1. Record the make, model and accuracy class of the reference instrument\.

2. Connect the reference instrument and the PAYGO meter in series with the load so that both measure the same current\. Check the wiring before switching on\.

3. Switch on the first load and wait for the readings to settle \(about 30 seconds\)\.

4. Read voltage, current and active power on the PZEM-004T \(from the serial output or the backend\) and on the reference at the same moment\. Take five readings, about 10 seconds apart\.

5. For the energy test, note the starting energy on both instruments, run the load for a fixed time \(for example 30 minutes\), then record the finishing energy on both\.

6. Repeat steps 3 to 5 for each load\.

7. Calculate the percentage error with Equation \(3\.4\) and the mean with Equation \(3\.5\) for each quantity and each load\.

**Record the following \(results go in Chapter Four\)**

| **Load** | **Quantity** | **PZEM reading** | **Reference reading** | **Error \(%\)** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |



**Expected result**

- PZEM readings are close to the reference at every load level\.

- Errors are small and consistent; they may be larger at very low power\.

**Pass criterion**

State the acceptance limit before testing \(for example ±2% for energy and power\)\. If a result is outside the limit, report it and discuss the reason; do not adjust the data\.

### T2: Prepaid credit deduction

**Objective of the test**

To check that the balance on the meter falls by the amount of energy actually consumed\.

**What you need**

- PAYGO meter with the grid as the AC source

- A load of known power \(for example 100 W lamp or heater\)

- Reference energy meter \(optional but recommended\)

- Access to the backend or web application to view the balance

**Procedure**

1. Set a known starting balance \(for example 0\.100 kWh\) using the normal recharge route or a test-mode credit\.

2. Record the starting balance on the meter display and in the web application\.

3. Switch on the load and let it run for a measured time, or until about half of the credit is used\.

4. Record the new balance on the display and in the web application, and the energy measured by the PZEM-004T and the reference meter over the same period\.

5. Compare the fall in balance with the measured energy using Equation \(3\.1\)\.

6. Repeat with a second load of different power\.

**Record the following \(results go in Chapter Four\)**

| **Run** | **Start balance \(kWh\)** | **End balance \(kWh\)** | **Fall in balance \(kWh\)** | **Measured energy \(kWh\)** | **Difference \(%\)** |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |



**Expected result**

- The fall in balance equals the measured energy within the measurement error\.

- The balance never becomes negative\.

**Pass criterion**

Fall in balance and measured energy differ by no more than the acceptance limit you set\.

### T3: Load control \(relay operation\)

**Objective of the test**

To check that the relay supplies the load while credit is available, disconnects it when credit is exhausted, and reconnects it after a recharge\.

**What you need**

- PAYGO meter with relay and a visible load \(a lamp\)

- Stopwatch

- A small starting balance so the credit runs out quickly \(for example 0\.010 kWh\)

**Procedure**

1. Set a small balance and switch on the lamp\. Confirm the relay is on\.

2. Leave the load running until the balance reaches zero\.

3. Note whether the relay switches off and how long after the balance reaches zero\. Confirm the lamp is off and the balance does not go below zero\.

4. Try to run the load again with zero balance and record what happens\.

5. Add credit \(a test-mode recharge or the normal recharge route\) and record whether and how soon the relay switches on\.

6. Repeat the cycle three times\.

**Record the following \(results go in Chapter Four\)**

| **Cycle** | **Balance at cut-off \(kWh\)** | **Relay off? \(Y/N\)** | **Delay to cut-off \(s\)** | **Relay on after recharge? \(Y/N\)** | **Delay to reconnect \(s\)** |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |



**Expected result**

- Relay is on while balance is above zero\.

- Relay switches off when the balance is exhausted and stays off\.

- Relay switches on again after credit is added\.

**Pass criterion**

All three cycles behave as above, with no unintended switching\.

## Objective 2: HTTPS communication with the backend

*Implement HTTPS communication between the embedded meter and backend for heartbeat reporting and prepaid balance synchronisation.*

### T4: Heartbeat and balance synchronisation over HTTPS

**Objective of the test**

To check that the meter sends heartbeat requests and synchronises its local prepaid balance with the authoritative balance returned by the backend.

**What you need**

- PAYGO meter connected to Wi-Fi
- Deployed backend and web application
- Backend logs or database access

**Procedure**

1. Power the meter and allow it to connect to Wi-Fi.
2. Check the backend logs or device record for a recent heartbeat and last-seen timestamp.
3. Record the balance shown on the meter and compare it with the server-side device balance.
4. Allow the device to perform its normal balance synchronisation and record the resulting values.
5. Repeat after a controlled balance update.
6. Do not expect raw voltage, current, active-power or frequency samples to appear in the backend as continuous telemetry; those measurements are acquired locally by the meter.

**Record the following**

| Check | Meter balance (kWh) | Backend balance (kWh) | Match? |
|---|---:|---:|---|
| Initial synchronisation | | | |
| After balance update | | | |

**Expected result**

- The backend receives valid heartbeat requests.
- The meter and backend balance values agree after synchronisation.

**Pass criterion**

The heartbeat is received and the meter synchronises to the authoritative server-side balance. Record only observed outcomes.

### T5: Verified payment and HTTPS balance synchronisation

**Objective of the test**

To check that a verified payment updates the server-side device balance and that the meter obtains the updated balance through its HTTPS heartbeat and synchronisation process.

**What you need**

- PAYGO meter online
- Web application and backend
- Paystack test mode or an authorised test payment process
- Access to the meter display and backend transaction/device records

**Procedure**

1. Record the starting balance displayed by the meter and stored by the backend.
2. Initiate a payment through the web application.
3. Confirm that the backend receives and verifies the Paystack webhook.
4. Check that the payment transaction is recorded and the server-side device balance is updated.
5. Allow the meter to send its next HTTPS heartbeat.
6. Record the balance returned by the backend and the balance displayed by the meter after synchronisation.
7. Compare the server-side and local balances.

**Record the following**

| Run | Payment reference | Server balance after payment (kWh) | Meter balance after sync (kWh) | Match? |
|---|---|---:|---:|---|
| | | | | |
| | | | | |
| | | | | |

**Expected result**

- A verified payment updates the server-side balance.
- The meter synchronises its local balance through HTTPS.
- The local and server-side balances agree after synchronisation.

**Important limitation**

The firmware does not subscribe to the backend MQTT credit topic and does not send a transaction-specific physical credit acknowledgement. Do not describe the backend transaction status as proof of such an acknowledgement. If no actual payment test was performed, report the integration as implemented and leave the test result unclaimed.

### T6: Recovery after network interruption

**Objective of the test**

To check that the meter continues local operation during a temporary network interruption and synchronises its balance with the backend after connectivity is restored.

**What you need**

- PAYGO meter and Wi-Fi router that can be switched off
- Access to the meter display and backend device record

**Procedure**

1. Record the meter's local balance and the corresponding backend balance.
2. Disconnect the Wi-Fi network while leaving the meter powered.
3. Observe whether the meter continues local measurement and load-control operation.
4. Restore the Wi-Fi connection.
5. Allow the meter to send its next HTTPS heartbeat and synchronise its balance.
6. Compare the local meter balance with the backend balance after synchronisation.

**Record the following**

| Run | Local operation maintained? | Backend status after reconnect | Meter balance (kWh) | Backend balance (kWh) | Match? |
|---|---|---|---:|---:|---|
| | | | | | |
| | | | | | |

**Expected result**

- The meter continues local operation while the network is unavailable, subject to its locally stored balance.
- After reconnection, the meter and backend reconcile their balance information.

**Important limitation**

This test concerns HTTPS heartbeat and balance synchronisation. It is not a test of pending MQTT credit-command delivery or a physical transaction-specific acknowledgement.

## Objective 3: Web platform and marketplace

*Develop a web-based energy management and location-aware marketplace platform that supports digital credit recharge, user and transaction management, energy data visualisation, and identification of nearby listed energy sources using geographical coordinates and the Haversine formula\.*

### T7: Payment initiation and webhook verification

**Objective of the test**

To check that a valid Paystack payment event creates a correct transaction and that an event with an invalid signature is rejected\.

**What you need**

- Paystack account in test mode, with its test card or bank details

- Web application and backend

- A tool for sending HTTP requests \(for example curl or Postman\)

- Backend logs and database access

**Procedure**

1. Log in to the web application and select the device and an amount\.

2. Start the payment and complete it with the Paystack test details\.

3. Check that the backend received the webhook, validated the HMAC-SHA512 signature and created a transaction record with the Paystack reference\. Record the transaction identifier \(TXN\_\.\.\.\)\.

4. Check the amount in naira and the energy in kWh stored in the transaction\.

5. Send a copy of a webhook request with the signature altered \(or removed\)\. Record the HTTP response and check that no transaction is created\.

6. Repeat with a failed or abandoned test payment and check that no credit is created\.

**Record the following \(results go in Chapter Four\)**

| **Case** | **Amount \(₦\)** | **Signature valid?** | **Transaction created?** | **HTTP status** | **Outcome** |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |



**Expected result**

- A valid event creates exactly one transaction with the correct amount and energy\.

- An invalid-signature request is rejected and creates no record\.

- A failed payment creates no credit\.

**Pass criterion**

All three cases behave as expected\.

### T8: Energy-credit calculation

**Objective of the test**

To check that each payment is converted into the correct energy, using Equation \(3\.2\)\.

**What you need**

- Backend with a known tariff p \(naira per kWh\)

- Paystack test mode

- Calculator or spreadsheet

**Procedure**

1. Record the tariff p used by the backend\.

2. Make test payments of several different amounts \(for example ₦100, ₦500, ₦1,000 and ₦5,000\)\.

3. For each payment, read the energy stored in the transaction record\.

4. Calculate the expected energy as A divided by p and compare\.

**Record the following \(results go in Chapter Four\)**

| **Amount A \(₦\)** | **Tariff p \(₦/kWh\)** | **Expected kWh \(A/p\)** | **Stored kWh** | **Difference** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |



**Expected result**

- The stored energy equals A/p for every amount, allowing for rounding\.

- Naira and kWh are stored in separate fields\.

**Pass criterion**

Stored energy equals the expected value for all amounts\.

### T9: Duplicate prevention

**Objective of the test**

To check that a repeated payment event cannot credit the meter twice\.

**What you need**

- Backend and database access

- A tool for sending HTTP requests

- A copy of one valid webhook payload and its signature from T7

**Procedure**

1. Record the device balance and the number of transactions\.

2. Send the same valid webhook \(same Paystack reference\) to the backend a second time, and then a third time\.

3. Record the response each time\.

4. Check the number of transactions and the balance in the database\.

5. If the firmware supports it, repeat a credit instruction with the same TXN identifier and check that the meter does not apply it again\.

**Record the following \(results go in Chapter Four\)**

| **Attempt** | **Response** | **Transactions after** | **Balance after \(kWh\)** | **Credited again? \(Y/N\)** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |



**Expected result**

- Only one transaction exists for the reference\.

- The balance rises once only\.

**Pass criterion**

No duplicate credit in any attempt\.

### T10: Marketplace: location matching and service radius

**Objective of the test**

To check that listings are matched using the Haversine distance and the service radius, and that purchases do not oversell a listing\.

**What you need**

- Web application with two owner accounts and two buyer accounts

- Known coordinates for the listing and for test buyer locations

- Map tool or an independent distance calculation \(for example a spreadsheet using Equation 2\.5\)

**Procedure**

1. Register an energy source and publish a listing with available energy, a price and a service radius \(for example 5 km\)\.

2. As a buyer, enter locations inside the radius \(about 2 km away\), near the limit \(about 5 km\), and outside it \(about 10 km\)\. Record the distance shown and whether the listing is returned\.

3. Calculate each distance independently and compare it with the value from the backend\.

4. Pause the listing and check that it is no longer offered\.

5. Test inventory protection: with a listing of, say, 1\.0 kWh, have a buyer request 0\.6 kWh and then a second buyer request 0\.6 kWh\. Record the result of each request and the remaining available energy\.

6. Check that the reserved energy \(reserved\_kwh\) is reduced when a purchase is completed or cancelled\.

**Record the following \(results go in Chapter Four\)**

| **Buyer location** | **Distance \(backend, km\)** | **Distance \(independent, km\)** | **Radius \(km\)** | **Listing returned?** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |



**Expected result**

- Listings are returned only when d ≤ r\.

- Backend distances agree with the independent calculation\.

- Paused listings are not offered\.

- The second 0\.6 kWh request is refused or limited, so the 1\.0 kWh listing is never oversold\.

**Pass criterion**

Eligibility matches d ≤ r in every case and no listing is oversold\.

**Note**

Distance within the service radius does not prove that energy is physically available\. The test checks the software rule only\.

### T11: Web platform functions and response time

**Objective of the test**

To check the user, transaction and energy-data functions of the web application, and how quickly its pages respond\.

**What you need**

- Web application on a laptop and on a phone

- Two test user accounts

- Browser developer tools \(network tab\) or a stopwatch

**Procedure**

1. Register a new user, log out and log in again\. Try a wrong password and record the result\.

2. Open a protected page without logging in and record whether access is refused\.

3. View the device page: check the balance, device status and energy data \(power and accumulated energy\) and compare them with the meter and the backend\.

4. Start a recharge from the web application and check that the payment appears in the transaction history with the correct amount and energy\.

5. Open the marketplace page and check that listings and purchase options load\.

6. Repeat the main pages on the phone and on the laptop\.

7. Measure the load time of the dashboard five times and record the average\.

**Record the following \(results go in Chapter Four\)**

| **Function** | **Expected** | **Observed** | **Response time \(s\)** | **Pass \(Y/N\)** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |



**Expected result**

- Registration, login and logout work; wrong passwords and unauthenticated access are refused\.

- Balance, status, energy data and transaction history are correct and match the backend\.

- Pages work on mobile and desktop and load within the limit you set \(for example 3 seconds\)\.

**Pass criterion**

All functions work as expected and response times are within the limit\.

## Objective 4: Evaluation of the integrated system

*Evaluate the integrated system through component-level, integration, and operational testing to validate its metering accuracy, prepaid billing, load switching, communication reliability, and web platform performance\.*

### T12: Integrated end-to-end test

**Objective of the test**

To check that the whole chain works together: payment, backend record, credit at the meter, load operation and display on the web application\.

**What you need**

- Complete system \(meter, load, Wi-Fi, backend, web application\)

- Paystack test mode

- Reference energy meter \(optional\)

**Procedure**

1. Start with zero balance and confirm the load is off\.

2. Make a test payment of a known amount\.

3. Record the transaction, the credit arriving at the meter, and the time taken\.

4. Confirm that the load switches on and run it for a set time\.

5. Compare the balance on the display, in the backend and on the web page with the energy used\.

6. Let the credit run out and confirm that the load switches off\.

7. Check the transaction history in the web application for the payment\.

**Record the following \(results go in Chapter Four\)**

| **Stage** | **Expected** | **Observed** | **Time \(s\)** | **Pass \(Y/N\)** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |



**Expected result**

- Each stage follows the one before it\.

- Payment record, database balance, meter balance and device status are consistent\.

**Pass criterion**

All stages pass in the same run, repeated at least three times\.

### T13: Automated backend tests

**Objective of the test**

To record the results of the automated tests already written for the backend\.

**What you need**

- Backend source code

- Node\.js environment and test database

**Procedure**

1. Run the automated test files \(for example for the endpoints and the marketplace\) with the project’s test command\.

2. Save the console output\.

3. Record the number of tests run, passed and failed, and the reasons for any failures\.

**Record the following \(results go in Chapter Four\)**

| **Test file** | **Tests run** | **Passed** | **Failed** | **Notes** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |



**Expected result**

- Tests pass, or failures are explained and understood\.

**Pass criterion**

Report the actual counts; do not remove failing tests to improve the result\.

# 4\. After testing

- Copy all readings into tables for Chapter Four and calculate the percentage errors and means\.

- Match each result to its test name in Table 3\.3 so the plan and the results line up\.

- Keep the screenshots, logs and photos; refer to them in Chapter Four\.

- Write down any test you could not carry out and the reason, and mention it in Chapter Four\.