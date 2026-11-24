# iptables Firewall

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 130–131; Linux Security.pdf, s. 303–307.

## Mapa wiedzy

- iptables is a CLI firewall framework that evaluates packets against ordered rules and actions.
- The lab/course uses INPUT rules to create a whitelist-style policy for SSH: explicitly allow a trusted source, then block other SSH traffic.
- Rules can match protocol, destination port, source address and target/action; listing rules with numeric addresses verifies active policy.

## Komendy / pliki / składnia występujące w materiale

```text
iptables is the command-line user interface for the built-in Linux kernel subsystem
iptables can be likened to a conditions system in which whether or not a condition is
iptables has three main tables, which are defined by their rules:
iptables organizes rules in chains that determine when rules will be evaluated. The filter
Iptables has multiple flags that can be used when defining rules:
sudo iptables -L -n
sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT
```

## Notatki z zajęć (PadRiseup)

- `sudo iptables -L -n`
- `sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-08-L1 — Configure a Whitelist](../labs/lnx-08-l1.md)
- [LNX-08-L2 — Summary Exercise](../labs/lnx-08-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 130:** | Chapter 8: Network Security

Section 1: iptables

iptables is the command-line user interface for the built-in Linux kernel subsystem

called Netfilter. Netfilter is what implements the firewall and routing capabilities of the

kernel, making it so that every Linux device can act as a router and/or firewall.

iptables can be likened to a conditions system in which whether or not a condition is

met, an action is executed. It either accepts, drops, or rejects network packets based

on rules in the tables.

e Accept — accepts the connection and allows communication.

e Drop — denies the connection and prevents the communication without displaying

an error code.

e Reject — denies the connection and prevents the communication but sends an

error message to the source of the request.

iptables has three main tables, which are defined by their rules:

e Filter: The main and most widely used table that controls whether or not a packet

is allowed to continue to its destination.

e NAT: This table implements network address translation rules for packets that

must have their source or destination address modified to reach their destination.

e Mangle: Holds rules that modify IP headers.

Two more tables that are not as widely used are:

e Raw: This table is called before the filter or the NAT tables, and is used to specify

whether or not connection tracking should be applied.

e Security: A table that marks packets in the context of SELinux security.

**Textbook s. 131:** iptables organizes rules in chains that determine when rules will be evaluated. The filter

table consists of three built-in chains that represent the direction of the traffic. Input

represents packets entering the system, forward is for routers that forward the traffic

to the next hop or recipient, and output is for traffic leaving the system.

New chains can be added, and existing ones can be deleted. Chains contain rules that

are evaluated sequentially, meaning that if you have a rule in your input chain in the

filter table to accept traffic from 192.168.10.15 but before it, there is a rule that drops

traffic from 192.168.0.0/24, the packet will not get through since the rule to accept it

comes after the rule to drop all traffic from that network.

Iptables has multiple flags that can be used when defining rules:

Flag Meaning

A Appends rules

€ Checks rules before adding them

D Deletes a rule by number

E Renames a user-defined chain

E Flushes the selected chain

h Lists command structures

i Sets a network interface

j Jumps to a specified target

° Sets the outgoing interface

p Protocol name

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 303:** Network Security

lptables

**Slides s. 304:** “ipt iptables

Q

®@ Iptables is a rule-based firewall daemon.

|| ® |t uses a command-line interface to add,

in delete, or edit rules.

® Policy chains allow or prevent traffic.

| lptables —L displays the complete rule list. &-

q\ = :

**Slides s. 305:** (Ch Iptables

Input - controls incoming connection behavior. %

| Forward - determines where packets can be

{| routed to.

¥ Output - controls outgoing connection behavior. 7

**Slides s. 306:** (Re Iptables

Accept - allows the connection. tea

Drop - drops the connection without issuing an

error code (connection timeout).

le Reject - denies the connection and sends an

y) error message to the source of the request.

aa

**Slides s. 307:** (Fle Iptables

Off

<) Appends rules ~) Lists command structures

“) Checks rules before adding them O) Sets a network interface

o ) Deletes a rule by number CJ Jumps to a specified target

oJ Renames a user-defined chain -) Sets the outgoing interface

O) Flushes the selected chain ) Protocol name

8

</details>
