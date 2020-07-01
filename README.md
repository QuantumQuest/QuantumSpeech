# Quantum Noise Analyzer
##IBM Qiskit Community Summer Jam 2020 Hackathon

Efficient quantum signal processing is desirable to understand the dynamics of noisy quantum systems. To measure quantum noise, the scientist typically performs a measurement that projects the quantum state of the system onto a classical computational basis. Phase information is lost during this projection, and many repeated measurements on the quantum system are required to estimate the quantum state -- a feat often undesirable in the case of quantum sensors. However, processing speed and throughput can be increased by coherently analyzing quantum data on a quantum computer, and avoiding projective readout. We demonstrate this with our quantum noise analyzer (QNA). 

First, we create a quantum register in an equal superposition state and a single sensing qubit. We then entangle only one of the register states with the sensor qubit that accumulates the phase information from the sensing. After disentangling the sensor and the register, which re-initializes the sensor, various MCMT gates deterministically move the phase to the appropriate multi-qubit quantum register state. After the sensing sequence is done and all of the phase information is encoded, QNA implements a Quantum Fourier Transform (QFT) to transform the signal from time domain into the frequency domain. Encoding quantum data directly into a quantum register exponentially reduces the qubit and gate requirements of the QFT as compared to the classical fourier transform with the same number of classical bits.

In a classical computer, it takes 64-bits to encode a floating point number, whereas a qubit can theoretically encode any arbitrary amplitude (including irrational numbers!). For example it would require 64 x 64-bit floating numbers to encode 64 floating numbers in a classical computer, whereas a quantum computer only requires 6 qubits to encode 64 numbers where each superposition state can encode an arbitrary amplitude. QNA can process information in only 6 qubits that would require a classical computer over 4000 classical bits!

By example of our QNA, we have presented a new paradigm where quantum data is directly analyzed on a quantum processor. The next step towards on-chip quantum noise analysis will require understanding the effects of finite qubit coherence on the QNA performance. Robust implementation of the QNA on IBM Q will allow us to fully leverage the rapid development of quantum technological infrastructure. For instance, our quantum signal processing algorithm can be generalized to two-qubit gate couplings or even larger quantum sensor networks. A dynamical decoupling pulse sequence can be employed to accumulate phase on a sensor qubit from a nearby qubit that is rotating at a known frequency. This could help IBM diagnose problems with decoherence due to two-qubit gate couplings and improve them. 

Furthermore, the QFT algorithm can be swapped out or combined with other quantum algorithms to extend its performance. Examples include combining the existing QNA with error correcting circuits or implementing a Grover search algorithm to search a database of noisy qubits and optimize quantum network topologies. The sensing qubit need not be limited to a quantum chip either. Future quantum transductors that would be used for distributed quantum computing could also be used to teleport quantum states from quantum sensors. This could lead to many advancements from discovering novel material properties to chemistry and biology. Being able to generate a quantum data set from quantum sensors could also aid training quantum artificial intelligence. A superposition quantum register can encode an exponential number of data points simultaneously, however, this information is inaccessible through classical means before a quantum computation. QNA merges quantum data generation and it’s analysis to demonstrate the exponential gain in register and processing power from this technique, and applies it to a real system to measure environmental sensitivity (decoherence) as a proof of principle.
