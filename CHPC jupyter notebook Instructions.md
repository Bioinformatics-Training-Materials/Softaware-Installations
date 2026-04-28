# Jupyter Notebook Startup on CHPC Lengau (PBS + SSH)

**User:** `fkebaso@lengau.chpc.ac.za`

---

## Goal

Run JupyterLab on an allocated **compute node** and access it safely from your laptop browser using SSH tunneling.

---

## Important

- Never run heavy Jupyter sessions on `login2` if avoidable.
- Always request an interactive compute node first.
- The compute node name changes each time (`cnodeXXXX`).
- Replace the node name in the SSH tunnel accordingly.

---

# Step 1: On Login Node (`login2`)

Request interactive compute resources.

## Resources Requested

- 1 node
- 20 CPUs
- 120 GB RAM
- Up to 8 hours

```bash
qsub -I -P CBBI1470 -l select=1:ncpus=20:mem=120gb -l walltime=08:00:00
```

---

# Step 2: Wait for PBS to Start Job

You will see:

```text
qsub: waiting for job XXXXXXX.sched01 to start
qsub: job XXXXXXX.sched01 ready
```

Your prompt changes from:

```bash
[fkebaso@login2 ~]$
```

to something like:

```bash
[fkebaso@cnode0941 ~]$
```

This means you are now on a compute node.

---

# Step 3: On the Compute Node

Load the software environment.

```bash
module load chpc/BIOMODULES
module load anaconda/3-2024.10.1
eval "$(conda shell.bash hook)"
```

---

# Step 4: Start JupyterLab

```bash
jupyter lab --no-browser --ip=0.0.0.0 --port=8888
```

Keep this terminal open.

---

# Step 5: Copy the Token URL Shown

Example:

```text
http://cnode0941:8888/lab?token=abc123...
```

---

# Step 6: On Your Laptop (WSL Terminal)

Create SSH tunnel. Replace the node name accordingly.

```bash
ssh -L 8888:cnode0941:8888 fkebaso@lengau.chpc.ac.za
```

Examples:

```bash
ssh -L 8888:cnode0027:8888 fkebaso@lengau.chpc.ac.za
ssh -L 8888:cnode0312:8888 fkebaso@lengau.chpc.ac.za
```

Keep this terminal open.

---

# Step 7: On Laptop Browser

Open:

```text
http://localhost:8888
```

Or:

```text
http://localhost:8888/lab?token=PASTE_TOKEN_HERE
```

---

# Troubleshooting

## If Port 8888 Is Busy Locally

```bash
ssh -L 8890:cnode0941:8888 fkebaso@lengau.chpc.ac.za
```

Then open:

```text
http://localhost:8890
```

## If You Forget the Node Name

```bash
hostname
```

## If Session Ends

```bash
qstat -u fkebaso
```

## To Stop Jupyter

Press `Ctrl+C` in the compute-node terminal.

---

# Best Practice

Keep three windows open:

1. Compute-node terminal running Jupyter
2. WSL terminal with SSH tunnel
3. Browser
