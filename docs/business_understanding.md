# Business Understanding

## Introduction
In this section, we will explore the business understanding phase of a data science project. This phase is crucial as it sets the foundation for the entire project by defining the problem, understanding the objectives, and identifying the key stakeholders.

## Market Research
**•	What image classifier product or product feature could make organizational life easier?**

The indoor plant market is experiencing a rapid surge in popularity, gaining increased attention from consumers. Indoor plants serve multifaceted purposes, ranging from enhancing aesthetic appeal and infusing spaces with vitality to contributing to improved air quality. With millions of plant shops competing for consumer attention, distinguishing oneself from the competition can be a daunting task.

To address the challenge of standing out in the rapidly growing market, businesses can leverage a plant image classifier as a unique product feature. This classifier would allow customers to easily identify different types of indoor plants, enhancing their shopping experience and enabling them to make informed choices. By integrating this technology, businesses can distinguish themselves from competitors and offer enhanced customer service, ultimately improving their market position and driving growth within the organization. It can significantly improve organizational efficiency, customer satisfaction, and decision-making processes, ultimately making life easier for both customers and staff alike.

**•	How can I improve work within an organization?**

A user-friendly and informative plant image classifier can help drive sales by empowering customers to make informed purchasing decisions. Many customers may have questions about the plants they consider purchasing, such as care requirements and ideal growing conditions. The plant image classifier can provide instant answers to these inquiries, reducing the need for customers to reach out for assistance. This reduces the burden on customer service representatives and other employees who may have otherwise been tasked with responding to customer inquiries. Enabling employees to focus on higher-value tasks, leading to improved operational efficiency and productivity within the organization.

Furthermore, by providing this tool, the organization demonstrates its commitment to customer satisfaction and provides a valuable resource for plant enthusiasts. This fosters customer loyalty, as it enhances the overall experience and support for those passionate about plants. 

**•	What problem can I alleviate for an organization?**

By integrating a plant image identifier, an organization can effectively distinguish itself in a competitive market, showcasing innovation and a strong focus on customer needs and preferences. This unique feature not only sets the organization apart from competitors but also strengthens brand recognition and creates customer loyalty. With the plant image classifier integrated into the organization's website or mobile app, customers enjoy a more interactive and convenient shopping experience, further enhancing their satisfaction and affinity towards the brand.


## Stakeholder Analysis
__1. Characteristics__

•	Botanical research and plant education organizations

>Botanical research and plant education organizations wield significant power and influence in the botanical community. Their expectations include innovative approaches to research, education, and community engagement. Botanical research and plant education organizations require access to accurate botanical data, research tools, and educational resources, preferring platforms and networks that facilitate knowledge-sharing, research collaborations, and outreach activities.

*Expectations:*\
Expect reliable and scientifically accurate plant classification results from the image classifier.

*Needs:*\
Require a robust classifier that can accurately identify various plant species, potentially with features for species rarity or conservation status.

*Preferences:*\
Prefer a classifier that can provide additional information such as botanical names, habitat preferences, and ecological significance.

•	Plant shops

>They hold power as primary points of contact for plant enthusiasts and customers. Their influence lies in shaping trends in plant cultivation and sales. With a keen interest in satisfying customer demands and promoting plant appreciation, they expect reliable access to diverse plant species and accurate information about plant care.

*Expectations:*\
Expect a user-friendly image classifier that can quickly identify popular plant species to assist in inventory management and customer inquiries.

*Needs:*\
Require a classifier that can handle a wide variety of plant species commonly found in their inventory.

*Preferences:*\
Prefer a classifier with a simple interface and fast processing speed.

•	Customers/Consumers

>These stakeholders have powers that lie in their collective passion for plants and their active engagement in citizen science initiatives and community outreach programs. With a deep interest in plants, species diversity, and conservation, they expect access to accurate plant information, resources for plant care, and opportunities for plant-related activities. Their preferences include engaging social platforms for knowledge-sharing, access to plant communities, and participation in plant-related events and workshops.

*Expectations:*\
Expect an accessible and informative image classifier that can help them identify plants they encounter in their hobbyist endeavors.

*Needs:*\
Require a classifier that is easy to use, provides accurate results, and offers additional educational resources.

*Preferences:*\
Prefer a classifier with a user-friendly mobile app interface, the ability to save and share identified plants, and access to plant tips.

