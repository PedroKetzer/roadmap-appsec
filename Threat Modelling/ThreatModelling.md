##### 💡 All of the following course/content suggestions are free, except those marked with 💰

# Threat Modeling
Threat modeling in the context of Application Security is essential for anticipating and addressing potential vulnerabilities in systems. By identifying threats before they become real attacks, security professionals can develop preventative strategies, strengthening application security. This proactive approach not only improves the resilience of systems, but also promotes a culture of security from the earliest stages of application development.
To learn about modeling, see:
- [What is Threat Modeling and Why Is It Important?](https://www.youtube.com/watch?v=h_BC6QMWDbA)
- [How to do Real World Threat Modeling](https://youtu.be/fggB70PxhmA?si=4PQVB-QhpKWeYs8u)
- [Threat Modeling Lab | Security Threat Modeling Workshop](https://www.youtube.com/watch?v=oioLnkQeVek)
- [OWASP Threat Modeling Process](https://owasp.org/www-community/Threat_Modeling_Process)
- [OWASP Threat Dragon](https://owasp.org/www-project-threat-dragon/)
- [IriusRisk DeRisker Training Program](https://www.iriusrisk.com/derisker-training-and-certification)
- [Threat Modeling Security Fundamentals - Microsoft](https://learn.microsoft.com/en-us/training/paths/tm-threat-modeling-fundamentals/)
- [Maturing Your Threat Modeling Skills - Semgrep](https://www.youtube.com/watch?v=2zxYPwpPVis)

# The first steps in modeling

Threat modeling is a process used in the field of information security to identify and understand potential threats and vulnerabilities to a system, application or project. Abstract, I would say, isn't it? Understand that in addition to security, you must be able to talk about the business as well as its peculiarities, from what a happy user path is expected to possible exploit attempts, malicious scenarios, everything that will be offensive to your performance.

## Looking at the whole

When we talk about Shift Left, the idea of anticipating problems, reducing costs and the values employed in the concept is very nice, but how?
Let's assume that you know about system architecture, REST Api and the like. If you don't, here are some links to help you.

First of all, it's important to understand the construction of a system on a "piece of bread": who communicates with what? How? What for? So I've drawn up a roadmap of basic questions so that you can internalize the context and be able to use them to create many, many others about the product.

1. Could you give me a summary of the purpose of the application?
2. Will it be displayed on the internet or only internally?
3. Who will use the application? Internal services, ordinary users, internal users?
4. What type of data is in transit? Card data? Personal information? System information? Transactions?
5. Will data be stored? Where?

From these points you can visualize and even draft an architecture of pipelines and filters where it will be possible to both structure who or what performs the action and which action for a specific purpose. Complex? Let's break down a basic example.


## About the Application

1. **Purpose of the application**
   - The application allows third parties from other companies to record customer service information via a website during field visits. This helps to check whether calls are being resolved on the spot or whether there are recurrences.

2. **Access and exposure**
   - The application will be available on the Internet to third parties, but our team will have access for monitoring purposes.

3. **Application Consumers**
   - The main consumers will be third-party users of a contracted company (Company X) and internal users of our organization.

4. **Data in Transit and Storage**
   - Data in transit includes personal customer information (name, telephone number, service address, problem summary and resolution), as well as data on the technicians responsible. All will be stored in our cloud database.

5. **Available Services**
   - We will have a BFF (Backend For Frontend) and a microservice. The BFF will receive information, while the microservice will be responsible for publishing it in the database.

## Pipeline and filter architecture

Based only on the comments we have:

![Draft Architecture Drawing](https://github.com/PedroKetzer/roadmap-appsecbr/assets/37319386/6d91a609-1b47-4c96-aa51-c274bfabfb3c)


## Survey of problems

From this start you could visualize some problems, such as:
How is the exhibition of this BFF going to be carried out?
How will these users be governed if we have internal and external people? Who or what will create users?
This service will record information in a database, it's personal data, so what is the LGPD about this? How long will they keep this information? Did the customer authorize it?
How will this service be published? Will they have to correlate it to a call source?
Will they send a file or will it be a form?
If they want to link repeat offenses, who will use the information in the database?
If only the attendant is going to interact on the site, why do internal users need to access it?

Numerous doubts arise and can be resolved later, but what if the team needs a minimum of guidance to understand what they can and can't do? Or if nothing is ready yet, because in the Shift Left model there is an anticipation of problems, so it should be able to raise points before even an architectural design is completed, or not necessarily?

It depends.
It depends on the size of the company, the size of the team, the maturity of the team about the company itself and how it works, in short, many variables. That's why AppSec (or any other name the company may use for this activity) needs to understand the business very well, the corporate ecosystem and its peculiarities, as well as the architecture and tools available for its operation.

## Surveying threats

Threats could, in a superficial view, be reduced to 3 types of possibilities, such as:

![Threats of the Draft Architecture](https://github.com/PedroKetzer/roadmap-appsecbr/assets/37319386/f5a94642-995c-4e17-8484-93f06ede0284)



--
Next: [Next steps under construction and will be linked here]