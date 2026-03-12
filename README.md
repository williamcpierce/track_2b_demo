# track_2b_demo

PyLabRobot + Opentrons OT-2 liquid-handling demo for Monomer hackathon participants. Demonstrates deck setup, tip handling, aspirate/dispense with mixing, and dual pipette (P300/P1000) transfers across 24-well, 96-deep, and 96-flat plates.

## Setup

1. **Python 3.9+** and a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```

2. **Install dependencies** (includes PyLabRobot from GitHub):

   ```bash
   pip install -r requirements.txt
   ```

3. **Set the robot host.** The example script requires `OT2_HOST` (your OT-2’s IP):

   ```bash
   export OT2_HOST=192.168.1.1
   ```

   Replace with your robot’s actual IP.

## Running the example

With the OT-2 on the network and labware in the expected slots:

```bash
python monomer_example.py
```

**Deck layout** (see `monomer_example.py` for details):

| Slot | Labware |
|------|--------|
| 1 | 24-well deepwell plate (10 mL) |
| 2 | 96-well deepwell plate (2.2 mL) |
| 3 | 96-well flat bottom plate (360 µL) |
| 6 | 200 µL filter tip rack (P300) |
| 9 | 1000 µL filter tip rack (P1000) |

On error or Ctrl+C, the script discards tips and homes the robot before exiting.