•	IT department

>Their power lies in managing technological infrastructure and systems within organizations. Their influence extends to streamlining processes, ensuring data security, and facilitating communication and collaboration. With an interest in optimizing technological solutions for organizational needs, they expect clear communication channels, reliable support, and alignment of technology with organizational goals. Their needs include robust IT systems, cybersecurity measures, and integration of technologies for efficient operations. 

*Expectations:*\
Expect a well-documented and scalable solution that can be easily integrated into existing IT infrastructure.

*Needs:*\
Require a classifier with clear documentation, support for deployment on various platforms, and compatibility with existing security protocols.

*Preferences:*\
Prefer a classifier that follows best practices in software development, such as modular design, version control, and compatibility with common programming languages and frameworks.

__2. Prioritization__

#### Botanical research and plant education organizations:
| Power | Interest |
|----------|----------|
| High | High |
They possess authority and expertise in botanical research and education.|They are deeply invested in advancing botanical knowledge and promoting plant education.

#### Plant shops:
| Power | Interest |
|----------|----------|
| Medium | High |
They influence the local plant market and supply chain.|Their business relies on selling plants and meeting customer demands.

#### Customers / Consumers:
| Power | Interest |
|----------|----------|
| High | High |
Individually low, but collectively high as their demand drives the app's success.|They are passionate about plants and actively engage in plant-related activities.

#### IT department:
| Power | Interest |
|----------|----------|
| Low to Medium  | Medium |
| They manage technological infrastructure but do not have direct influence over plant-related decisions.|They are interested in supporting the project's technological aspects.

Based on the Power and Interest grid matrix:

*High Power, High Interest:*\
Botanical research and customers/consumers.

*Medium Power, High Interest:*\
Plant shops.

*Low to Medium Power, Medium Interest:*\
IT department.


__3. Main stakeholder__

The main stakeholders identified are botanical research centers, plant shops and customers/consumers. This decision is based on their high power and interest in the plant identifying application. Plant shops are pivotal in facilitating access to indoor plants for consumers, while botanical research organizations possess specialized knowledge essential for the project's success.

Engaging closely with these stakeholders is crucial as they wield significant authority and expertise in the domain, thus influencing the project's direction and outcomes. Their deep interest in advancing botanical knowledge and promoting plant education aligns closely with the project's objectives. 

Amateur botanists and plant hobbyists also hold substantial interest and influence in the project, given their passion for plants and active engagement in plant-related activities. However, their power might be relatively lower in terms of institutional authority compared to the aforementioned stakeholders.

While the IT department plays a crucial role in managing technological infrastructure, their power and interest may be comparatively lower in the context of the project's core objectives. Nevertheless, their involvement remains important for supporting the project's technological aspects and ensuring seamless integration of IT systems.

In summary, prioritizing engagement with plant shops, customers/consumers and botanical research is the primary decision-making context. Their collective power and interest make them key drivers in shaping the project's success and fostering widespread adoption and impact within the botanical community and beyond.

## DAPS Diagram
![DAPS Diagram ](/images/DAPS_Diagram.png)

__1. The data-analytic problem__

What are the potential predictors, features?
The potential predictors and features include; the plant leafs, shape, width height, and color

__2. The decision framework__

The model will be used to make decisions related to plant identification and provide relevant information to users on how to care for the identified plant species. This includes decisions such as accurately identifying the plant species from user-submitted images, retrieving care instructions specific to each identified species, and presenting the information in a user-friendly application. These decisions are primarily taken by the algorithm within the app. The algorithm analyzes the images that are submitted and makes decisions based on features extracted from the image to determine the plant species. Additionally, the shop owner may curate the information, through developers, to match the shop's offerings.
The algorithm processes user-submitted images in real time to identify plant species and provide species-specific care instructions. Interventions refine algorithms and expand care database for accuracy and comprehensiveness.


__3. The business value__

Implementing this application will provide significant value to the business, giving them a competitive edge in the market. This, in turn, leads to increased customer satisfaction, which ultimately translates to higher profitability. Additionally, this application leads to the automation of certain processes, as customers are less likely to need assistance from an employee. This improves organizational efficiency by reducing the number of inquiries that employees have to handle, allowing them to focus on more important tasks.