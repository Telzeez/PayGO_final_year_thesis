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

The aim of this project is to design and construct a smart prepaid solar energy metering and billing platform for small-scale residential energy sharing, integrating electrical energy measurement, prepaid credit management, automated load control, IoT communication, digital payment and location-aware energy discovery. 

The specific objectives of the project are to: 

1. Design and implement an embedded prepaid smart metering unit using the PZEM-004T sensor module, ESP32 microcontroller, and automated relay control to measure single-phase electrical parameters, deduct consumed energy credit in real time, and automatically disconnect or reconnect the load based on available balance. 

2. Establish bidirectional wireless communication between the embedded metering device and a cloud backend to transmit real-time energy consumption data and execute authorised remote control commands. 

3. Develop a web-based energy management and location-aware marketplace platform that supports digital credit recharge, user and transaction management, energy data visualisation, and identification of nearby listed energy sources using geographical coordinates and the Haversine formula. 

4. Evaluate the integrated system through component-level, integration, and operational testing to validate its metering accuracy, prepaid billing, load switching, communication reliability, and web platform performance 

6 

# **1.4 Significance of the Study** 

The significance of this study lies in its contribution to embedded energy management, prepaid electricity access, and the sustainable utilization of small-scale solar installations. The research is justified by the growing need for efficient management of decentralized renewable energy systems, particularly in enabling small-scale solar owners to systematically recover operational and maintenance costs through metered energy sharing. For solar energy system owners, the Pay-As-You-Go (PAYGO) architecture provides a reliable mechanism for measuring, recording, and billing electricity supplied to third-party consumers based on actual consumption. By establishing an automated, consumption-based revenue model, the system generates financial returns that help offset battery replacement, maintenance, and operating expenses, thereby promoting the long-term sustainability of decentralized solar installations. 

For electricity consumers, the platform offers a transparent prepaid model in which energy access is directly tied to an active credit balance. Real-time tracking of energy consumption and remaining credit promotes conscious energy usage while ensuring fair, verifiable billing based on accurately recorded kilowatt-hour (kWh) consumption. 

For engineering practice, this project demonstrates the end-to-end integration of electrical parameter sensing, embedded control, relay-based load switching, Internet of Things (IoT) telemetry, digital payment processing, and web-based monitoring within a unified prototype. Utilizing an ESP32 microcontroller alongside a PZEM-004T energy monitoring module provides a cost-effective framework for automated prepaid load control. Furthermore, incorporating a location-aware software marketplace establishes a practical testbed for 

7 

evaluating the technical requirements of localized energy discovery and small-scale energy distribution. 

For future research, the developed prototype serves as a foundational platform for advancing studies in smart metering, decentralized peer-to-peer (P2P) energy trading, cryptographic device security, automated payment gateways, and the regulatory frameworks governing local microgrids. 

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

The requirements were derived from the objectives of the project and the intended use in a small solar energy-sharing setting. They are summarised in Table 3.1. 

Table 3.1 Functional and non-functional requirements of the PAYGO system 

|**Type**|**Requirement**|
|---|---|
|Functional|Register and authenticate users; register and manage metering devices;<br>measure the AC energy consumed by the connected load; maintain the|
||available energy balance of each device; control the load according to<br>that balance.|
|Functional|Accept digital payments; convert each verified payment into energy<br>credit; record every transaction; send the credit to the physical meter and<br>confirm that the meter accepted it; retry credit operations that could not|
||be delivered.|
|Functional|Monitor whether each device is online; present transaction information to<br>users.|
|Functional|Allow energy owners to list available energy; find listings near a buyer|
||using geographical distance; process purchases from listings.|



30 

|**Type**|**Requirement**|
|---|---|
|Non-functional|Transaction integrity and prevention of duplicate processing; verification|
||of payment notifications; reliable device communication; separation of|
||money from energy quantities; modular and maintainable software;|
||usability on mobile and desktop devices.|



# **3.4 Overall System Architecture** 

The architecture is shown in Figure 3.1. It has a physical and device layer, a communication layer, a backend layer, a data and external-services layer and a presentation layer. 

31 



