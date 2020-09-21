# Bare Metal
In a bare metal deployment there are three major components:
1. The hardware that's running the code.
2. The OS (operating system) that manages the hardware, and schedules software to run.
3. The service that's being deployed into the hardware.

## Advantages
- Only 1 kernel running reducing overhead.
- Conceptually simpler.
- With all things the same, better performance then a VM.

## Disadvantages
- Slow to deploy (requires a physical thing before deployment)
- "Drift" between deployments becomes problematic.
	- Deployments that have been running for a while may be on older version of software (like node, or the OS version) which lead to differences at runtime.
	- New deployments take time to "image" the machine, and make it avaliable for use.
- Installing a new "package" (think node) can break other software running on the machine, so the versions need to be consistant.
- Deploying new software can be combersom.

### Security
The security is limited by what the kernel can do. The OS has direct access to [Ring 0][1].
[1]: https://en.wikipedia.org/wiki/Protection_ring