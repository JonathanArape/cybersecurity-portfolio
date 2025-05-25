# Internal Security Audit – Botium Toys

**Author:** Jonathan Arape  
**Date:** [5/25/2025]  
**Course:** Google Cybersecurity Certificate  
**Activity:** Controls and Compliance Checklist

---

## Activity Scenario (Provided Instructions)

Botium Toys is a small U.S.-based company that develops and sells toys. The company’s only physical location serves as headquarters, storefront, and warehouse. As their online presence grows, their IT department faces increased pressure to support international markets.

The IT manager wants to perform an internal audit to assess risks, improve compliance, and identify missing controls using the **NIST Cybersecurity Framework (CSF)**.

**Key Audit Goals:**
- Review managed assets
- Identify gaps in controls and compliance
- Provide recommendations to improve security posture

**Current Risks Identified:**
- Inadequate asset management
- Lack of encryption for customer data
- Poor password policies
- No backups or disaster recovery plan
- No intrusion detection system (IDS)
- No least privilege enforcement
- Access to sensitive data by all employees

**Risk Score:** 8 out of 10

---

## Controls Assessment Checklist

| Control                                             | Implemented |
|-----------------------------------------------------|-------------|
| Least Privilege                                     | ❌ No  
| Disaster Recovery Plans                             | ❌ No  
| Password Policies                                   | ❌ No  
| Separation of Duties                                | ❌ No  
| Firewall                                            | ✅ Yes  
| Intrusion Detection System (IDS)                    | ❌ No  
| Backups                                             | ❌ No  
| Antivirus Software                                  | ✅ Yes  
| Legacy System Monitoring                            | ✅ Yes *(irregular)*  
| Encryption                                          | ❌ No  
| Password Management System                          | ❌ No  
| Physical Locks (Office, Store, Warehouse)           | ✅ Yes  
| CCTV Surveillance                                   | ✅ Yes  
| Fire Detection and Prevention                       | ✅ Yes  

---

## Compliance Checklist

### **PCI DSS**

| Best Practice                                                            | Compliant |
|--------------------------------------------------------------------------|-----------|
| Only authorized users access customer credit card data                   | ❌ No  
| Credit card data is stored/transmitted securely                          | ❌ No  
| Data encryption is implemented                                           | ❌ No  
| Secure password management policies are in place                         | ❌ No  

### **GDPR**

| Best Practice                                                            | Compliant |
|--------------------------------------------------------------------------|-----------|
| E.U. customer data is secured                                            | ✅ Yes  
| Breach notification within 72 hours plan                                 | ✅ Yes  
| Data is classified and inventoried                                       | ❌ No  
| Privacy policies and processes enforced                                  | ✅ Yes  

### **SOC 1 / SOC 2**

| Best Practice                                                            | Compliant |
|--------------------------------------------------------------------------|-----------|
| User access policies are established                                     | ❌ No  
| Sensitive data is private/confidential                                   | ❌ No  
| Data integrity is ensured                                                | ✅ Yes  
| Data availability for authorized individuals                             | ✅ Yes  

---

## Recommendations

To improve its security posture and reduce the current high risk level (score: 8/10), Botium Toys should:

- Enforce least privilege and separation of duties.
- Implement a disaster recovery plan and backup strategy.
- Use encryption for sensitive data.
- Strengthen password policies and deploy a password manager.
- Install and configure an IDS.
- Schedule regular maintenance for legacy systems.

These improvements will help achieve compliance with key frameworks and better protect organizational assets.

---

> *This internal audit was conducted as part of my cybersecurity training. It demonstrates my understanding of security controls, risk analysis, and compliance best practices.*
