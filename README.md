# Introduction

Aegis is a collection of tools that make up an intelligent system which provides fool-proof protection against sophisticated malaware attacks and zero-day attacks. The following is the aegis stack of tools in aegis collection:

* [AEGIS-IDENTITY](https://github.com/SidhuG/aegis-identity)
* [AEGIS-OBSERVER](https://github.com/SidhuG/aegis-observer)
* [AEGIS-ENGINE](https://github.com/SidhuG/aegis-engine.git)
* [AEGIS-ENFORCER](https://github.com/SidhuG/aegis-enforcer)


With each of the tool dependent on the tool(s) above it in the stack. Any exploits and vulnerabilities that may exist in the softwares/services are neutralised by Aegis. The tools and a machine learning system that make up 'Aegis' severley limit actions of malawares, ransomwares or a hacker who has broken into the system.

## What and How of Aegis

**Aegis-Identity** provides mechanism and tooling to use a combination of parameters or sub identities to assign an identity to a running program/executable on a linux system. It can also be run as a standalone tool for managing identities.

**Aegis-Observer** records the actions of a running program/executable. During test cycle it records actions and behaviours at a very granual level and writes down a trail of those actions/behaviours. These trails form the whitelist. That is, this is what that executable/binary which is not compromised would do. In a production or live environment aegis-observer observes actions again, however, this time, it is meant for the purpose of monitoring those in order to detect malicious and anomalous behaviours/actions and with the purpose of enforcement where any malicious and  anomalous behaviour is prevented. Aegis-observer could be run along with aegis-identity, however, it can be run standalone. When run standalone, it basically runs in a monitoring and detection mode. When used with aegis-identity, the enforcement is more stricter as anything not identifiable through aegis-identity is not run, and those identifiable have their actions/behaviours observed, recorded, and traced.

It helps other tools in the chain, as aegis-engine described below. As output from aegis-observer is used by aegis-engine.

**Aegis-Engine** is the AI/ML brain of Aegis, it consumes data, which is, 'granular actions' of a running executable from the aegis-observer and it uses that to develop insights and models. This is done during the test stage. During a live-production stage, engine is able to detect and flag up an anomalous behaviour of a running executable as compromised. That is if the executable diverges from its normal or regular trail of actions.

**Aegis-Enforcer** enforces secure patterns and standards, it takes proactive actions based on the observation carried out by the aegis-observer and the result of the aegis-engine. If aegis-engine flags up a compromise or anomalous behaviour of the executable, it could be configured to unload the executable, save the context for offline screening.