<!-- Start of picture text -->
Next.js web application<br>(PWA)<br>{ HTTPS REST API<br>Express / TypeScript backend<br>PAYGO meter Authentication<br>ESP32 firmware HTIPS over Wi-Fi Devices and balances<br>(device API) .<br>PZEM-004T measurement Payments and transactions<br>Prepaid balance Marketplace<br>Relay load control<br>Displayi heartbeat,‘acknowledgementbalance sync,<br>SQL API +fo<br>_<br><!-- End of picture text -->

Figure 3.1 Architecture of the PAYGO system The device layer is the PAYGO meter, which contains the ESP32 controller, the PZEM-004T measurement module, the relay and a display. The meter is placed downstream of the owner’s solar system, so it measures only the AC electricity delivered to the consumer’s load. The communication layer uses HTTPS between the meter and the backend. The device API carries the heartbeat, the synchronisation of the device balance and the other device operations, such as acknowledgements, energy reports, and retrieval of the device profile. 

32 

The backend is built with Node.js, Express and TypeScript. It coordinates authentication, devices, payments, transactions, the marketplace and device communication. It stores its records in a PostgreSQL database and works with two external services: Paystack for payments. The presentation layer is a Next.js progressive web application. It communicates only with the backend through its REST API and never connects directly to the database, or the meter. 

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

The ESP32 requests measurements from the PZEM-004T over its UART interface using the Modbus-RTU protocol (Abed, 2020). Active power, energy and the related quantities follow Equations (2.1) to (2.3). The accumulated energy is converted to kilowatt-hours for the billing process. The accuracy of the measurements is not assumed and is evaluated against a reference instrument as described in Section 3.13. 

# **3.6 Embedded Firmware Design** 

The firmware runs on the ESP32 and performs five tasks. It reads the PZEM-004T, maintains the local energy balance, controls the relay, handles credit commands from the backend and 

36 

communicates with the backend. Each meter has a unique device identifier, device_id, which the backend uses to link the meter to its balance, transactions and connection status. 

The meter holds the available energy balance in kilowatt-hours. When energy is consumed it is deducted locally, and when credit is received it is added. The new balance is: 



where _Bnew_ is the new balance, _B prev_ is the previous balance, _E purchased_ is newly purchased energy and _Econsumed_ is the measured consumption. The relay follows the balance: the load is on while credit is available and is switched off when the balance is exhausted. 

When a credit instruction is received, the firmware checks that it is valid and whether its transaction identifier has already been processed. A transaction that has already been processed is not credited again. Otherwise the credit is applied and an acknowledgement is returned to the backend. The firmware also sends a regular heartbeat to the backend over HTTPS and reports the remaining balance so that the backend and the web application show the current state of the meter. 

# **3.7 Backend Design and Implementation** 

The backend uses Express 5 with TypeScript on Node.js and connects to PostgreSQL through the pg connection pool. The code is organised into routes, middleware, services and supporting modules, so that request handling is separate from business logic and from communication with other systems. The API has separate route groups for authentication, payments, the Paystack webhook, devices, transactions and the marketplace. 

Authentication is provided by dedicated routes for registration, login, retrieval of the signedin user and logout. An authentication middleware and role guards protect the device, 

37 

transaction and marketplace operations, so that they cannot be performed without a valid authenticated user. 

PostgreSQL stores the persistent records. The devices table holds the device identifier, the current balance in kilowatt-hours, the connection status, the time the device was last seen and the time of the last balance update. The transactions table is the authoritative record of payments, energy quantities and hardware execution. It holds the transaction type, the amount paid in naira, the energy in kilowatt-hours, an internal transaction identifier, the Paystack reference, the hardware status, a retry count, the time of the last attempt and a timestamp. Further tables hold the marketplace records. 

# **3.8 Payment and Prepaid Credit Management** 

The payment and recharge workflow is shown in Figure 3.5. It runs from payment initiation, through Paystack and verification of the webhook, to a database transaction, the energycredit calculation, the credit command to the meter and the acknowledgement from the meter. 

38 



<!-- Start of picture text -->
webBuyer/app Backend Paystack PostgreSQL ESP32meter<br>1. initiate payment | H i<br>om | H H<br>| ainiise | 1<br>—— H<br>| 3.signed webhook | H<br>itm ——— H<br>4. verify HMAC-SHAS12;| i H<br>check unique reference Hl i<br>' 5. commit credit and record '<br>rr<br>' 6. credit command (TXN id, kWh)<br>H ' Hl 7. skip if TXN processed;<br>i i i apply credit<br>' | B.acknowledgement |<br>i¢ T T<br>' 9, hardware_status = CONFIRMED '<br>ee ll<br><!-- End of picture text -->

Figure 3.5 Sequence of payment, credit allocation and hardware acknowledgement 

The user starts a payment from the web application, which calls the payment route of the backend. The backend initialises the transaction with Paystack and returns the payment details to the application. When the payment is completed, Paystack sends a notification to the webhook endpoint of the backend. 

Several design decisions protect the integrity of this process. The first is verification of the webhook. The backend reads the raw request body and validates the HMAC-SHA512 

39 

signature before it processes the event, so that a fabricated payment notification is rejected. The second is idempotency. A webhook may be delivered more than once, so the reference field of the transactions table carries a unique constraint, and an event whose reference is already recorded is ignored. The third is the separation of money from energy. The amount paid in naira and the energy purchased in kilowatt-hours are stored in separate fields. The energy credited for a payment is: 



where _EkWh_ is the energy in kilowatt-hours, _A_ is the amount paid in naira and _p_ is the configured price per kilowatt-hour. Keeping the two quantities apart prevents a monetary amount from being mistaken for an energy quantity, and allows the tariff to change without changing the measurement subsystem. 

A verified payment is handled in one database transaction. The transaction adds the energy to the device balance, records the payment with an internal transaction identifier of the form TXN_XXXXXXXX and a hardware status of PENDING. Only after this transaction has been committed does the backend send the credit command to the meter. The database is therefore the primary record of the payment, and the command to the meter is not. The transaction identifier is carried in the command and returned in the acknowledgement, which links the payment, the database record and the hardware operation. 

The hardware status separates the success of the payment from the success of the physical credit. Its three states are described in Table 3.2. 

40 

Table 3.2 Hardware execution states of a credit transaction 

|**State**|**Meaning**|
|---|---|
|PENDING|The payment and credit transaction exist but the meter has not yet<br>confirmed the credit.|
|CONFIRMED|The ESP32 has acknowledged that the credit was processed.|
|FAILED|The hardware credit operation did not succeed after the defined retry<br>conditions.|



# **3.9 Device Communication and Remote Recharge** 

A credit command tells the meter how much energy to add and carries the transaction identifier. The meter acts on it as described in Section 3.6 and returns an acknowledgement. When the backend receives the acknowledgement, it changes the hardware status of the transaction from PENDING to CONFIRMED. The backend records a device as ONLINE or OFFLINE according to the heartbeat messages it receives, and updates the last-seen time when a valid heartbeat arrives. The device API is the HTTPS interface through which the meter reports its heartbeat, balance, energy and acknowledgements and obtains its profile. If the meter is offline, the transaction stays in the PENDING state and is not treated as failed. The backend retries pending credit commands when the device reconnects or sends a heartbeat. A minimum interval, based on the time of the last attempt, prevents repeated retransmission. A transaction becomes FAILED only if the physical credit still does not succeed after the defined retry conditions. 

# **3.10 Local Energy Marketplace** 

The marketplace lets energy owners offer energy and lets buyers find offers near them. An energy source is the supplier’s physical energy resource, while an energy listing is a quantity of energy from that source that is offered for sale. A listing holds the available energy in 

41 

kilowatt-hours, the price per kilowatt-hour, a status of ACTIVE or PAUSED, and a link to its source. Separating the two allows a source to remain registered while its listing is paused. The process is shown in the flow diagram in figure 3.6 below: 



<!-- Start of picture text -->
Energy owner registers an energy source<br>Owner publishes a listing<br>(available energy, price, service radius)<br>Buyer supplies a location<br>Backend calculates distance d to each<br>listing using the Haversine formula<br>Isd<r No Listing is<br>Eligible listings(service radius)?are presented to the buyer= excluded<br>makeDoesathepurchase? buyer Ne° End<br>Yes<br>Backend reserves the requested energy<br>using a reserved_kwh lock<br><!-- End of picture text -->

Figure 3.6 Flowchart of the marketplace discovery and purchase process 

42 

_d ≤r_ 

(3.3) 

The distance test shows only that a listing lies within the configured service radius. It does not show that energy is physically available. The available energy of a listing is a figure published by the owner, and the marketplace in this project is a prototype discovery and purchase feature and not an established energy-trading service. 

# **3.11 Web Application Design** 

The user interface is a Next.js progressive web application that can be used on mobile and desktop devices. It sends all requests to the Express REST API and has no direct access to the database. This keeps the interface independent of the way the devices are implemented. The application supports registration and login, the viewing of device information and balance, payment initiation, the transaction history, and the discovery and purchase of marketplace listings. 

# **3.12 System Integration** 

The subsystems are integrated in stages. The ESP32 is first connected to the PZEM-004T and the relay to form the measuring and load-control unit. The firmware is then connected to the backend, with HTTPS for the heartbeat, the balance synchronisation, credit acknowledgements and the other device operations. The backend is next connected to Paystack for payment initiation and webhook processing, and to the database for the persistent records. The web application is connected through the REST API. Finally, the complete workflow is run from payment to the acknowledged credit at the meter, as shown in Figure 3.5. The status of each stage and the problems found are reported in Chapter Four. 

43 

**Table 3.3** Test plan for the PAYGO system 

|**Test**|**Procedure**|**Metric or expected outcome**|
|---|---|---|
|Energy measurement|Connect loads of varying power levels.<br>Record the PZEM-004T readings and the<br>reference instrument readings<br>simultaneously, repeating each<br>measurement.|Percentage error and mean of<br>voltage, current, power and<br>energy readings|
|Prepaid credit|Add a known amount of energy to the<br>balance, operate a load and observe the<br>balance decrement.|Balance follows Equation (3.1)<br>within measurement error limits|
|Load control|Operate a load with available credit until the<br>credit is exhausted, then recharge the<br>balance.|Relay remains on while credit is<br>available, switches off when<br>exhausted and switches back on<br>after recharge|
|Payment processing|Submit valid payment webhook events with<br>a valid signature, alongside events with an<br>invalid signature.|Valid events generate a<br>transaction and the<br>corresponding energy credit;<br>invalid events are rejected|
|Credit command and<br>acknowledgement|Issue a credit command and observe delivery<br>to the meter and its acknowledgement<br>response.|Transaction status updates from<br>'PENDING' to 'CONFIRMED';<br>confirmation rate calculated via<br>Equation (3.6)|
|Duplicate prevention|Submit the same payment reference multiple<br>times and resend the same transaction<br>identifier to the meter.|Energy credit is applied once<br>only|
||Disconnect the meter from the network,|Transaction remains 'PENDING'<br>|
|Device reconnection|<br>initiate a payment and subsequently<br>reconnect the meter.|while offline and updates to<br>'CONFIRMED' upon<br>reconnection|
|Marketplace|Create energy sources and listings, supply<br>buyer coordinates inside and outside service<br>radii and attempt concurrent purchases.|Only listings satisfying d ≤ r are<br>returned; reserved energy is not<br>double-sold|
||Execute the complete sequence from|Payment record, database|
|Integrated workflow|payment initiation to credit|balance, meter balance and|
||acknowledgement and load actuation.|device status remain consistent|



# **3.13 Performance Evaluation and Data Analysis** 

Measurements are analysed using the percentage error and the mean. For a measured 

quantity _X m_ and a reference quantity _X r_ , the percentage error is: 

44 



and for n repeated observations x_i the mean is: 



The functional tests are judged by whether the expected system state is reached. A remote recharge is successful when the payment is verified, the database is credited, the command is delivered, the acknowledgement is received, the status becomes CONFIRMED and no duplicate credit is created. The share of credit operations that reach the confirmed state is expressed as: 



The recovery after reconnection, the handling of duplicates and the identification of listings within a service radius are judged as passed or failed against the outcomes in Table 3.3. 

# **3.14 Security and Reliability Considerations** 

The backend uses several security mechanisms. Payment notifications are verified with HMAC-SHA512 signatures. Protected operations require authentication and role checks. Reliability measures are built into the design. A unique payment reference and a unique transaction identifier prevent duplicate credit at the backend, and the meter independently ignores a transaction it has already processed. The credit is committed to the database before the command is sent. The PENDING, CONFIRMED and FAILED states record what actually happened at the hardware, retries recover credit for meters that were offline, These mechanisms are examined in the tests above. The project does not include a full security audit, and no claim is made beyond the behaviour observed in those tests. 

45 

# **3.15 Methodological Limitations** 

The prototype is small in scale and does not represent a utility metering infrastructure. The measurement performance depends on the PZEM-004T, the installation and the reference instrument used. The experiments use the grid as the AC source, so the behaviour of the meter on a particular solar installation is not examined. The marketplace provides discovery by distance and purchase from listings and is not an electricity-market clearing mechanism. Device communication depends on network availability, and retries improve recovery but cannot remove this dependence. The prototype demonstrates technical integration and function. It does not establish regulatory approval, commercial viability or long-term field performance. 

46 

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

