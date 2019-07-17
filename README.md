# Solidity Security Design Patterns
## Code and slides of ICT Risk Assessment 2018/2019 seminar.

NEW! Now compatible with Solidity 0.5.1!


Design  patterns are a commonly used technique to encode design guide-lines or best practices. They express an abstract or conceptual solution to a concrete, complex, and reoccurring problem.


_ | CHECKS-EFFECTS-INTERACTION PATTERN |
--- | :---  | 
**Problem** | When  a  contract  calls  another  contract,  it  hands  over  control to that other contract. The called contract can then, in turn, re-enter the contract by which it was called and try to manipulate its state or hijack the control flow through malicious code. | 
**Solution** | Follow a recommended functional code order, in which calls to external contracts are always the last step, to reduce the attack surface of a contract being manipulated by its own externally called contracts. | 
Source | [security/ChecksEffectsInteraction.sol](security/ChecksEffectsInteraction.sol)

_ | EMERGENCY STOP (CIRCUIT BREAKER) PATTERN |
--- | :---  | 
**Problem** | Since a deployed contract is executed autonomously on the Ethereum network, there is no option to halt its execution in case of a major bug or security issue. | 
**Solution** | Incorporate an emergency stop functionality into the contract that can be triggered by an authenticated party to disable sensitive functions. | 
Source | [security/EmergencyStop.sol](security/EmergencyStop.sol)

_ | SPEED BUMP PATTERN |
--- | :---  | 
**Problem** | The simultaneous execution of sensitive tasks by a huge number of parties can bring about the downfall of a contract. | 
**Solution** | Prolong the completion of sensitive tasks to take steps against fraudulent activities. | 
Source | [security/SpeedBump.sol](security/SpeedBump.sol)

_ | RATE LIMIT PATTERN |
--- | :---  | 
**Problem** | A request rush on a certain task is not desired and can hinder the correct operational performance of a contract. | 
**Solution** | Regulate how often a task can be executed within a period of time. | 
Source | [security/RateLimit.sol](security/RateLimit.sol)

_ | MUTEX PATTERN |
--- | :---  | 
**Problem** | Re-entrancy attacks can manipulate the state of a contract and hijack the control flow. | 
**Solution** | Utilize a mutex to hinder an external call from re-entering its caller function again. | 
Source | [security/Mutex.sol](security/Mutex.sol)

_ | BALANCE LIMIT PATTERN |
--- | :---  | 
**Problem** | There is always a risk that a contract gets compromised due to bugs in the code or yet unknown security issues within the contract platform. | 
**Solution** | Limit the maximum amount of funds at risk held within a contract. | 
Source | [security/LimitBalance.sol](security/LimitBalance.sol)


# Reference
[Smart Contracts: Security Patterns in the Ethereum Ecosystem and Solidity](https://swa.cs.univie.ac.at/research/publications/publication/5433/)
