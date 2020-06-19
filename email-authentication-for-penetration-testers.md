---
description: Registered Conference - Youtube 36c3
---

# Email authentication for penetration testers

{% embed url="https://www.youtube.com/watch?v=elxL8BU4vH8&list=PL\_IxoDz1Nq2YWdnWC4VFPk5ovr\_xUZemX&index=56" %}

Topics: _"How to fake an Email", "Email Conterfeiting", "Strategies for modern anti-spoofing"_

## Introduction - Why pentesters should care

 Everyone should start using **DEMARC** \( = _Domain-based Message Authentication, Reporting and conformance\)_ which is a email **authentication protocol**.

There are many different technologies that can be adopted to secure email usage and it can be difficult to know what should be implemented in the industry.

One way to choose from it is by doing some penetration testing. Looking the security of email form the perspective of an attacker is a great way to understand it and to adopt relevant countermeasures.

The email threat landscape is pretty large but this talk is focusing on the **spoofing. -**&gt; _attacks w/o any user-visible signs of tampering_

## Intro to SMTP

### Data Flow

SMTP is a protocol that underlies some email communications.

The following image shows the data flow happening when someone \(Alice\) sends an email to another person \(Bob\) from a **different organization**.

Normally each organization has its own **servers** for **incoming** and **outgoing** emails. If the company wants its domain to be accessible from others \(outside world\) than it has to be registered to some kind of DNS, the MX, which will give the IP address of the incoming server to the transmitter of the email.

Thus when Alice sends an email to Bob it first goes to the outgoing server which retrieves the address of  Bob's incoming server and sends the email.

For a penetration tester its important to think of about the different servers\(even if its physically on the same machine\): incoming/outgoing because they use different configurations thus we need to check for both of them. The client of the pentester only controls part of the protocol.

![](.gitbook/assets/smtp.png)

If Alice is communicating with a colleague than they are using the same domain \(same servers\) with two logical servers but in this case they both belongs to the same organization \(our client\).

![](.gitbook/assets/smtp-2.png)

### SMTP Structure

The SMTP protocol is a plain text protocol that involves an **enveloppe** and a **content** with _headers_ and a _body_.

An intersting thing to notice is that each address appears two times: 

1. In the enveloppe \(MAIL FROM and RCPT TO\)
2. In the Headers of the content \(From and To\)

![An simplified example of SMTP conversation](.gitbook/assets/smtp-3.png)

What is important to understand is that they are some standards for the headers but **in practice we can deliver messages with malformed headers.** Thus the penetration testers can play with this rules to find some breaches in the organization servers.

![Example of SMTP standards for headers](.gitbook/assets/smtp-standards.png)

## Basic Spoofing

## SPF

## DKIM

## DMARC

## Unauthenticated relays



