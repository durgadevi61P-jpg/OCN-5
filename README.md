# Exp.No:5  Free-Space Optical Communication (FSO) Implementation

## Aim

To implement and analyze a Free-Space Optical (FSO) communication link using a laser/LED transmitter and photodiode/APD receiver.

## Apparatus / Software Required

- Python
- Google Colab
- NumPy
- Matplotlib

## Theory

- FSO uses light beams to transmit data through free space instead of optical fiber.
- Performance depends on distance, alignment, and atmospheric attenuation.
- Received power decreases exponentially with distance due to atmospheric losses and beam spreading.

## Formula

**Link Loss (dB):**

```text
Loss = 10 × log10(P_in / P_out)
```

Where:

- P_in = Input optical power
- P_out = Received optical power

## 1. Setup the Transmitter

Prepare the optical source for transmission.

- Use a Laser/LED source.
- Mount it on an optical bench.
- Ensure a stable power supply.

## 2. Align the Optical Path

Proper alignment ensures maximum received signal.

- Place the transmitter and receiver in line of sight.
- Adjust using lenses/mirrors if needed.
- Minimize beam divergence.

## 3. Connect the Receiver

Set up the photodiode/APD to detect the optical signal.

- Mount the detector opposite to the transmitter.
- Connect it to an oscilloscope for signal observation.
- Record the received power.

## 4. Measure Received Power

Collect data at different distances.

- Vary the distance (1 m, 5 m, 10 m, etc.).
- Note the received power in µW.
- Calculate link loss using the formula:

```text
Loss = 10 × log10(P_in / P_out)
```

## 5. Plot Graphs

Visualize the performance of the FSO link.

- Plot Received Power vs Distance.
- Observe the exponential decay trend.
- Compare the results with the theoretical model.

## 6. Conclude Results

Summarize the findings of the experiment.

- Reliable communication up to approximately 10 m indoors.
- Signal loss increases with distance.
- Proper alignment is critical for better performance.

## Sample Output

**Graph: Received Power vs Distance (Decay Curve)**

![FSO Output 1](https://github.com/user-attachments/assets/0ec8bb24-ddfb-4d3a-b0f2-a5b661798ad4)

![FSO Output 2](https://github.com/user-attachments/assets/2a113e54-2433-4072-ba62-16539939e93a)

![FSO Output 3](https://github.com/user-attachments/assets/448e0d3f-a834-4e14-953f-4d429b7a9996)

## Python Code

```python
import numpy as np
import matplotlib.pyplot as plt

# --------------------------------
# 1. FSO Attenuation vs Visibility
# --------------------------------
visibility = np.linspace(0.1, 20, 100)

# Simple attenuation model
attenuation = 20 / visibility

plt.figure()
plt.plot(visibility, attenuation)
plt.xlabel("Visibility (km)")
plt.ylabel("Atmospheric Attenuation (dB)")
plt.title("FSO Attenuation vs Visibility (Kruse Model)")
plt.grid()
plt.show()


# --------------------------------
# 2. Rain Attenuation
# --------------------------------
rain = np.linspace(0, 50, 100)

# Simple rain attenuation model
rain_loss = 2 * np.sqrt(rain)

plt.figure()
plt.plot(rain, rain_loss)
plt.xlabel("Rain Rate (mm/hr)")
plt.ylabel("Rain Attenuation (dB/km)")
plt.title("Rain Attenuation in FSO Link")
plt.grid()
plt.show()


# --------------------------------
# 3. Attenuation vs Wavelength
# --------------------------------
wavelength = np.linspace(800, 1600, 100)

# Simple fog attenuation model
fog_loss = 20 * (800 / wavelength) ** 2

plt.figure()
plt.plot(wavelength, fog_loss)
plt.xlabel("Wavelength (nm)")
plt.ylabel("Attenuation (dB)")
plt.title("Attenuation vs Wavelength (Fog Condition)")
plt.grid()
plt.show()


# --------------------------------
# Result
# --------------------------------
print("Result:")
print("Reliable FSO link up to ~10 m indoors;")
print("beyond that, signal quality degrades significantly.")
```

## Output

<img width="800" height="1387" alt="WhatsApp Image 2026-11-26 at 9 06 46 AM" src="https://github.com/user-attachments/assets/db928eb3-7f87-455e-bd8e-69c9835e5e13" />
<img width="1535" height="1600" alt="WhatsApp Image 2026-11-26 at 9 07 01 AM" src="https://github.com/user-attachments/assets/310899ef-3de7-4bf2-8aed-623a072b229e" />


## Result
Reliable FSO link up to ~10 m indoors; beyond that, signal quality degrades significantly.
