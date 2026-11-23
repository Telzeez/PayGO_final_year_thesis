## **1CHAPTER ONE** 

# **INTRODUCTION** 

# **1.1 Background to the Study** 

Electricity is an essential requirement for household activities, education, healthcare, communication and economic production. In Nigeria, limitations in the reliability and availability of centralised electricity supply have encouraged households, businesses and institutions to adopt alternative energy sources. Solar photovoltaic (PV) systems are increasingly used because they can generate electricity close to where it is consumed and can operate independently of the national grid when designed as standalone systems. 

Small-scale solar installations are commonly found in homes, business premises and residential compounds. In some settings, a system owner may have more energy available than is immediately required, while occupants or nearby users may need an alternative source of electricity. Sharing locally generated solar energy can therefore provide an opportunity to make better use of existing installations. However, for such an arrangement to operate effectively, the energy supplied to each consumer must be measured and accounted for in a transparent manner. 

A further concern is the upkeep of solar installations. Solar panels, batteries, inverters and associated components require periodic inspection, servicing and eventual replacement. Their performance may also decline with age and operating conditions. These activities involve costs, and an installation that does not generate income beyond serving its owner may be difficult to maintain over time. Allowing a system owner to supply surplus energy to other users on a prepaid basis can create a source of income that may contribute towards maintenance and the continued operation of the installation. 

1 

The decline in photovoltaic output is supported by field evidence. (Jordan and Kurtz, 2013) reviewed nearly 2,000 degradation measurements from photovoltaic modules and systems and reported a median power-output degradation rate of approximately 0.5% per year. A more recent meta-analysis by (Straub-Mück et al., 2025) based on 610 observations from 80 studies, reported a median annual degradation rate of 0.94%. The authors also found that reported degradation rates are significantly influenced by cell technology, mounting location and the measurement approach used in each study. These findings show that the rated output of a solar installation should not be assumed to remain constant throughout its service life. In this study, degradation refers specifically to the gradual, irreversible reduction in a photovoltaic (PV) module's maximum power output over time under comparable operating conditions. This phenomenon is distinct from temporary output reductions caused by fluctuating irradiance, shading, or surface soiling, which require different corrective measures. 

To illustrate the cumulative effect of degradation, a module experiencing a constant degradation rate of 0.5% per year would undergo an estimated linear power-output reduction of approximately 5% over ten years; at a rate of 0.94% per year, the corresponding simple estimate is about 9.4%. These figures serve as theoretical illustrations derived from published literature rather than empirical measurements from the PAYGO prototype or universal predictions for all Nigerian installations. Actual long-term performance depends on module technology, local climate, installation quality, and operating conditions. Nevertheless, this evidence provides a clear technical justification for system owners to plan for periodic inspection, preventive maintenance, and eventual component replacement. 

2 

The Pay-As-You-Go (PAYGO) approach provides a framework for supplying a service in exchange for payment made in advance or in controlled increments. When applied to electricity, prepaid metering associates energy consumption with an available credit balance. As the consumer uses electricity, the system measures the energy consumed and deducts the corresponding amount from the available balance. When the credit is exhausted, the supply can be disconnected through an automated load-control mechanism until additional credit is provided. 

Embedded systems and the Internet of Things (IoT) make it possible to combine electrical measurement, local control and remote monitoring in a single platform. A microcontroller can receive measurements from an energy-metering module, process the readings, manage the consumer credit balance and operate a relay connected to the load. Wireless communication allows the device to exchange information with a backend platform, where users, payments, energy records and device information can be managed. 

This project presents the design and construction of PAYGO, a smart prepaid energy metering and billing platform intended for small-scale solar energy sharing within residential compounds. The hardware prototype uses an ESP32 microcontroller and a PZEM-004T energy measurement module to obtain relevant single-phase AC electrical parameters. The embedded system works with a prepaid credit mechanism and relay-based load control, while the software platform supports user management, device monitoring, payment records and energy information. 

The platform also incorporates a location-aware energy marketplace concept. Energy owners can provide information about their energy sources and service coverage, while potential consumers can submit their location to identify nearby listed sources. Geographical distance 

3 

is calculated using the Haversine method to support this matching process. By bringing metering, prepaid credit management, digital payment and local energy discovery together, PAYGO explores how small solar installations can supply nearby consumers while creating a potential income stream for system upkeep. 

# **1.2 Problem Statement** 

The increasing use of small-scale solar installations provides an opportunity to improve access to electricity, particularly in locations where centralised supply is unreliable. However, the value of these installations can be limited when available energy is not efficiently shared, when consumption cannot be measured transparently, and when system owners have no structured means of earning from energy supplied to other users. 

One problem is the absence of a simple and reliable arrangement for measuring the amount of electricity delivered to individual consumers in a shared solar installation. Without appropriate metering, it becomes difficult for the energy owner and consumer to establish how much electricity has been used and what amount should be paid for. 

Another problem is the lack of an integrated prepaid mechanism that connects measured energy consumption to a consumer's available credit. Where energy usage and payment records are handled separately, it may be difficult to maintain an accurate account of the energy supplied. A system is therefore required to link energy measurement, credit deduction and load control. 

A further problem concerns the long-term upkeep of small solar installations. The performance of photovoltaic modules can decline over time: a review of nearly 2,000 field degradation measurements reported a median annual power-output degradation rate of 0.5%, while a 2025 meta-analysis of 610 observations reported a median of 0.94% per year (Jordan 

4 

and Kurtz, 2013; Straub-Mück, Geyer-Klingeberg and Rathgeber, 2025). The rate varies with cell technology, mounting location and measurement approach, but the evidence demonstrates that solar-system output may reduce as equipment ages. Batteries and other system components also require inspection and eventual replacement during the operating life of an installation. These activities involve costs, yet a system owner may have no regular income from the installation beyond its direct use. Where surplus energy can be supplied to other users and charged for according to measured consumption, the resulting income can provide a means of contributing towards maintenance and continued operation. 

There is also a need for remote monitoring and management of the metering device. System owners require access to relevant information such as energy consumption, available credit, payment records and device status. In addition, potential consumers need a convenient way to discover nearby energy sources that may serve their location. These requirements call for an integrated system that combines embedded metering, prepaid billing, communication, digital payment and location-aware energy discovery. 

The problem addressed by this project is therefore the lack of an integrated and affordable prototype for measuring electricity supplied from small-scale solar installations, managing prepaid energy credit, controlling the connected load and supporting the identification of nearby energy sources. PAYGO is developed to address these needs and to explore a prepaid energy-sharing arrangement through which income from supplied electricity can contribute to the upkeep of solar installations. 

5 

# **1.3 Aim and Objectives**

# **Aim**

The aim of this project is to design and implement a smart prepaid energy metering and billing platform for small-scale distributed energy applications, integrating electrical energy measurement, local prepaid balance management, automated load control, secure device-to-server communication, digital payment processing and a location-aware energy marketplace.

The specific objectives are to:

1. Design and implement an embedded prepaid metering unit using the PZEM-004T module and ESP32 microcontroller to measure single-phase AC electrical parameters, calculate energy consumption and maintain a local prepaid balance.
2. Implement relay-based load control and HTTPS communication between the embedded meter and backend for device heartbeat and prepaid balance synchronisation.
3. Develop a web-based platform for user and device management, digital payment processing, transaction records, consumption reporting and CSV export.
4. Implement a location-aware energy marketplace that identifies available listings according to geographical distance and the service radius of each energy listing.
5. Evaluate the integrated prototype through functional hardware, firmware, backend and web-application tests.

# **1.4 Significance of the Study**

This study demonstrates how embedded metering, prepaid balance management and web-based software can be combined to support energy management in small-scale distributed energy applications. The prototype provides a practical engineering example of measuring electricity consumption, maintaining a prepaid balance and controlling a connected load.

For owners of small solar installations, a platform of this type could support more transparent accounting when energy is supplied to another user within a residential compound. Consumption-based records may also help owners estimate energy use and plan for system operation and maintenance. These are potential applications of the design; the prototype has not been deployed as a commercial energy service and does not establish financial returns.

For consumers, the system provides a prepaid model in which the available energy balance is displayed locally and can be viewed through the web application. Consumption records and transaction history are intended to improve transparency between energy supply and use.

From an engineering perspective, the project integrates an ESP32 microcontroller, a PZEM-004T measurement module, relay-based load control, HTTPS communication, a PostgreSQL database, a payment gateway and a web application. It also provides a software implementation of location-based energy listing discovery. The prototype can serve as a basis for further work on distributed energy management and smart metering.

# **1.5 Scope of the Work** 

This project covers the design, construction and evaluation of  PAYGO solar energy metering and billing platform intended for small-scale residential compound energy sharing. The work focuses on the following areas: 

- (a) Single-phase AC electrical energy measurement using the PZEM-004T module. 

- (b) ESP32-based embedded processing and control. 

- (c) Measurement and processing of voltage, current, power, accumulated energy and other parameters supported by the selected metering module. 

- (d) Prepaid energy-credit management and balance updates. 

- (e) Local display of device information. 

- (f) Automated relay-based control of the connected load. 

- (g) Wireless communication between the embedded device and backend platform. 

- (h) Digital recording and management of energy and payment transactions. 

- (i) A web-based platform for user and device management. 

- (j) Location-based identification of nearby energy sources using geographical coordinates and Haversine distance calculation. 

8 

- (k) Functional testing of the hardware, firmware and software components, including their integration. 

The work is limited is limited to the design, construction, and testing of a single-phase smart prepaid metering prototype powered by a standard alternating current (AC) supply for laboratory and bench-top evaluation. While the prototype interfaces with a single-phase AC source to validate energy measurement, credit deduction, and load-control functionalities, it is not designed for direct high-voltage integration into the Nigerian national grid or utilityscale power distribution networks. 

This work does not encompass three-phase electricity metering, nor does it seek to replace certified utility prepaid metering infrastructure or regulatory standards. Although the proposed platform incorporates a software-based energy marketplace module, this study does not constitute a full commercial deployment of a regulated electricity trading system. Rather, the marketplace serves as a supporting software interface, while the primary engineering focus remains the hardware-software integration and operational reliability of the metering, prepaid credit management, and automated load-control mechanisms. 

# **1.6 Organisation of Report** 

This report is structured into five chapters, followed by the references and appendices. Chapter One introduces the study by presenting the background, problem statement, aim and specific objectives, significance and justification, scope and limitations, and the overall organisation of the report. 

Chapter Two reviews existing literature relevant to decentralized solar energy systems, PayAs-You-Go (PAYGO) business models, smart prepaid metering technologies, embedded 

9 

control systems, Internet of Things (IoT) communication protocols, digital payment gateways, and localized energy markets. 

Chapter Three details the system design and methodology, covering the overall system architecture, hardware component selection and circuit design, embedded firmware development, backend server architecture, web application interface, and experimental testing procedures. 

Chapter Four presents and discusses the performance results obtained from the hardware implementation, system integration, and evaluation tests in relation to the stated project objectives. 

Chapter Five summarizes the key findings, draws conclusions based on the system evaluation, and offers recommendations for future research and development. 

10 

## **2CHAPTER TWO** 

# **LITERATURE REVIEW** 

# **2.1 Introduction** 

