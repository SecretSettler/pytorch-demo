### **1. Install Required Packages**
On the head node:
```bash
git clone https://github.com/SecretSettler/pytorch-demo.git
cd pytorch-demo
conda create -n mlsys python=3.10 -y
conda activate mlsys
pip install -r requirements.txt
```

---

### **2. Run the Demo in Interactive Mode**
To start the demo interactively, use:
```bash
srun --gres gpu:1 --pty bash
```

This command will allocate and enter a compute node with one GPU. Once inside the compute node, run the following commands to execute the demo:

```bash
conda activate mlsys
python demo.py
```

If the script runs without any errors, congratulations!

---

### **3. Run the Demo in Batch Mode**
To run the demo in batch mode, first create a Bash script (e.g., `test.sh`) with the following content:

```bash
#!/bin/bash
source ~/miniconda3/bin/activate
conda activate mlsys
cd pytorch-demo
python demo.py
```

Then submit the job using:
```bash
sbatch --gres gpu:1 test.sh
```

If the output file does not show any errors, congratulations! The demo has successfully executed.
