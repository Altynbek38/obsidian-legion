# **The Three Dimensions**

# The Cybersecurity Cube
The **Cybersecurity Cube** is a model that provides a comprehensive way to think about protecting data. It is defined by three dimensions: security principles, data states, and safeguards.

**1. Security Principles (The CIA Triad)**  
This dimension identifies the fundamental goals of information security:

- **Confidentiality:** Prevents the disclosure of information to unauthorized people or systems.
    
- **Integrity:** Ensures the accuracy, consistency, and trustworthiness of data.
    
- **Availability:** Ensures that information is accessible to authorized users when needed.

**2. Data States**  
This dimension represents the three possible states in which data can exist, all of which must be protected:

- **Data in transit:** Data that is moving across a network.
    
- **Data at rest:** Data that is stored on a device or media.
    
- **Data in process:** Data that is actively being used or manipulated by an application.
    

**3. Safeguards**  
This dimension defines the types of countermeasures used to protect data and infrastructure:

- **Technology:** Technical tools and systems used for defense (e.g., firewalls, encryption).
    
- **Policy and Practices:** Administrative controls, rules, and procedures that govern security.
    
- **People:** Improving security through education, training, and awareness for users and personnel.


# The Principle of Confidentiality
Confidentiality prevents the disclosure of information to unauthorized parties. Key methods to achieve this include:

- **Tokenization:** A non-encryption technique that replaces sensitive data with a random, meaningless value (a token). This token preserves the original data's format, making it useful for protecting data in databases and payment processing systems.

- **Rights Management:** Uses encryption to protect data from unauthorized access.
    - **Digital Rights Management (DRM):** Protects copyrighted digital content like music, films, and books by encrypting them so only licensed users can access the content.
    - **Information Rights Management (IRM):** Protects organizational documents (e.g., emails, files) by allowing the owner to control and manage access rights even after the information has been shared.


# Data Integrity
**Data integrity** is the accuracy, consistency, and trustworthiness of data throughout its entire lifecycle. It ensures that data is not altered by unauthorized entities during any operation (e.g., storage, transfer, processing). Methods used to ensure integrity include **hashing**, data validation checks, and access controls.

The importance of data integrity varies depending on the organization and how it uses data:
- **Critical Need:** In healthcare, where prescription accuracy can be a matter of life or death.
- **High Need:** In e-commerce, where financial transactions and customer accounts must be accurate.
- **Mid Need:** For online sales and search engines that collect publicly posted data with little verification.
- **Low Need:** In social media or forums, where content is user-generated and often unverified.

# Availability
**Availability** ensures that information, systems, and services are accessible to authorized users when needed. Cyberattacks and system failures are common causes that can prevent access and impact the availability of data.


# Ensuring Availability
Organizations can implement many measures to ensure the availability of their services and systems. Key practices include:

- **Regular equipment maintenance** to improve uptime.
- Keeping all systems and software **updated** with the latest patches.
- Performing regular **data backups** and testing the recovery process.
- Creating and practicing a **disaster recovery plan**.
- **Adopting new technologies** to counter emerging threats.
- **Continuous monitoring** of system logs and alerts for real-time information.
- Regular **vulnerability testing** through port scans, vulnerability scans, and penetration tests.


# Data at Rest
**Data at rest** is data that is in storage and is not actively being accessed or processed. It can be stored on local devices or on a centralized network.

**Direct-attached storage (DAS)**  
This is storage connected directly to a computer, such as an internal hard drive or a USB flash drive. By default, it is not shared with other computers on the network.

**Redundant array of independent disks (RAID)**  
RAID combines multiple physical hard drives into a single logical unit to provide improved performance and fault tolerance (redundancy).

**Network attached storage (NAS) device**  
A NAS is a centralized storage device connected to a network, allowing authorized users to store and retrieve data. NAS systems are flexible and scalable.

**Storage area network (SAN)**  
A SAN is a high-performance, network-based storage system that uses high-speed connections to allow multiple servers to access a centralized block-level storage repository.

**Cloud storage**  
This is a remote storage option provided by a third-party data center and is accessible over the internet. Examples include Google Drive, iCloud, and Dropbox.


# Data in Transit

**Data in transit** is data that is actively being transmitted from one device to another. Protecting this data is a major challenge for cybersecurity professionals. The primary methods of transmission are:

- **Sneaker Net:** The physical transfer of data between computers using removable media like USB drives.
- **Wired Networks:** Transmit data as packets over physical media such as copper or fiber optic cables.
- **Wireless Networks:** Transmit data as packets using radio waves. Wireless networks increase the attack surface of a network because they are more easily accessible.


# Challenges of Protecting Data in Transit
Protecting data as it moves across networks is a significant challenge due to the increasing use of mobile and wireless devices. Cybersecurity professionals must address the following challenges to protect data in transit:

**Protecting Confidentiality**  
Attackers can capture and steal data as it is being transmitted. To ensure confidentiality, cybersecurity professionals use **encryption** technologies such as Virtual Private Networks (VPNs), SSL/TLS, and IPsec.

**Protecting Integrity**  
Attackers can intercept and alter data in transit. To ensure integrity, cybersecurity professionals deploy systems that use **hashing** and data redundancy to verify the authenticity and detect any modification of the transmitted data.

**Protecting Availability**  
Attackers can use rogue devices, such as a fake wireless access point, to intercept, hijack, or delete data, impacting its availability. To counter this, **mutual authentication** can be implemented, where both the client and the server must authenticate to each other, preventing connections to unauthorized systems.


# Data in Process
**Data in process** refers to data that is actively being used, such as during initial input, modification, computation, or output.

**Input**  
This is the initial collection of data through methods like data entry, form scanning, file uploads, or sensors. Threats to integrity at this stage include data entry errors, mislabeling, incorrect data formats, or malfunctioning sensors.

**Modification**  
This is any change made to the original data. Changes can be intentional (e.g., processing, encoding, encryption) or unintentional/malicious, which is often called **data corruption**. Corruption can be caused by equipment failure or malware.

**Output**  
This refers to sending data to devices like printers or displays. The accuracy of output data is critical for decision-making. Output corruption can be caused by incorrect data delimiters or improperly configured devices.