This chapter reviews the literature and technologies on which the PAYGO solar energy metering and billing platform is based. Rather than treating the technologies as a list of separate topics, the review follows the argument that motivates the project. Nigeria needs more reliable and accessible electricity, and decentralised solar systems can help to meet this need. Solar modules and batteries, however, deteriorate with age and require maintenance, which creates recurring costs for the people who own them. Where an owner has surplus energy, supplying nearby consumers on a prepaid basis could provide an additional source of income towards that upkeep. Prepaid metering, embedded systems, the Internet of Things (IoT), digital payment and location-based search make such an arrangement technically possible. 

Sections 2.2 and 2.3 describe the energy context and the solar systems concerned. Sections 2.4 and 2.5 review the evidence on module degradation, battery ageing and maintenance. Sections 2.6 to 2.9 review PAYGO models, prepaid metering and smart metering. Sections 2.10 to 2.17 cover the measurement, embedded, communication, security and payment technologies used in the prototype. Sections 2.18 to 2.22 deal with energy sharing, locationbased discovery and web-based monitoring, and Section 2.23 outlines the Nigerian regulatory environment. Sections 2.24 to 2.27 compare related systems, state the research gap, present the conceptual framework and summarise the chapter. 

9 

# **2.2 Energy Access and Decentralised Electricity Generation in Nigeria** 

Studies of Nigeria’s energy situation describe persistent energy poverty and the need for improved supply and etering (Monyei et al., 2018), and estimated billing has been identified as a continuing problem for electricity consumers (Soyemi et al., 2021). 

Nigeria has a substantial solar resource, with solar radiation generally higher in the north of the country than in the south (Mohammed et al., 2013; Chanchangi et al., 2023). Solar photovoltaic (PV) systems are therefore among the technologies most often considered for improving access, particularly where extending conventional infrastructure is difficult or uneconomic. Off-grid and standalone systems typically combine PV modules, powerconditioning equipment, energy storage and electrical loads. Their technical and economic performance depends on correct sizing, energy management, storage and monitoring (Oladigbolu et al., 2020; Olatomiwa et al., 2015). 

Distributed generation also changes the relationship between those who produce and those who consume electricity. A household with a solar installation can potentially supply other users nearby. A participant who both produces and consumes electricity is described as a prosumer(Reddy et al., 2014), and this idea underlies research on local energy markets and peer-to-peer energy trading (Soto et al., 2021;Baig et al., 2021) For the present project, decentralised solar generation is the energy source around which the metering, prepaid billing and energy-discovery functions are organised. 

# **2.3 Solar Photovoltaic Energy Systems** 

Solar PV technology converts solar radiation directly into electrical energy using semiconductor devices. A standalone system typically consists of PV modules, a charge controller, battery storage, an inverter and the electrical loads. Where AC loads are supplied, 

10 

an inverter converts the available DC energy into AC electricity (Chanchangi et al., 2023). Because solar generation varies with weather and time of day, batteries store energy for later use, and the interaction between generation, storage and consumption makes monitoring an important part of managing standalone systems (Oladigbolu et al., 2020). 

Earlier work has used IoT-based monitoring to report the performance and operating conditions of PV systems. (Wibowo et al., 2024), for example, developed an IoT-based monitoring system for an on-grid PV installation using a NodeMCU ESP8266 and a PZEM-004T module and reported an average accuracy of 96.37% across the measured parameters. Such work shows the value of connecting energy systems to digital platforms. However, monitoring generation does not allocate electricity among several users. Where one installation supplies more than one consumer, the energy used by each must be measured separately through individual sub-metering (Numminen and Lund, 2019) The PAYGO system therefore concentrates on the consumption side of decentralised solar energy, managing user access and billing without replacing the PV generation or storage equipment (Mergulhão et al., 2026) 

# **2.4 Solar PV Module Degradation** 

Solar modules gradually lose the ability to produce electricity as they age. In this study, degradation means the slow reduction in a module’s maximum power output over time under comparable operating conditions. It is distinct from temporary reductions caused by shading, dirt or changes in sunlight, which are corrected by different actions. Module degradation is influenced by environmental exposure and operating conditions, and its measured rate depends on the module technology, the installation and the measurement method. 

11 

(Jordan and Kurtz, 2013)assembled nearly 2,000 degradation rates measured on individual modules and entire systems and reported a median value of 0.5% per year. A more recent meta-analysis by (Straub-Mück et al., 2025) examined 610 observations from 80 primary studies and reported a median degradation rate of 0.94% per year. They found that cell technology, mounting location and methodological choices significantly influenced the reported rates, and they predicted an average lifespan of 47 years for well-ventilated crystalline silicon modules in cold climates. The difference between the two medians, and the factors identified by the later study, show that degradation rates differ between studies, technologies and installations. 

Note that these values represent reported literature medians rather than guaranteed rates for a specific installation, nor are they empirical measurements from the PAYGO prototype. For illustration, a linear loss of 0.5% per year corresponds to an approximate 5% reduction in power output over ten years, whereas a loss of 0.94% per year results in a 9.4% reduction. Practically, this indicates that solar generation cannot be assumed constant over a system's service life, requiring operators to account for periodic inspection, maintenance, and eventual component replacement. 

# **2.5 Battery Ageing and Maintenance of Solar Systems** 

Batteries are usually the component of a standalone solar system that needs the most attention over time. (Vetter et al., 2005) reviewed the ageing mechanisms of lithium-ion batteries and described how repeated cycling and storage lead to capacity fade, power fade and rising impedance. Operating conditions such as temperature and the way the battery is charged and discharged influence the rate at which this occurs. (Xu et al., 2018) proposed a semi-empirical model that estimates the loss of battery life from an operating profile and 

12 

uses a cycle-counting method to identify stress cycles in irregular operation. Ageing behaviour differs between battery chemistries, and the studies cited here address lithium-ion cells in particular. 

Batteries are not the only components that need attention. Charge controllers, inverters, wiring and the modules themselves require periodic inspection, servicing and eventual replacement, and the costs of these activities recur over the life of the installation. An owner whose system serves only a single household may have no income from it with which to meet these costs. 

This is where the PAYGO concept becomes relevant. If an owner has surplus electricity and supplies it to nearby consumers on a prepaid basis, the payments for measured energy form a source of income that could contribute towards maintenance and operating costs. The amount depends on the energy supplied, the tariff and the number of consumers, and the project does not claim that this income will cover all maintenance expenses. The battery itself is not a subject of this research and no battery-management system is developed. The metering system is placed downstream of the power-conversion equipment so that it measures the energy used by the connected AC load. 

# **2.6 PAYGO Solar Energy Systems** 

Pay-As-You-Go (PAYGO) systems have been used to widen access to solar technology in developing countries. Instead of paying the full cost of a system at once, the customer makes smaller payments over time (Rolffs et al., 2015; Yadav et al., 2019). (Rolffs et al., 2015) examined PAYGO financing of solar home systems in Kenya and found that it fits existing social practices of paying for energy in small amounts. (Yadav et al., 2019) analysed the success of the model in Sub-Saharan Africa and its prospects in rural India, and described it 

13 

as a business model in which payments are made online in a flexible manner. (Barry and Creti, 2020) analysed PAYGO contracts held by 10,120 customers in Benin and concluded that in their case study PAYGO targets credit-worthy consumers, which raises doubts about whether it bridges the last-mile electrification gap. 

A typical PAYGO arrangement has three elements: an energy system that supplies electricity, a payment mechanism through which the customer pays for access, and a control mechanism through which payment status determines whether the system continues to operate. Digital communication allows these to be linked remotely, so that a payment made on a mobile or electronic platform updates the state of the equipment. 

The conventional model is concerned mainly with access to a solar product or service and its financing. The PAYGO platform in this project applies the same principle in a different way. A local solar owner supplies electricity to consumers, the energy used by each consumer is measured in kilowatt-hours, and that measurement reduces the consumer’s prepaid credit. The platform does not finance the purchase of solar equipment. Table 2.1 summarises the distinction. 

14 

Table 2.1 Conventional PAYGO solar financing compared with the PAYGO prepaid energy-billing platform 

|**Aspect**|**Conventional PAYGO solar financing**|**PAYGO prepaid energy-billing**<br>**platform**|
|---|---|---|
|What is paid for|Access to, or ownership of, a solar<br>product, paid in instalments|Measured electricity (kWh) supplied from<br>an existing installation|
|Purpose of<br>payment|Repayment of the cost of the equipment<br>over time|Purchase of energy credit; the income may<br>contribute to upkeep of the supplier’s<br>installation|
|Control mechanism|Equipment is enabled or disabled<br>according to payment status|Load is disconnected when the energy<br>credit is exhausted|
|Roleof metering|Not the primary function|Central: energy used by each connection<br>is measured and deducted from credit|
|Scale|Vendor and a customer base|Local supplier and nearby consumers|



# **2.7 Prepaid Electricity Metering** 

Prepaid metering requires the consumer to buy electricity credit before use. The meter reduces the available credit as energy is consumed and restricts supply when it is exhausted. In conventional postpaid billing, consumption is recorded before payment is requested, so the supplier carries the risk of late or unpaid bills. Prepaid metering links payment and consumption more directly (Jack and Smith, 2020; Alao et al., 2022). Jack and Smith, 2020 studied customers in Cape Town who were moved from monthly billing to prepaid meters. They found that electricity use fell after the switch, but the utility recovered more of what was owed to it and at lower cost, with the benefits differing between customers. In a prepaid meter, the credit remaining after a period of consumption can be expressed as: 



where _C r_ is the remaining credit, _C p_ is the credit purchased, _r_ is the energy tariff and _E_ is 

the energy consumed over the period. The process can be described as payment, credit 

15 

allocation, energy consumption, credit deduction and, when credit is exhausted, restriction of supply. 

Existing prepaid designs use microcontrollers, displays and communication modules to implement this process. (Quazi et al., 2011) built a prepaid meter on an AVR microcontroller with a GSM module so that credit could be added by SMS. (Rajput et al., 2018) modelled an Arduino-based prepaid meter using GSM technology. More recent designs add Internet connectivity. (Irianto, 2023)designed a prepaid smart energy meter monitoring system (PreSEMMS) for household use based on IoT, which links measured consumption to a prepaid balance. In many basic designs, however, the meter and the payment mechanism are treated as largely independent components. A connected architecture can instead join the meter, a backend transaction system and a user interface, and this is the approach adopted here. 

# **2.8 Smart Metering and Advanced Metering Infrastructure** 

Smart metering extends electronic metering by adding communication, processing and data management. A smart meter can measure consumption and transmit it to another system for monitoring, billing or analysis (Rashed Mohassel et al., 2014; Chen et al., 2023). Its distinguishing feature is therefore its ability to take part in a larger information system as well as to measure (Rind et al., 2023). Typical functions include remote measurement, consumption monitoring, remote configuration, prepaid billing and automated data collection. In distributed solar systems, smart metering can provide the per-consumer information needed for billing and energy management (Abed and Naser, 2020). 

Advanced Metering Infrastructure (AMI) is the wider system that collects, transmits, stores and processes data from smart meters. It generally consists of the meters, a communication 

16 

network, data-management facilities and applications for utilities or consumers (Rashed Mohassel et al., 2014;  Wan et al., 2019) In a utility setting it supports remote reading, remote connection and disconnection, and tariff management. Wan et al. (2019) demonstrated Narrowband IoT for AMI and showed that low-power wide-area technologies can support large-scale metering deployments. 

