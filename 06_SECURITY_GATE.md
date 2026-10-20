• What it is: The hardware-enforced security barrier and transaction fencing subsystem.
• Technologies inside: Biometric authentication APIs (PAM modules for Fingerprint/FaceID), Linux Kernel Capability drops, hardware security modules (TPM 2.0), and cryptographic action authorization tokens.
• Purpose: To prevent the AI cognitive core from executing destructive operations on the host system by intercepting critical system calls and locking them behind a mandatory physical biometric verification barrier.

---

### Open Questions

1. How is intent validated before syscall interception, not after?
2. What is the false-positive rate for biometric authentication in field use?
3. How does the TPM handle key rotation after compromise?
4. What is the recovery procedure if biometric hardware fails?
5. How are policy updates delivered without breaking the immutable host?
