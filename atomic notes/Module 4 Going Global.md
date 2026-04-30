---
tags:
  - aws
---


# Увод
Различни локации имат различни рестрикции и различни цени. Но за да имаш глобализиран софтуер ти се налага твоят продукт да е колкото се може по-близо до потребителя. От гледна точка на договори за продукта или за бързина на изпълнението или разлики в задоволството на дадената държава. 
Това е постижимо с edge locations за по малки и по-бавни но по-евтини и покриващи по широк регион. И всичкото това как се реализира чрез [[AWS CloudFormation]].

## AWS Regions
Regions are geographical areas around the world that are made up of multiple data centers. These data centers provide scalable and redundant infrastructure for hosting cloud services. Each Region consists of multiple, isolated locations known as Availability Zones. Each Region has three or more Availability Zones.

## Availability Zones
Availability Zones are distinct locations within a Region, each designed as an independent zone with its own power, networking, and connectivity. Availability Zones maintain high availability and fault tolerance for applications. Each Availability Zones consists of one or more data centers.

## Edge locations
Edge locations are strategically placed sites around the world that cache content to deliver data, video, and applications with lower latency and higher transfer speeds. Edge locations are considered a vital part of the AWS content delivery network (CDN) and use services like CloudFront to efficiently distribute data to end users.

# How to choose a region
AWS Притежава богат набор от регион. Всеки регион е изолиран от всеки друг. Тоест данните на един регион остават там докато не индексираш експлицитно че желаеш да преместиш данните от този регион. Най-често държавите имат закони против преместването на локални данни в други региони. Затова когато избираш регион първото нещо което е важно да се провери са законите за data requirement( data compliance). 
Следващия фактор който трябва да разгледаш при избор на регион е proximity. Колко си близо да аудиторията която ще използва твоя продукт. 
Третия фактор който трябва да имаш предвид е дали дадена функционалност е покрита в този регион. 
Четвъртия фактор е цената. Някой локации са по рентабилни да се опира в тях. най-често това се влияе от данъци, такси и разходи за електричество. AWS има много линирани ценови листи но те варират от регион до регион. Но за всеки регион можеш да очакваш еднакви разходи за еднакви ползвани функционалности.
![[Pasted image 20260409084744.png]]

# Diving Deeper into AWS Global Infrastructure
Когато става въпрос за инфраструктура ние целим да имаме никакъв down time за крайния клиент. Един от начините е се сложат redundant източници чрез [[Designing for high Availability & fault Tolerance|availability zones]]. Това е вид архитектура използваща множество AZ за менаджиране на на провал когато се лучи. Да имаш резерв в съвсем различна зона която не би се повлияла от спиране на ток или бедствия като наводнения или пожари. 
[[AWS CloudFront]]
[[AWS Global explorator]]
[[AWS route 53]]

# Infrastructure and Automation
Най-често когато разработва в облака искаме всичко да повторяемо и устойчиво. Както и искаме разгъването на продукта ни да е повторяемо и еднакво както в вече ползвания регион. За тази цел е нужна автоматизация или така нареченото Infrastructure as code(IaC) 

> [!опр] Infrastructure as code: Това е процеса по който чрез кода се вдига изгражда и разгъва инфраструктурата.

[[AWS CloudFormation]] Предоставя много на брой функционалности на AWS чрез декларации. Създава се документ описваш какво правиш наречен cloud formation templates. Всичко декларира в този документ се реализира върхъ дадена среда и се разгъва всичко описано.

## Programmatic access
Programmatic access includes options like the AWS CLI and AWS SDKs. These options are best suited for developers and those familiar with coding languages.

## AWS Management Console
The AWS Management Console is a web interface that you use for managing AWS services, offering quick access to services, search functionality, and simplified workflows. The console is a great option for those new to the cloud or users with minimal or no development experience.

## Infrastructure as Code
With IaC tools such as CloudFormation, you can automate resource management across your organization with AWS service integrations offering efficient and repeatable resource creation and management.