The Pay-As-You-Go (PAYGO) prototype adopts a simplified version of this arrangement, comprising an ESP32-based field meter, a communication layer, a backend platform, and a web application. Rather than functioning as a utility-scale Advanced Metering Infrastructure (AMI), the system represents a small-scale Internet of Things (IoT) metering architecture inspired by AMI principles and tailored for a local solar energy application. 

Metering is also relevant to electricity theft and non-technical losses. Smart and prepaid meters have been proposed as ways to reduce theft and tampering (Mohammed et al., 2013; Depuru et al., 2011; T. E et al., 2019). The present project does not implement a theftdetection algorithm and makes no claim to detect theft. Its contribution is that electronic metering, transaction records and remote monitoring give a more traceable link between energy used and payment made. 

# **2.9 Electrical Energy Measurement** 

Billing in a prepaid system depends on the quantity of electricity consumed, so electrical energy measurement is its technical foundation (Abed, 2020; Varela-Aldas et al., 2022). For a single-phase AC load, the relevant quantities are voltage, current, active power, power factor, frequency and accumulated energy. Active power is given by: 



17 

where P is the active power in watts, V is the RMS voltage, I is the RMS current and cos φ is the power factor. Energy is the integral of power over time: 



and, for constant power over a period t, 



where energy is standardly expressed in watt-hours (Wh) or kilowatt-hours (kWh) (VarelaAldás et al., 2022; El-Khozondar et al., 2024). Because the energy value computed by the meter determines the rate at which prepaid credit is depleted, measurement inaccuracies translate directly into billing errors. For that reason, the accuracy of the measurement subsystem must be empirically verified rather than assumed. 

# **2.10 PZEM-004T Energy Measurement Module** 

The PZEM-004T is a digital energy-monitoring module designed to measure electrical parameters on the alternating current (AC) side of a circuit. It captures voltage, current, active power, accumulated energy, frequency, and power factor, and transmits these readings digitally through a serial interface (Yasa et al., 2023). Because the module monitors the electricity consumed by the connected AC load, it does not directly measure direct current (DC) parameters such as solar-panel efficiency or battery health. According to the manufacturer's technical manual, the module operates across a voltage range of 80 to 260 V AC, supports active power loads up to 22 kW (at 220 V and 100 A), measures frequencies from 45 to 65 Hz, and communicates via Transistor-Transistor Logic Universal Asynchronous Receiver-Transmitter (TTL UART) using the Modbus-RTU protocol at 9600 baud (Abed and Naser, 2020). 

18 

Several empirical studies have evaluated the measurement accuracy of the PZEM-004T in microcontroller-based monitoring prototypes. Yasa et al. (2023) compared the module against a commercial power meter and reported a voltage error of 0.35% and a power error of 1.26%. Similarly, (Varela-Aldás et al., 2022) benchmarked the sensor against a commercial energy monitor and recorded an active power accuracy within 3% and an active energy accuracy within 2%. In a separate photovoltaic monitoring system developed by (Wibowo et al., 2024), the energy measurement accuracy was 93.92%, while the average accuracy across all monitored electrical parameters reached 96.37%. 

Integrating an external measurement module separates high-voltage sensing from the main controller, allowing the ESP32 to receive processed digital readings rather than performing analogue voltage and current measurements itself. Nevertheless, the inclusion of a commercial sensor module does not guarantee the accuracy of the entire prototype. Overall measurement reliability also depends on wiring quality, the current-sensing arrangement, calibration, and operating conditions; consequently, the performance of the completed device must be evaluated experimentally. 

# **2.11 Embedded Systems and the ESP32** 

An embedded system combines dedicated hardware and software to execute a specific operational function. Energy meters represent a practical application of embedded systems because they acquire electrical measurements, process the acquired data, and execute control actions (Abed and Naser, 2020; El-Khozondar et al., 2024). The ESP32 is a dual-core microcontroller equipped with integrated wireless networking capabilities (Abed and Naser, 2020), which eliminates the need for an external communication controller. In a related 

19 

implementation, El-Khozondar et al. (2024) employed an ESP32 in a smart energy monitoring system that measured voltage, current, active power, and cumulative energy consumption, transmitted the readings over Wi-Fi to the Blynk cloud platform, and dispatched user notifications via WhatsApp. 

Within the Pay-As-You-Go (PAYGO) meter architecture, the ESP32 serves as the central embedded controller rather than functioning merely as a wireless transceiver. Specifically, it acquires electrical measurements from the PZEM-004T module, updates the prepaid credit balance, maintains the local operating state of the unit, actuates the load-control relay, drives the local user display, and exchanges telemetry and control messages with the backend server, including the execution of authorised remote commands. Consequently, the microcontroller acts as the core interface linking the physical electrical circuit to the cloud software platform. 

# **2.12 Modbus RTU Communication** 

Modbus is an established industrial communication protocol for exchanging data between electronic devices. Its Remote Terminal Unit (RTU) variant operates over serial communication lines using a master-slave architecture (Urrea and Morales, 2019; VarelaAldás et al., 2022). In the present system, the ESP32 microcontroller operates as the master device, polling electrical measurements from the PZEM-004T slave module through its serial interface and subsequently processing the returned values for prepaid billing and cloud transmission (Abed and Naser, 2020; Varela-Aldás et al., 2022). In an investigation of Modbus-RTU communications for smart metering in building energy management systems, Urrea and Morales (2019) demonstrated that incorporating forward error correction in network segments susceptible to electromagnetic interference improves transmission 

20 

reliability. Adopting a standardised protocol establishes a well-defined interface between the sensing module and the main controller, thereby enhancing the modularity of the hardware design. 

# **2.13 Internet of Things in Energy Monitoring** 

The Internet of Things (IoT) connects physical devices to communication networks so that they can exchange data and support monitoring or control (El-Khozondar et al., 2024; Rind et al., 2023). A typical IoT energy-monitoring architecture comprises five core components: sensors or measurement devices, a processing unit, a communication network, a backend or cloud service and a user interface. Rind et al. (2023) reviewed smart energy meters from an IoT perspective, treating the meter as a combination of sensing, computing and communication nodes, and identified gaps that include limited use of the full range of available technology and a lack of interdisciplinary design. 

The PAYGO architecture follows this model. The PZEM-004T provides the measurements, the ESP32 processes and sends them, HTTPS transports the messages, the backend stores and processes the information and the web application presents it to users. Monitoring is thereby extended beyond the physical meter into an integrated software system. 

# **2.14 IoT Cybersecurity** 

Connecting a meter to the Internet creates security risks that isolated meters do not have. A compromised device or communication channel could expose energy data or allow unauthorised control of the connected load, and where credit has monetary value an attacker may also try to obtain energy without paying. 

For a prepaid energy platform the main concerns are the authentication of users and devices, 

the authorisation of commands that operate the relay or change credit, the protection of 

21 

payment and transaction data, the protection of stored credentials, protection against replayed messages, and the privacy of consumption data. The proposed system treats security as part of its architecture and not as a separate feature. The security properties claimed in this report must, however, correspond to mechanisms that were actually implemented and tested in the prototype. 

# **2.15 Digital Payment Systems and Energy Transactions** 

Digital payment systems provide the critical link between financial transactions and prepaid energy delivery. Existing Pay-As-You-Go (PAYGO) literature demonstrates how digital payment infrastructure underpins this model: online repayment serves as a distinguishing feature of PAYGO systems (Yadav et al., 2019), and the framework aligns with established household practices of purchasing energy in small, incremental amounts (Rolffs et al., 2015). In this study, the payment gateway, Paystack, confirms customer payment prior to the allocation of energy credit. The operational sequence follows five distinct stages: payment initiation, payment confirmation, transaction verification, energy-credit allocation, and device update. Rather than relying on repeated polling queries, the payment provider notifies the application of transaction state changes via automated event notifications known as webhooks. However, payment confirmation alone does not guarantee reliable credit delivery. To prevent the duplicate processing of identical payment events caused by network retries or race conditions, the system enforces idempotent processing governed by unique transaction identifiers. Consequently, the proposed architecture maintains the payment record and the energy-credit record as related yet distinct states, thereby separating the financial settlement from the physical delivery of energy credit to the end-user meter. 

22 

# **2.16 Peer-to-Peer Energy Trading** 

Peer-to-peer (P2P) energy trading enables energy producers and consumers, including prosumers, to participate directly in localised energy transactions (Soto et al., 2021; (Baig et al., 2021). In a comprehensive review of the literature, (Soto et al., 2021) identified key research domains encompassing trading platforms, optimisation, game theory, blockchain technology, and market mechanisms. Similarly, (Baig et al., 2021) designed and implemented an open-source Internet of Things (IoT) and blockchain-based P2P trading platform utilising an ESP32-S2 microcontroller, Node-RED, and the Message Queuing Telemetry Transport (MQTT) protocol, with trading activities recorded via a smart contract on a private Ethereum blockchain. Earlier foundational work by (Reddy et al., 2014) examined the integration, control, communication, and metering requirements of renewable energy-based smart grids, including the technical arrangements that facilitate local energy exchange. Rather than attempting to replicate a full decentralised P2P electricity market, the Pay-As-You-Go (PAYGO) platform developed in this study implements a simplified local arrangement in which consumers locate nearby participating suppliers and purchase prepaid energy directly from them. 

# **2.17 Local Energy Marketplaces** 

A local energy marketplace is a digital environment in which energy producers and consumers can interact. Such platforms can list available energy resources, display prices, match buyers and sellers and record transactions (Reddy et al., 2014). Local markets are relevant to distributed renewable energy because generation is geographically dispersed, and a consumer may benefit more from finding a nearby supplier than a distant one (Soto et al., 2021) 

23 

The marketplace in this project adds a geographical element to supplier selection. Rather than presenting all registered suppliers equally, the platform uses the distance between the consumer and each supplier in the discovery process. It should be regarded as a prototype location-aware discovery and matching feature. It does not show that a complete regulated electricity market has been established. 

# **2.18 The Haversine Formula and Location-Aware Matching** 

Where two locations are given by latitude and longitude, the Haversine formula gives the great-circle distance between them (Yunardi et al., 2024). 



where _d_ is the distance, _R_ is the radius of the Earth (about 6371 km), _φ_ ₁ and _φ_ ₂ are the latitudes in radians, _Δφ_ is the difference in latitude and _Δλ_ is the difference in longitude. (Yunardi et al., 2024) applied the formula in a geographic information system to search for the nearest sea-freight expedition services, and (Muttaqin et al., 2024) used it to find the closest minimarket. Both applications show its use for proximity-based search. 

In the proposed system the calculated distance is compared with a service radius, and a supplier is eligible for a consumer who is within that radius. This gives a simple way to implement location-aware discovery without a complex optimisation algorithm. The formula measures geographical distance only. It does not show whether a supplier has enough electricity available, and that must be established by other means. 

# **2.19 Distributed Energy Resources and Prosumers** 

Distributed Energy Resources (DERs) are small-scale resources located close to where energy is used, such as rooftop solar PV and battery storage (Reddy et al., 2014); Chen et 

24 

al., 2023). With distributed generation, electricity no longer flows only from central generators through the network to consumers, because consumers may also produce electricity and supply others. Such participants are called prosumers (Reddy et al., 2014; (Chen et al., 2023). Chen et al. (2023) reviewed the control and optimisation of power grids using smart meter data and pointed to the role of smart meters in supporting DER integration. The PAYGO concept is consistent with this model. A solar owner can act as a supplier and neighbouring households as consumers. The marketplace feature provides a way to find such suppliers, and the metering subsystem provides the measurement needed to account for the energy used. 

# **2.20 Web-Based Energy Monitoring** 

Web-based platforms give users remote access to data produced by IoT devices. For energy systems, dashboards can show voltage, current, power, energy consumption, balance and transaction history (Manowska et al., 2022); Irianto, 2023) Manowska et al. (2023) used a time-series database. Irianto (2023) used a smartphone application to monitor a prepaid energy meter. A web platform also provides an interface for managing users, devices and transactions, so that users need not interact directly with the embedded device. 

The proposed system uses a web application for these purposes. The web platform is the part of the architecture that users interact with, while the embedded device remains responsible for physical measurement and load control. 

# **2.21 Nigerian Regulatory Environment** 

The supply of electricity in Nigeria is governed by the Electricity Act 2023, which repealed the Electric Power Sector Reform Act 2005 (Federal Republic of Nigeria, 2023). The Nigerian Electricity Regulatory Commission (NERC) issues regulations under the Act, 

25 

including regulations for mini-grids. Mini-grid regulations distinguish between smaller systems of up to about 100 kW, which are registered with the Commission, and larger systems, which require a permit (Nigerian Electricity Regulatory Commission, 2026). These regulations have been revised since they were first issued, so the current text and the details of any obligations should be taken from NERC’s official documents. 

Whether a particular energy-sharing arrangement falls within these regulations is a legal question that this study does not settle. The PAYGO system is a proof-of-concept prototype for small-scale sharing and the project makes no claim that it has been approved by, or complies with, any regulatory requirement. Establishing the regulatory position for a real deployment would require confirmation with NERC. 

# **2.22 Review of Related Systems** 

Many of the functions of the proposed system have been implemented before, but usually one or two at a time. Table 2.2 summarises selected related systems and the aspects that the present project addresses differently. The comparison is intended to identify specific differences and does not claim that the proposed system is better overall. 

Table 2.2 Selected related systems and their relationship to the PAYGO platform 

|**Study**|**Approach**|**What it achieved**|**Aspect addressed**<br>**differently by PAYGO**|
|---|---|---|---|
|Wibowo et al.<br>(2024)|IoT monitoring of an on-<br>grid PV system using<br>NodeMCU ESP8266 and<br>PZEM-004T|Reported average accuracy of<br>96.37% across the measured<br>parameters|Monitors the system;<br>PAYGO adds prepaid credit,<br>billing and relay-based load<br>control|
|Yasa et al.<br>(2023)|IoT electrical power<br>recording using ESP32<br>and PZEM-004T|Validated the sensor against<br>a commercial meter (voltage<br>error 0.35%, power error<br>1.26%)|Records power; PAYGO adds<br>credit management and<br>payment|
|El-Khozondar et<br>al. (2024)|ESP32 energy monitoring<br>with the Blynk platform<br>and WhatsApp<br>notifications|Real-time monitoring of<br>voltage, current, power and<br>cumulative consumption|Monitoring and notification<br>only; no prepaid billing or<br>load control|



26 

|**Study**|**Approach**|**What it achieved**|**Aspect addressed**<br>**differently by PAYGO**|
|---|---|---|---|
|Irianto (2023)|IoT-based prepaid smart<br>energy meter for<br>household use (Pre-<br>SEMMS)|Linked measured<br>consumption to a prepaid<br>balance|Household meter; PAYGO<br>adds backend transactions,<br>digital payment and supplier<br>discovery|
|Rajput et al.<br>(2018); Quazi et<br>al. (2014)|Arduino or AVR meters<br>with GSM-based prepaid<br>recharge|Showed that prepaid recharge<br>by mobile messaging is<br>feasible|SMS-based; PAYGO uses<br>Wi-Fi, HTTPS and online<br>payment with a web platform|
|Mohammad et<br>al. (2013)|Prepaid meter with PIN<br>scratch-card recharge by<br>SMS|Low-cost recharge without<br>Internet connectivity|No remote monitoring or<br>location-aware discovery|
|Baig et al.<br>(2021)|IoT and blockchain P2P<br>energy trading using<br>ESP32-S2, Node-RED and<br>MQTT|Recorded trading activity on<br>a private blockchain with<br>smart contracts|Focus on trading records;<br>PAYGO focuses on prepaid<br>metering, load control and<br>distance-based discovery<br>without a blockchain|



(Wibowo et al., 2024) and (Yasa et al., 2023) show that the PZEM-004T and low-cost microcontrollers can measure and report electrical parameters with useful accuracy. Their systems record and display consumption. The present project extends the measurement concept to prepaid consumption, so that measured energy reduces a credit balance and the load is disconnected when the credit is exhausted.(Irianto, 2023) combined prepaid credit with IoT monitoring in a household meter. The PAYGO platform places a similar function inside a platform with payment confirmation and a link between suppliers and consumers. The GSM-based prepaid meters of(Quazi et al., 2011) and (Rajput et al., 2018) and the SMS recharge system of Mohammad et al. (2013) rely on mobile messaging for communication and recharge. This is a valid approach, especially where Internet access is limited. The proposed system instead uses Wi-Fi, HTTPS messaging and a payment service. The two approaches make different trade-offs and neither is shown here to be superior. (Baig et al., 2021) address energy exchange between prosumers using a blockchain ledger, whereas the 

27 

proposed platform records transactions in a conventional database and concentrates on the physical meter and on finding nearby suppliers by distance. 

# **2.23 Research Gap** 

Existing studies have examined solar monitoring, prepaid electricity metering, IoT-based energy management and peer-to-peer energy trading. At the same time, the literature on PV degradation and battery ageing shows that solar installations lose performance and need maintenance, which creates recurring costs for their owners. There is a need for an integrated small-scale system through which an owner can supply nearby consumers and receive payment according to measured consumption. Such a system must combine: 

1. measurement of the electricity supplied to individual consumers; 

2. prepaid energy-credit management; 

3. automatic load control based on available credit; 

4. digital payment and transaction records; 

5. remote device communication and monitoring; and 

6. location-aware discovery of nearby solar-energy suppliers. 

The gap addressed by this research is therefore not a new measurement principle or a new market algorithm. It is the integration of these established technologies in one small-scale platform for prepaid solar energy sharing, together with an evaluation of whether the integrated prototype works as intended. PAYGO is proposed in response to this gap. 

# **2.24 Conceptual Framework** 

The conceptual framework of the proposed system is shown in Figure 2.1. The physical subsystem consists of the solar source, the power-conversion and storage equipment, the PAYGO meter and the consumer load. The meter measures the energy consumed and 

28 

controls the load through a relay. The communication layer, which uses HTTPS carries measurements and heartbeat information from the meter to the backend and commands from the backend to the meter. The backend manages users, devices, energy records, transactions and credit, and is connected to the payment service, the energy marketplace and the web 

application. 



<!-- Start of picture text -->
i ‘Owner's solar system H<br>| peceececeneecnnennnnenny1| Web application<br>itit Solar PV modules iit Owners and consumers<br>itannri rns, Aeneait<br>Hy { Charge controller, battery, inverter | |<br>po Tommsmesesessesesceses? Backend platform<br>{__Civended supply: gid used intesing) Users and devices<br>| Energy records<br>AC supply Transactions<br>‘ Energy credit<br>HTTPS over Wi-Fi ey<br>PAYGO prepaid energy meter |g¢—___»<br>PZEM-004T energy measurement eanbenibciane<br>ESP32 controller sync, acknowledgement<br>Display<br>Load relay<br>Payment service Energy marketplace<br>Controlled¥ supply Ma Paystack) ened Location matchin;8<br>Consumer AC load<br><!-- End of picture text -->

Figure 2.1 Conceptual framework of the proposed PAYGO system 

29 

# **2.25 Summary** 

This chapter has reviewed the literature behind the PAYGO platform as a connected argument. Decentralised solar systems can help to improve electricity access in Nigeria. Research on PV degradation and battery ageing shows that these systems lose performance and require maintenance, which creates recurring costs for owners. Supplying surplus electricity to nearby consumers on a prepaid basis could provide income that contributes towards those costs, although the amount is not guaranteed and the project does not claim that it will cover all expenses. 

Research on PAYGO financing, prepaid metering and smart metering shows how payment can be linked to measured consumption, and embedded systems, IoT communication and digital payment make this possible at small scale. The ESP32 and PZEM-004T provide processing and measurement, HTTPS carries the data, and the Haversine formula supports the location-aware discovery of suppliers. Existing systems address these functions individually. The gap identified is their integration in one small-scale platform, and Chapter Three presents the methodology used to design, implement and evaluate it. 

30 

## **3CHAPTER THREE** 

# **METHODOLOGY** 

# **3.1 Introduction** 

This chapter explains how the PAYGO solar energy metering and billing system was designed, developed, assembled, integrated and tested, and how its performance was evaluated. It follows from the objectives outlined in Chapter One and the research gap identified in Chapter Two. The chapter describes the system design and test procedures only, while the measured results, test tables and percentage errors are presented in Chapter Four. The system is a proof-of-concept prototype for small-scale solar energy sharing. It measures the AC electricity consumed by a connected load, manages prepaid energy credit and controls the load according to the available credit. It does not measure solar panel degradation, battery condition or the overall efficiency of the solar installation. 

# **3.2 Research Design** 

The study adopted an engineering design and development approach. First, the problem was defined and the system requirements were specified. Next, an overall system architecture was proposed, after which the hardware and software subsystems were developed in parallel. The hardware subsystem comprised an embedded energy meter, while the software subsystem consisted of a backend service, a database and a web application. 

Following parallel development, the two subsystems were integrated and tested in two stages: individual unit testing of components and end-to-end integration testing of the complete workflow. Conducting component-level tests prior to integration simplified fault isolation. Finally, the performance of the integrated prototype was evaluated against the specific objectives outlined in Chapter One. 

29 

# **3.3 System Requirements**

The system requirements were derived from the project objectives and intended use in a small-scale distributed energy setting.

**Table 3.1 Functional and non-functional requirements**

| Type | Requirement |
|---|---|
| Functional | Measure single-phase AC voltage, current, active power, frequency, power factor and cumulative energy using the PZEM-004T. |
| Functional | Calculate energy consumption and maintain the prepaid balance locally on the ESP32. |
| Functional | Control the connected load using a relay according to the available prepaid balance. |
| Functional | Display meter information locally and preserve essential balance information across power interruptions. |
| Functional | Communicate with the backend over HTTPS for device heartbeat and balance synchronisation. |
| Functional | Process digital payments through the backend and record verified payment transactions. |
| Functional | Provide user and device management, transaction history, consumption summaries and CSV export through the web application. |
| Functional | Support location-based discovery of energy listings using geographical coordinates and configured service radii. |
| Non-functional | Protect authenticated operations and verify payment notifications. |
| Non-functional | Prevent duplicate payment processing and maintain consistency between server-side and local prepaid balances. |
| Non-functional | Support local metering and balance operation during temporary network unavailability, followed by synchronisation when connectivity returns. |
| Non-functional | Provide modular software and a responsive web interface. |

# **3.4 Overall System Architecture**

The PAYGO architecture consists of an embedded metering unit, a communication interface, a backend service, a database, external payment processing and a web application. The ESP32 forms the embedded control layer and interfaces with the PZEM-004T module, relay and local display. The PZEM-004T provides electrical measurements to the ESP32 through a UART connection using Modbus RTU.

The embedded device communicates with the backend through HTTPS over Wi-Fi. Device communication is used for heartbeat reporting and prepaid balance synchronisation. The firmware performs local energy accounting and load control; it does not rely on an MQTT credit command or a physical transaction-acknowledgement message.

The backend is implemented using Node.js, Express and TypeScript. It provides REST API routes for authentication, device operations, payment processing, transactions and marketplace functions. PostgreSQL stores device balances, payment transactions and consumption readings. Paystack is used as the external payment service.

The presentation layer is a Next.js web application. It communicates with the backend through its REST API and provides account access, device information, payments, transaction history, consumption reporting and marketplace functions. The web application does not connect directly to the meter or database.

**Figure 3.1** should illustrate the actual data flow: PZEM-004T measurements to ESP32; local balance and relay control on the ESP32; HTTPS heartbeat and balance synchronisation between ESP32 and Express backend; PostgreSQL persistence; Paystack payment notification to the backend; and the Next.js application communicating with the backend through the REST API.

# **3.5 Hardware Design and Implementation** 

# **Hardware components** 

The meter is built around the following components, which are shown in Figure 3.2. The ESP32 is the main embedded controller. It reads the measurements, keeps the prepaid balance, controls the relay and communicates with the backend over Wi-Fi. The PZEM-004T is the AC measurement module and supplies voltage, current, active power, energy, frequency and power factor through a serial interface (Abed, 2020). A relay switches the connected load on and off under the control of the ESP32. A local display shows information to the user, and a low-voltage DC supply powers the electronics. 

# **Electrical arrangement** 

In the intended application the meter sits between the AC output of the owner’s solar system and the consumer’s load. The meter responds only to the AC supply and the load, and does not depend on what generates the supply. For this reason the experiments use the grid supply as the AC source, and a solar installation is not needed to test the metering, billing and loadcontrol functions. The measurement and control path is therefore AC source, PZEM-004T, relay and load. Because the experiments involve mains voltage, the circuit should be housed 

in an insulated enclosure and the tests carried out with appropriate safety precautions. 

33 



<!-- Start of picture text -->
AC supply PZEM-004T Relay<br>Grid (testing); Voltage input and Load switching ee<br>owner's solar AC current sensor<br>output (intended)<br>(Modbus-RTU) control<br>ESP32 controller<br>Low-voltage DC pe Prepaid balance, relay logic, |/-—> Display<br>supply Wi-Fi communication<br>Wi-Fi (HTTPS)<br>ses AC power path —— signal / data /DC<br><!-- End of picture text -->

Figure 3.2 Hardware block diagram of the PAYGO meter 

34 



<!-- Start of picture text -->
xs fa eee [OW Seer<br>POWER INPUT & REGULATION CIRCUIT<br>i] BUZZER CIRCUIT<br>aes ; RELAY CIRCUIT<br>ie<br>Leo a pzeM CIRCUIT<br><!-- End of picture text -->

Figure 3.3 Circuit schematic of the PAYGO meter 

35 



Figure 3.4 A picture of the assembled hardware 

# **Electrical energy measurement** 

The ESP32 requests measurements from the PZEM-004T over its UART interface using the Modbus-RTU protocol (Abed, 2020). Active power, energy and the related quantities follow Equations (2.1) to (2.3). The accumulated energy is converted to kilowatt-hours for the billing process. The measurement observations are discussed in Chapter Four. A calibrated reference instrument was not available, so measurement accuracy is not established. 

# **3.6 Embedded Firmware Design**

The embedded firmware runs on the ESP32 and performs electrical measurement acquisition, energy accounting, local balance management, relay control, display updates and backend communication.

The ESP32 obtains voltage, current, active power, cumulative energy, frequency and power-factor measurements from the PZEM-004T through its UART interface using Modbus RTU. Energy consumed over an interval is determined from the change in the cumulative energy reading. The resulting consumption is used to update the local prepaid balance.

The balance is maintained locally and persisted using ESP32 Preferences storage. The relay is controlled according to the local prepaid balance, while the display presents relevant meter and balance information. A low-balance buzzer function is also implemented in the firmware.

The firmware communicates with the backend over HTTPS. It periodically sends a heartbeat and synchronises its balance with the server. When connectivity is unavailable, local metering and balance control can continue; synchronisation takes place when communication is restored.

The balance relationship is:

\[
B_{new}=B_{previous}+E_{credited}-E_{consumed}
\]

where the balance and energy quantities are expressed in kilowatt-hours (kWh).

# **3.7 Backend Design and Implementation**

The backend is implemented using Node.js, Express 5 and TypeScript. It provides the REST API used by the web application and the HTTPS endpoints used by the embedded meter. The application is organised into routes, middleware and service modules to separate request handling, authentication and business logic.

The backend includes routes for user authentication, device operations, payment initiation, Paystack webhook processing, transaction records and marketplace operations. Authentication middleware and role-based checks protect applicable user operations.

PostgreSQL is used for persistent storage. Device records contain identifiers, balance information and connection-related timestamps. Payment transactions store payment references and monetary and energy-credit information. Consumption readings are stored separately in the `meter_readings` table. The production migration `20261119_multi_device_metering.sql` introduced the multi-device metering and consumption-reading structure. A database trigger routes consumption records generated through balance synchronisation into `meter_readings`, allowing reporting to aggregate consumption independently of financial top-up transactions.

The backend provides consumption-reporting endpoints that aggregate recorded kilowatt-hour values over supported periods. The web application uses these endpoints to display consumption summaries and generate CSV exports.

# **3.8 Payment and Prepaid Credit Management**

The payment process begins when a user initiates a top-up from the web application. The application sends the request to the Express backend, which initialises the payment with Paystack and returns payment information to the user interface.

After payment, Paystack sends a notification to the backend webhook. The backend verifies the notification using HMAC-SHA512 signature validation before processing it. Payment references and database constraints support duplicate-event prevention. The amount paid in naira is stored separately from the energy quantity credited in kilowatt-hours.

The energy equivalent of a verified payment is determined using:

\[
E_{credit}=\frac{A}{p}
\]

where \(E_{credit}\) is the energy credit in kWh, \(A\) is the payment amount in naira and \(p\) is the configured tariff in naira per kWh.

Following successful payment verification, the backend updates the server-side device balance and records the top-up transaction. The embedded meter obtains the authoritative balance through its HTTPS heartbeat and balance-synchronisation process. The firmware then synchronises its local balance with the server-side value.

This implementation should not be described as an MQTT credit-command workflow. The firmware does not subscribe to the backend MQTT credit topic. A backend transaction status must not be presented as proof that the physical meter returned a transaction-specific acknowledgement.

**Figure 3.5** should show: web application initiates payment; backend initialises payment with Paystack; Paystack sends a signed webhook; backend verifies the signature and payment reference; backend records the top-up and updates the server-side balance; ESP32 sends an HTTPS heartbeat; backend returns the authoritative balance; and ESP32 synchronises its local balance.

# **3.9 Device Communication and Balance Synchronisation**

The embedded meter communicates with the backend over HTTPS. Heartbeat requests allow the backend to update the device's last-seen information and return the authoritative server-side balance. The firmware synchronises its local balance with this value.

The meter performs energy measurement and local balance accounting independently of the web application. It does not transmit every raw PZEM-004T voltage, current, power and frequency sample to the backend as a continuous telemetry stream. Consumption information is reflected in the backend through balance updates and the associated consumption-recording process.

When the network is unavailable, the firmware can continue local metering and load control using its persisted balance state. When connectivity returns, heartbeat and balance synchronisation allow the device and backend to reconcile their balance information. This is the implemented communication workflow; it does not use an MQTT credit command or a transaction-specific physical acknowledgement from the meter.

# **3.10 Local Energy Marketplace**

The marketplace allows a prosumer to publish an energy listing and a buyer to discover listings that may serve the buyer's location. A user account can support both buyer and prosumer capabilities. An energy source represents the supplier's registered source, while an energy listing represents the energy quantity and terms offered through the marketplace.

At purchase time, the buyer supplies a location. The backend compares this location with the coordinates associated with available listings and evaluates whether the buyer falls within each listing's configured service radius. Geographic distance is calculated using the Haversine formula.

The distance calculation supports location-based discovery; it does not independently verify physical energy availability or guarantee delivery. The marketplace is a prototype software feature and is not a regulated electricity-market settlement or dispatch system.

# **3.11 Web Application Design**

The user interface is implemented as a Next.js progressive web application and is accessible through mobile and desktop browsers. It communicates with the Express backend through REST API requests and does not connect directly to the PostgreSQL database or communicate directly with the meter.

The application supports user authentication, device and balance information, payment initiation, transaction history and marketplace functions. Its consumption-reporting interface retrieves aggregated readings from the backend and supports period selection and CSV export. The exported consumption data contains date-based energy values in kWh; it is not a historical export of raw voltage, current, active-power or frequency samples.

# **3.12 System Integration**

System integration was carried out across the embedded hardware, firmware, backend, database, payment service and web application. The PZEM-004T and ESP32 form the measurement and control unit. The firmware performs local energy accounting and relay control, while HTTPS provides the communication path for heartbeat and balance synchronisation.

The backend provides the application API and stores device, payment and consumption records in PostgreSQL. Paystack is integrated for payment processing. The Next.js web application accesses these services through the backend REST API and provides the user-facing functions, including consumption reporting and CSV export.

The production database migration for multi-device metering and consumption readings was applied. Consumption records are stored in `meter_readings` and made available to the reporting endpoint. The integration was evaluated using the functional observations and results presented in Chapter Four.

**Table 3.3 Test plan and evaluation status**

| Test area | Evaluation approach | Evidence or status |
|---|---|---|
| Electrical measurement response | Observe meter readings under connected loads and compare behaviour as the load changes. | Functional load observations recorded; no calibrated reference meter was available for accuracy testing. |
| Prepaid balance management | Observe local balance handling and synchronisation with the backend. | Implemented; report only behaviours directly observed during testing. |
| Relay load control | Test physical load disconnection and reconnection. | Physical cut-off and reconnection test passed. |
| HTTPS device communication | Check device heartbeat and balance synchronisation. | Implemented in firmware and backend; do not infer unobserved performance metrics. |
| Payment processing | Verify payment notification handling and server-side balance update. | Paystack verification and processing implemented; no invented transaction values or physical meter acknowledgement. |
| Consumption storage and reporting | Check database reading storage, reporting endpoint and CSV export. | Production migration applied; CSV export produced a consumption record. |
| Marketplace | Check location and service-radius matching logic. | Implemented as a prototype software feature. |
| Integrated operation | Consider combined operation of hardware and software components. | Functional prototype demonstrated; extended field and accuracy testing remain future work. |
| Backend unit tests | Execute isolated tests for appliance-load calculations, Haversine distance/radius rules and access-control middleware. | 18 test cases are present in the proposed backend test branch; execution results have not yet been recorded. |
| Backend API/functional tests | Exercise HTTP endpoints for health, authentication, payment initiation, webhook validation, device access and transaction verification. | 24 test cases are present in the proposed backend test branch; several database/payment interactions are mocked. Execution results have not yet been recorded. |

# **3.13 Performance Evaluation and Data Analysis**

The evaluation distinguishes direct experimental observations, software-function checks and calculated quantities. The available tests establish functional behaviour of the prototype; they do not constitute a complete calibration exercise.

For a measured quantity \(X_m\) and corresponding reference quantity \(X_r\), percentage error may be calculated as:

\[
\%E=\frac{|X_m-X_r|}{X_r}\times100
\]

For \(n\) repeated observations \(x_i\), the arithmetic mean is:

\[
\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_i
\]

A calibrated reference energy meter was not available during the reported tests. Consequently, percentage measurement error and an accuracy result are not reported. The equations are retained as the appropriate method for future comparative testing.

For exported energy records \(E_i\), a total over the selected export period can be calculated as:

\[
E_{total}=\sum_{i=1}^{n}E_i
\]

The available export contains one record of 0.058 kWh dated 21 November 2026. It is reported as an actual exported record and is not extrapolated to represent other days or longer periods.

# **3.14 Security and Reliability Considerations**

The backend verifies Paystack webhook notifications using HMAC-SHA512 signature validation before processing payment events. Payment references and database constraints support idempotent handling of repeated notifications. Authenticated routes and role checks restrict access to protected application operations.

The meter and backend communicate through HTTPS. The firmware maintains local balance information and persists essential state using ESP32 Preferences storage. This supports local operation during temporary network interruption, while heartbeat-based synchronisation allows the device to reconcile its balance with the backend after connectivity is restored.

These mechanisms reduce specific risks associated with unauthorised payment notifications, duplicate payment processing and temporary network loss. They do not constitute a complete cybersecurity assessment or certification of the prototype.

# **3.15 Methodological Limitations**

The prototype is a small-scale engineering implementation and is not a certified utility meter. The available electrical observations were obtained using the prototype display and connected test loads. A calibrated reference instrument was not available, so measurement accuracy and percentage error could not be established.

The reported load tests were conducted using a single-phase AC supply. The prototype was designed with distributed solar energy applications in mind, but the reported tests do not establish long-term operation on a field-installed solar system. The available CSV evidence contains a limited consumption record and does not establish daily, weekly or monthly consumption trends.

The marketplace is a software prototype for location-based listing discovery. It does not verify physical energy availability, perform grid dispatch or establish regulatory approval for electricity trading. The evaluation also does not establish long-term component durability, large-scale performance or commercial viability.

These limitations define the extent of the conclusions drawn in Chapter Four and provide areas for further development.

# **CHAPTER FOUR**

# **RESULTS AND DISCUSSION**

## **4.1 Introduction**

This chapter presents the results obtained from the functional evaluation of the PAYGO prototype. The discussion covers electrical measurement observations, response to changes in connected load, prepaid load-control operation, device and backend integration, and consumption reporting. Results are separated into direct observations and software implementation evidence. No measurement-accuracy claim is made because a calibrated reference meter was not available.

## **4.2 Description of the Implemented Prototype**

The implemented prototype consists of an ESP32-based metering and control unit interfaced with a PZEM-004T energy measurement module, a relay, a local display and supporting power circuitry. The firmware performs local energy accounting, maintains the prepaid balance and controls the connected load. The device communicates with the backend over HTTPS.

The software platform consists of a Node.js and Express backend, a PostgreSQL database and a Next.js web application. Paystack is integrated for payment processing. The application provides device and balance information, transaction records, consumption reporting and CSV export. The marketplace provides location-based discovery of energy listings.

**Figure 4.1:** Photograph of the assembled PAYGO hardware prototype.  
**Figure 4.2:** Photograph of the meter LCD during the combined-load test.  
**Figure 4.3:** Screenshot of the PAYGO consumption-reporting interface.

## **4.3 Electrical Measurement and Load-Response Test**

The meter was observed under a single-phase AC supply. The LCD indicated approximately 228 V and 50 Hz.

A combined-load test was conducted using a pressing iron rated at 1.6 kW and a laptop charger rated at 65 W. While the iron's heating element was operating, the LCD displayed a current of 6.24 A and active power of approximately 1.26 kW. When the iron's thermostat switched off the heating element, the displayed active power decreased to approximately 104 W while the laptop charger remained connected.

**Table 4.1 Electrical observations during the load test**

| Test condition | Current displayed | Active power displayed |
|---|---:|---:|
| Pressing iron heating and laptop charger connected | 6.24 A | 1.26 kW |
| Iron heating element switched off; laptop charger remained connected | Not recorded | 104 W |

The decrease in displayed power is consistent with the operation of a thermostatically controlled pressing iron. When the heating element is energised, it draws substantial power. When the thermostat interrupts the heating element, the remaining connected load is primarily the laptop charger and any small residual appliance consumption.

The iron's 1.6 kW rating represents its nominal rated power, not a value that must be drawn continuously. The observed combined power of 1.26 kW is reported as the meter's displayed reading under the test condition, rather than as a direct measurement of the iron's rated power.

A consistency calculation can be made from the reported voltage, current and active-power observations. Apparent power is:

\[
S=VI=228\times6.24=1422.72\ VA
\]

The implied power factor is:

\[
PF=\frac{P}{S}=\frac{1260}{1422.72}\approx0.886
\]

This is a calculated value based on the reported display readings. It is not an independently verified power-factor measurement. The observations demonstrate the meter's response to a change in connected load, but do not establish measurement accuracy.

## **4.4 Prepaid Balance and Relay Operation**

The firmware maintains the prepaid energy balance locally and uses the balance state to control the load relay. Essential balance information is persisted using ESP32 Preferences storage.

The physical relay cut-off and reconnection test was successfully completed. This confirms that the relay control mechanism could disconnect and reconnect the connected load during the test. It does not establish long-term relay endurance or performance under every possible load condition.

**Table 4.2 Summary of prepaid load-control evaluation**

| Evaluation item | Result |
|---|---|
| Local prepaid balance handling | Implemented in firmware |
| Persistent balance storage | Implemented using ESP32 Preferences |
| Relay cut-off test | Passed |
| Relay reconnection test | Passed |
| Long-duration relay endurance | Not evaluated |

## **4.5 Device-to-Backend Communication**

The ESP32 firmware communicates with the backend through HTTPS. The device sends heartbeat and balance-synchronisation information, while the backend provides the authoritative server-side balance for synchronisation.

This design allows the embedded meter to perform local metering and load control without requiring a continuous network connection for every measurement. When network connectivity is restored, the device can communicate with the backend and synchronise its balance.

The device communication should be distinguished from an MQTT-based credit-command architecture. The firmware used in this prototype does not subscribe to the backend MQTT credit topic. A server-side payment or transaction status is not treated as proof of a transaction-specific acknowledgement from the physical meter.

## **4.6 Consumption Recording and CSV Export**

The backend stores consumption readings in the `meter_readings` table. The multi-device metering migration, `20261119_multi_device_metering.sql`, was applied to the production database. The backend provides an endpoint that retrieves and aggregates consumption readings for supported reporting periods. The web application uses this information to display consumption summaries and provide CSV export.

The CSV export generated the following record:

**Table 4.3 Exported consumption record**

| Date (UTC) | Energy consumed |
|---|---:|
| 2026-11-21T00:00:00.000Z | 0.058 kWh |

The exported value represents recorded energy consumption of 0.058 kWh for the date represented in the export. This provides evidence that the consumption-reporting pipeline returned an exportable record.

The CSV contains date-based energy values in kilowatt-hours. It does not contain historical raw samples of voltage, current, active power or frequency. Since only one exported record is available, it is not used to infer consumption for other days or to claim a long-term consumption pattern.

## **4.7 Payment and Balance Management**

The backend integrates Paystack payment initiation and webhook processing. Payment notifications are verified using HMAC-SHA512 signature validation, and payment references support duplicate-event prevention. Verified payments are recorded by the backend and used to update the server-side prepaid balance.

The meter obtains the authoritative balance through HTTPS heartbeat and balance synchronisation. The implementation therefore links payment processing to the prepaid balance without relying on an MQTT credit command or a physical transaction-specific acknowledgement.

No numerical payment transaction is presented in this chapter because a corresponding verified payment record was not supplied as experimental evidence. The payment integration is described as an implemented software function, not as a quantified payment-performance result.

## **4.8 Location-Aware Energy Marketplace**

The marketplace supports energy-source and listing management and location-based discovery. A buyer supplies a location, and the backend compares it with the coordinates and service radius associated with available listings. The Haversine formula is used to estimate geographic distance.

The marketplace demonstrates the software logic for location-based discovery. It does not confirm the physical availability of energy at a listing or constitute a deployed electricity trading and settlement service.

## **4.9 Software Unit and Functional Testing**

In addition to the physical prototype evaluation, automated tests have been prepared for the PAYGO backend. The tests use the Node.js native test runner through `tsx --test`. They are divided into unit tests, which check isolated calculations and middleware behaviour, and API/functional tests, which exercise HTTP routes using a locally started Express application.

The test cases described below are present in the proposed backend testing branch. They are documented here as implemented test cases and expected assertions. A test case being present in the source code does not, by itself, establish that it has passed. No pass percentage or successful execution total is claimed until the test commands have been run and their terminal or CI output has been saved.

### **4.9.1 Unit tests**

Eighteen unit test cases are defined across three test files.

**Table 4.4 Backend unit test coverage**

| Test file / module | Test coverage | Expected result asserted in code |
|---|---|---|
| `loadAssessment.test.ts` | Connected load and simultaneous demand | 240 W fixture demand; 288 W after applying a 20% safety margin |
| `loadAssessment.test.ts` | Apparent power and starting surge | 353.33 VA requested apparent power and 953.33 VA requested starting surge for the defined test catalogue |
| `loadAssessment.test.ts` | Simultaneous appliance quantity | Five installed 10 W appliances with two operating simultaneously produce 20 W simultaneous demand |
| `loadAssessment.test.ts` | Custom appliance rating | A valid 18 W override is accepted and used in the load calculation |
| `loadAssessment.test.ts` | Input validation | Invalid quantities, duplicate appliance selections, empty selections, invalid safety margins and invalid custom wattages are rejected |
| `marketplace.test.ts` | Coordinate validation | Valid latitude and longitude values are accepted; out-of-range and non-numeric coordinates are rejected |
| `marketplace.test.ts` | Haversine distance | Identical coordinates return 0 m; test coordinate pairs are checked against approximate distances of 178 m and 1.78 km |
| `marketplace.test.ts` | 50 m service-radius boundary | A distance of 50 m is included at a 50 m radius, while 51 m is excluded |
| `marketplace.test.ts` | Effective service radius | The smallest applicable buyer radius, seller service radius and platform maximum is selected |
| `marketplace.test.ts` | Listing inventory rule | The test fixture rejects a 7 kWh request where only 6 kWh remains sellable |
| `security.test.ts` | Device authentication | A hardware request without a device API key is rejected with HTTP 401 and does not proceed to the next middleware |
| `security.test.ts` | Administrator authorisation | A user with the OWNER role is rejected by the ADMIN-only middleware with HTTP 403 |
| `security.test.ts` | Administrator authorisation | An authenticated user with the ADMIN role is allowed through the administrator guard |
 
The load-assessment values are calculated from the artificial appliance catalogue defined in the unit test. They are software test fixtures, not measurements from the physical PAYGO meter. Likewise, the coordinate pairs are deterministic mathematical test inputs and are not field GPS measurements.

### **4.9.2 API and functional tests**

Twenty-four API/functional test cases are defined in `endpoints.test.ts`. The test starts the Express application on a local ephemeral HTTP port and sends HTTP requests to its routes. Several database and external-service operations are replaced with mocked responses so that route behaviour can be checked without making live payment transactions.

**Table 4.5 Backend API and functional test coverage**

| Functional area | Test performed | Expected response or behaviour |
|---|---|---|
| Health endpoint | Request the health route | HTTP 200 with server status metadata |
| Authentication | Register without required fields | HTTP 400 validation response |
| Authentication | Register a valid test user | HTTP 201 with a user and authentication token |
| Authentication | Log in with valid mocked credentials | HTTP 200 with a user and authentication token |
| Routing | Request an unknown endpoint | HTTP 404 |
| Payment initiation | Omit the device identifier | HTTP 400 |
| Payment initiation | Submit an amount below the configured minimum | HTTP 400 |
| Payment initiation | Mock a successful Paystack initialisation | HTTP 200 with a checkout URL and payment reference |
| Paystack webhook | Submit an invalid HMAC signature | HTTP 401; webhook rejected |
| Paystack webhook | Submit a valid signed success event using mocked database operations | HTTP 200; the handler follows the success processing path |
| Paystack webhook | Replay a previously processed payment reference | HTTP 200 duplicate response; mocked query path indicates no second credit |
| Device access control | Request protected platform device information without authentication | HTTP 401 |
| Hardware access control | Submit balance, heartbeat, acknowledgement, energy and token requests without a device API key | HTTP 401 responses |
| Transaction verification | Query an unprocessed payment reference | Pending response |
| Transaction verification | Query a mocked existing token record | Success response with token details |
| Legacy hardware lifecycle simulation | Simulate an accepted MQTT credit acknowledgement | Mocked transaction status is expected to become CONFIRMED |
| Legacy firmware idempotency simulation | Process the same transaction identifier twice in a simulated ESP32 handler | The simulated balance remains 25 kWh after the duplicate |
| Fallback token simulation | Redeem a token marked `auto_credited = true` | The mocked database path must not add the energy balance a second time |
| Offline payment simulation | Simulate the payment handler's pending hardware state and fallback-token record | Assertions check the expected database query path |

The API tests provide evidence of the assertions encoded in the test suite, but they are not equivalent to a live production test. In particular, the mocked Paystack initialisation does not demonstrate a real payment, and mocked database operations do not establish that a production PostgreSQL transaction completed successfully.

The legacy MQTT lifecycle tests also require careful interpretation. The current PAYGO firmware obtains the authoritative balance through HTTPS heartbeat and balance synchronisation. The physical prototype should therefore not be described as having passed an MQTT credit-command or transaction-specific hardware acknowledgement test. The MQTT-related cases are retained as software simulations of legacy handler behaviour and are not evidence of the current deployed meter workflow.

### **4.9.3 Test execution status and commands**

The backend test branch defines the following commands:

```bash
npm run type-check
npm test
npm run test:integration
```

The `npm test` command runs the unit test files for load assessment, marketplace location rules and access-control middleware. The `npm run test:integration` command runs the Express API/functional test file.

**Table 4.6 Automated test execution record**

| Test group | Test cases defined in source | Execution result |
|---|---:|---|
| Load assessment unit tests | 6 | Not yet verified by recorded terminal/CI output |
| Marketplace unit tests | 9 | Not yet verified by recorded terminal/CI output |
| Security middleware unit tests | 3 | Not yet verified by recorded terminal/CI output |
| API/functional tests | 24 | Not yet verified by recorded terminal/CI output |
| **Total** | **42** | **No overall pass/fail total claimed** |

The table reports the number of test cases defined in the source files, not the number that have successfully passed. The actual pass and failure totals, test date and any error messages must be entered after the commands are executed in the backend environment. These automated software tests are separate from the physical tests of voltage, current, load response and relay operation reported earlier in this chapter.

## **4.10 Discussion of Results**

The combined-load test showed a clear change in displayed active power when the pressing iron's thermostat switched off its heating element. The meter displayed approximately 1.26 kW while the iron was heating and approximately 104 W after the heating element switched off, with the laptop charger remaining connected. This is evidence of functional response to a changing load.

The successful relay cut-off and reconnection test demonstrated the operation of the prepaid load-control mechanism. The exported consumption record demonstrated that the backend and web application could make a consumption value available for CSV export. Together, these observations support the conclusion that the hardware and software components provide the core functional behaviour intended for the prototype.

The results do not establish calibrated measurement accuracy, long-term reliability or performance under a range of solar operating conditions. Those claims require additional testing with reference instruments, multiple loads and an extended field evaluation.

## **4.11 Limitations of the Evaluation**

The evaluation was limited by the absence of a calibrated reference energy meter. Consequently, no percentage error or accuracy result is reported. The available CSV export contained one consumption record, which is insufficient to establish daily or monthly trends. The reported electrical tests were conducted using a single-phase AC supply rather than an extended field installation on a distributed solar system. Long-term relay endurance, extended network interruption and large-scale marketplace operation were also outside the available test evidence.

# **CHAPTER FIVE**

# **CONCLUSION AND RECOMMENDATIONS**

## **5.1 Conclusion**

This project presented the design and implementation of PAYGO, a smart prepaid energy metering and billing platform intended for small-scale distributed energy applications. The prototype integrates an ESP32-based metering unit, a PZEM-004T measurement module, local prepaid balance management, relay-based load control, HTTPS communication, a backend service, a PostgreSQL database and a web application.

The electrical load observations demonstrated that the meter display responded to changes in the connected load. During the combined-load test involving a pressing iron and a laptop charger, the displayed power decreased from approximately 1.26 kW to 104 W when the iron's thermostat switched off its heating element. The physical relay cut-off and reconnection test was successful. The consumption-reporting interface also generated a CSV record of 0.058 kWh dated 21 November 2026.

The project achieved functional integration of embedded metering, prepaid balance management, load control and web-based consumption reporting. However, the evaluation did not establish calibrated measurement accuracy because a reference energy meter was not available. The prototype should therefore be regarded as an engineering demonstration rather than a certified commercial metering product.

## **5.2 Recommendations**

The following improvements are recommended for future development:

1. **Measurement validation:** Test the PZEM-004T against a calibrated reference energy meter over several load levels and operating conditions. Record repeated readings and calculate percentage error.
2. **Extended load testing:** Evaluate the meter with resistive, inductive and electronic loads over longer operating periods.
3. **Solar field evaluation:** Install the prototype in a controlled distributed solar environment to evaluate its behaviour under actual inverter and battery operating conditions.
4. **Consumption data collection:** Collect readings over several days and weeks to evaluate reporting consistency and compare exported records with dashboard totals.
5. **Communication reliability:** Evaluate recovery after longer network interruptions and test balance synchronisation under repeated connectivity loss.
6. **Hardware improvement:** Review enclosure design, electrical isolation, protection, relay ratings, wiring and thermal performance before any field deployment.
7. **Security assessment:** Conduct a structured security review of device authentication, API access, payment processing and protection of user data.
8. **Marketplace development:** Extend the marketplace with stronger verification of energy availability, transaction reservation and settlement controls, and an appropriate regulatory review.

## **5.3 Contribution of the Project**

The project contributes an integrated prototype that combines local embedded energy measurement and prepaid load control with a web-based platform for payment processing, device management and consumption reporting. It also demonstrates how location-based listing discovery can be incorporated into a software platform intended for distributed energy applications.

The implementation provides a foundation for further engineering work on prepaid energy management in small-scale solar installations. Its main contribution is the integration and functional demonstration of the hardware and software subsystems, rather than the development of a certified meter or a commercially deployed electricity market.

- JORDAN, D. C., and KURTZ, S. R., ‘Photovoltaic Degradation Rates—an Analytical Review’, _Progress in Photovoltaics: Research and Applications_ , January 2013, Vol. 21, no. 1, pp. 12–29, doi: 10.1002/pip.1182. 

- STRAUB-MÜCK, M., GEYER-KLINGEBERG, J., and RATHGEBER, A. W., ‘Determinants of the long-term degradation rate of photovoltaic modules: A metaanalysis’, _Renewable and Sustainable Energy Reviews_ , July 2025, Vol. 216, p. 115697, doi: 10.1016/j.rser.2025.115697. 

- MONYEI, C. G., ADEWUMI, A. O., OBOLO, M. O., and SAJOU, B., ‘Nigeria’s energy poverty: Insights and implications for smart policies and framework towards a smart Nigeria electricity network’, _Renewable and Sustainable Energy Reviews_ , January 2018, Vol. 81, pp. 1582–1601, doi: 10.1016/j.rser.2017.05.237. 

- SOYEMI, A. O., SAMUEL, I. A., AYOBAMI, A. A. O., and AKINMEJI, A., ‘The Challenges of Estimated Billing on Electricity Consumers in Nigeria: A Review’, _IOP Conference Series: Earth and Environmental Science_ , April 2021, Vol. 730, no. 1, p. 012025, doi: 10.1088/1755-1315/730/1/012025. 

- MOHAMMED, Y. S., MUSTAFA, M. W., BASHIR, N., and MOKHTAR, A. S., ‘Renewable energy resources for distributed power generation in Nigeria: A review of the potential’, _Renewable and Sustainable Energy Reviews_ , June 2013, Vol. 22, pp. 257–268, doi: 10.1016/j.rser.2013.01.020. 

- CHANCHANGI, YUSUF. N., ADU, F., GHOSH, A., SUNDARAM, S., and MALLICK, TAPAS. K., ‘Nigeria’s energy review: Focusing on solar energy potential and penetration’, _Environment, Development and Sustainability_ , July 2023, Vol. 25, no. 7, pp. 5755–5796, doi: 10.1007/s10668-022-02308-4. 

- OLADIGBOLU, J. O., RAMLI, M. A. M., and AL-TURKI, Y. A., ‘Optimal Design of a Hybrid PV Solar/Micro-Hydro/Diesel/Battery Energy System for a Remote Rural Village under Tropical Climate Conditions’, _Electronics_ , September 2020, Vol. 9, no. 9, p. 1491, doi: 10.3390/electronics9091491. 

- OLATOMIWA, L., MEKHILEF, S., SHAMSHIRBAND, S., and PETKOVIĆ, D., ‘Adaptive neuro-fuzzy approach for solar radiation prediction in Nigeria’, _Renewable and Sustainable Energy Reviews_ , November 2015, Vol. 51, pp. 1784– 1791, doi: 10.1016/j.rser.2015.05.068. 

- REDDY, K. S., KUMAR, M., MALLICK, T. K., SHARON, H., and LOKESWARAN, S., ‘A review of Integration, Control, Communication and Metering (ICCM) of renewable energy based smart grid’, _Renewable and Sustainable Energy Reviews_ , October 2014, Vol. 38, pp. 180–192, doi: 10.1016/j.rser.2014.05.049. 

- SOTO, E. A., BOSMAN, L. B., WOLLEGA, E., and LEON-SALAS, W. D., ‘Peer-to-peer energy trading: A review of the literature’, _Applied Energy_ , February 2021, Vol. 283, p. 116268, doi: 10.1016/j.apenergy.2020.116268. 

47 

- BAIG, M. J. A., IQBAL, M. T., JAMIL, M., and KHAN, J., ‘Design and implementation of an open-Source IoT and blockchain-based peer-to-peer energy trading platform using ESP32-S2, Node-Red and, MQTT protocol’, _Energy Reports_ , November 2021, Vol. 7, pp. 5733–5746, doi: 10.1016/j.egyr.2021.08.190. 

- CHANCHANGI, YUSUF. N., ADU, F., GHOSH, A., SUNDARAM, S., and MALLICK, TAPAS. K., ‘Nigeria’s energy review: Focusing on solar energy potential and penetration’, _Environment, Development and Sustainability_ , July 2023b, Vol. 25, no. 7, pp. 5755–5796, doi: 10.1007/s10668-022-02308-4. 

- OLADIGBOLU, J. O., RAMLI, M. A. M., and AL-TURKI, Y. A., ‘Optimal Design of a Hybrid PV Solar/Micro-Hydro/Diesel/Battery Energy System for a Remote Rural Village under Tropical Climate Conditions’, _Electronics_ , September 2020b, Vol. 9, no. 9, p. 1491, doi: 10.3390/electronics9091491. 

- WIBOWO, L., WAHYUSARI, R., YUWONO, T., and SHOFIA, A., ‘IoT-based highaccuracy monitoring system for on-grid photovoltaic power system using NodeMCU ESP8266 and PZEM004T’, _Journal of Mechatronics, Electrical Power, and Vehicular Technology_ , December 2024, Vol. 15, no. 2, pp. 230–241, doi: 10.55981/j.mev.2024.823. 

- NUMMINEN, S., and LUND, P. D., ‘Evaluation of the reliability of solar micro-grids in emerging markets – Issues and solutions’, _Energy for Sustainable Development_ , February 2019, Vol. 48, pp. 34–42, doi: 10.1016/j.esd.2018.10.006. 

- MERGULHÃO, V. P., CAPRA, L., and PARIKH, P., ‘Solar home system payment patterns show intermittent access and late-term defaults in pay-as-you-go contracts’, _Communications Sustainability_ , September 2026, Vol. 1, no. 1, p. 150, doi: 10.1038/s44458-026-00121-y. 

- VETTER, J., NOVÁK, P., WAGNER, M. R., VEIT, C., MÖLLER, K.-C., BESENHARD, J. O., et al., ‘Ageing mechanisms in lithium-ion batteries’, _Journal of Power Sources_ , September 2005, Vol. 147, no. 1–2, pp. 269–281, doi: 10.1016/j.jpowsour.2005.01.006. 

- XU, B., OUDALOV, A., ULBIG, A., ANDERSSON, G., and KIRSCHEN, D. S., ‘Modeling of Lithium-Ion Battery Degradation for Cell Life Assessment’, _IEEE Transactions on Smart Grid_ , March 2018, Vol. 9, no. 2, pp. 1131–1140, doi: 10.1109/TSG.2016.2578950. 

- ROLFFS, P., OCKWELL, D., and BYRNE, R., ‘Beyond technology and finance: pay-asyou-go sustainable energy access and theories of social change’, _Environment and Planning A: Economy and Space_ , December 2015, Vol. 47, no. 12, pp. 2609–2627, doi: 10.1177/0308518X15615368. 

- YADAV, P., HEYNEN, A. P., and PALIT, D., ‘Pay-As-You-Go financing: A model for viable and widespread deployment of solar home systems in rural India’, _Energy for_ 

48 

_Sustainable Development_ , February 2019, Vol. 48, pp. 139–153, doi: 10.1016/j.esd.2018.12.005. 

- BARRY, M. S., and CRETI, A., ‘Pay-as-you-go contracts for electricity access: Bridging the “last mile” gap? A case study in Benin’, _Energy Economics_ , August 2020, Vol. 90, p. 104843, doi: 10.1016/j.eneco.2020.104843. 

- JACK, K., and SMITH, G., ‘Charging Ahead: Prepaid Metering, Electricity Use, and Utility Revenue’, _American Economic Journal: Applied Economics_ , April 2020, Vol. 12, no. 2, pp. 134–168, doi: 10.1257/app.20180155. 

- ALAO, K., JIMOH, K., and OBADIORA, A. J., ‘Evaluation of Customer Education and Satisfaction of Prepaid Meter Usage in Nigeria Electricity Distribution Company’, _Journal of Digital Learning and Education_ , April 2022, Vol. 2, no. 1, pp. 31–41, doi: 10.52562/jdle.v2i1.323. 

- QUAZI, I., GUPTA, S. K., and PRASAD, R., ‘Pre-paid Energy Meter based on AVR Microcontroller’, 2011, Available: https://api.semanticscholar.org/CorpusID:13446326. 

- RAJPUT, U. A., RAFIQUE, K., SATTAR, A., SHAIKH, M., and TARIQUE, M., ‘Modeling of Arduino-based Prepaid Energy Meter using GSM Technology’, _International Journal of Advanced Computer Science and Applications_ , 2018, Vol. 9, no. 5, doi: 10.14569/IJACSA.2018.090558. 

- IRIANTO, K. D., ‘Pre-SEMMS: A Design of Prepaid Smart Energy Meter Monitoring System for Household Uses Based on Internet of Things’, _Journal of Electronics, Electromedical Engineering, and Medical Informatics_ , March 2023, Vol. 5, no. 2, pp. 69–74, doi: 10.35882/jeeemi.v5i2.282. 

- RASHED MOHASSEL, R., FUNG, A., MOHAMMADI, F., and RAAHEMIFAR, K., ‘A survey on Advanced Metering Infrastructure’, _International Journal of Electrical Power & Energy Systems_ , December 2014, Vol. 63, pp. 473–484, doi: 10.1016/j.ijepes.2014.06.025. 

- CHEN, Z., AMANI, A. M., YU, X., and JALILI, M., ‘Control and Optimisation of Power Grids Using Smart Meter Data: A Review’, _Sensors_ , February 2023, Vol. 23, no. 4, p. 2118, doi: 10.3390/s23042118. 

- RIND, Y. M., RAZA, M. H., ZUBAIR, M., MEHMOOD, M. Q., and MASSOUD, Y., ‘Smart Energy Meters for Smart Grids, an Internet of Things Perspective’, _Energies_ , February 2023, Vol. 16, no. 4, p. 1974, doi: 10.3390/en16041974. 

- ABED, I. A., and NASER, H. Y., ‘ESP32 Microcontroller Based Smart Power Meter System Design and Implementation’, _Al-Rafidain Engineering Journal (AREJ)_ , December 2020, Vol. 25, no. 2, pp. 136–143, doi: 10.33899/rengj.2020.127111.1038. 

49 

- WAN, L., ZHANG, Z., and WANG, J., ‘Demonstrability of Narrowband Internet of Things technology in advanced metering infrastructure’, _EURASIP Journal on Wireless Communications and Networking_ , December 2019, Vol. 2019, no. 1, p. 2, doi: 10.1186/s13638-018-1323-y. 

- DEPURU, S. S. S. R., WANG, L., and DEVABHAKTUNI, V., ‘Electricity theft: Overview, issues, prevention and a smart meter based approach to control theft’, _Energy Policy_ , February 2011, Vol. 39, no. 2, pp. 1007–1015, doi: 10.1016/j.enpol.2010.11.037. 

- T. E, S., C.O.A, A., and A., C., ‘Smart prepaid energy metering system to detect energy theft with facility for real time monitoring’, _International Journal of Electrical and Computer Engineering (IJECE)_ , October 2019, Vol. 9, no. 5, p. 4184, doi: 10.11591/ijece.v9i5.pp4184-4191. 

- VARELA-ALDÁS, J., SILVA, S., and PALACIOS-NAVARRO, G., ‘IoT-Based Alternating Current Electrical Parameters Monitoring System’, _Energies_ , September 2022, Vol. 15, no. 18, p. 6637, doi: 10.3390/en15186637. 

- EL-KHOZONDAR, H. J., MTAIR, S. Y., QOFFA, K. O., QASEM, O. I., MUNYARAWI, A. H., NASSAR, Y. F., et al., ‘A smart energy monitoring system using ESP32 microcontroller’, _e-Prime - Advances in Electrical Engineering, Electronics and Energy_ , September 2024, Vol. 9, p. 100666, doi: 10.1016/j.prime.2024.100666. 

- YASA, K. A., PURBHAWA, I. M., YASA, I. M. S., TERESNA, I. W., NUGROHO, A., and WINARDI, S., ‘IoT-based Electrical Power Recording using ESP32 and PZEM-004T Microcontrollers’, _Journal of Computer Science and Technology Studies_ , November 2023, Vol. 5, no. 4, pp. 62–68, doi: 10.32996/jcsts.2023.5.4.7. 

- URREA, C., and MORALES, C., ‘Enhancing Modbus-RTU Communications for Smart Metering in Building Energy Management Systems’, _Security and Communication Networks_ , November 2019, Vol. 2019, pp. 1–8, doi: 10.1155/2019/7010717. 

- OASIS, _MQTT Version 3.1.1_ , October 2014, Available: https://docs.oasis-open.org/mqtt/mqtt/v3.1.1/os/mqtt-v3.1.1-os.html. 

- ARBAB-ZAVAR, B., PALACIOS-GARCIA, E. J., VASQUEZ, J. C., and GUERRERO, J. M., ‘Message Queuing Telemetry Transport Communication Infrastructure for GridConnected AC Microgrids Management’, _Energies_ , September 2021, Vol. 14, no. 18, p. 5610, doi: 10.3390/en14185610. 

- MANOWSKA, A., WYCISK, A., NOWROT, A., and PIELOT, J., ‘The Use of the MQTT Protocol in Measurement, Monitoring and Control Systems as Part of the Implementation of Energy Management Systems’, _Electronics_ , December 2022, Vol. 12, no. 1, p. 17, doi: 10.3390/electronics12010017. 

- YUNARDI, E., MAGDALENA, L., and MESI FEBIMA, ‘Implementation of the Haversine Formula Method in Geographic Information Systems for Searching the Nearest Sea 

50 

Freight Expedition Services in East Jakarta’, _Journal of Artificial Intelligence and Engineering Applications (JAIEA)_ , October 2024, Vol. 4, no. 1, pp. 283–288, doi: 10.59934/jaiea.v4i1.622. 

- MUTTAQIN, A., MURTOPO, A. A., SYEFUDIN, S., and GUNAWAN, G., ‘Application of the haversine formula method to determine the closest distance to a minimarket’, _Jurnal Mandiri IT_ , June 2024, Vol. 13, no. 1, pp. 72–80, doi: 10.35335/mandiri.v13i1.293. 

- FEDERAL REPUBLIC OF NIGERIA, _Electricity Act 2023_ , Abuja, Nigeria: Federal Government Printer, 2023, Available: https://placng.org. 

- NIGERIAN ELECTRICITY REGULATORY COMMISSION, _Mini-Grid Regulations, 2026_ , 2026, Available: https://nerc.gov.ng. 

51 

