# SchedOS

SchedOS is a custom Linux distribution based on Manjaro XFCE, designed as an educational operating system project. The goal of SchedOS is to provide a lightweight Linux environment while integrating CPU Scheduling Visualization tools for learning Operating System concepts such as FCFS, SJF, and Round Robin scheduling.

---

## Features

- Based on Manjaro XFCE
- Lightweight and beginner-friendly
- Custom wallpaper and branding
- Educational CPU Scheduling Visualizer
- FCFS Scheduling Algorithm
- SJF Scheduling Algorithm
- Round Robin Scheduling Algorithm
- Gantt Chart Visualization
- Process Statistics and Comparison
- Custom ISO Generation

---

## Requirements

- Manjaro Linux
- Git
- Manjaro Build Tools
- Internet Connection
- At least 20 GB free disk space

---

## Install Required Packages

Update system:

```bash
sudo pacman -Syu
```

Install Git:

```bash
sudo pacman -S git
```

Install Manjaro ISO build tools:

```bash
pamac install manjaro-tools-iso-git git
```

---

## Download ISO Profiles

Clone official Manjaro ISO profiles:

```bash
git clone https://gitlab.manjaro.org/profiles-and-settings/iso-profiles.git ~/iso-profiles
```

Verify XFCE profile:

```bash
ls -l ~/iso-profiles/manjaro/xfce
```

Expected files:

```text
desktop-overlay/
live-overlay/
Packages-Desktop
Packages-Live
Packages-Mhwd
Packages-Root
profile.conf
```

---

## Download BuildISO

```bash
git clone https://gitlab.manjaro.org/tools/development-tools/buildiso.git
```

Move into buildiso directory:

```bash
cd buildiso
```

---

## Customization

### Create Skeleton Directory

```bash
cd ~/iso-profiles/manjaro/xfce/desktop-overlay/etc/

mkdir -p skel
```

---

### Create Wallpaper Directory

```bash
cd ~/iso-profiles/manjaro/xfce/desktop-overlay/

mkdir -p ./usr/share/backgrounds
```

---

### Copy Custom Wallpaper

Replace `your-wallpaper.png` with your own wallpaper file.

```bash
cp ~/Pictures/Wallpapers/your-wallpaper.png \
~/iso-profiles/manjaro/xfce/desktop-overlay/usr/share/backgrounds/
```

---

## Build SchedOS ISO

Generate the custom ISO:

```bash
buildiso -p xfce
```

Build time depends on your internet speed and hardware.

---

## ISO Output Location

Generated ISO file:

```text
/var/cache/manjaro-tools/iso/
```

View generated ISO:

```bash
ls /var/cache/manjaro-tools/iso/
```

---

## Testing in VirtualBox

Create a new Virtual Machine:

```text
Type: Linux
Version: Arch Linux (64-bit)
RAM: 4 GB or higher
CPU: 2 Cores or higher
Disk: 30 GB or higher
```

Attach the generated ISO and boot the VM.

---

## Project Structure

```text
SchedOS/
│
├── scheduler/
│   ├── process.py
│   ├── fcfs.py
│   ├── sjf.py
│   └── round_robin.py
│
├── ui/
│   ├── main_window.py
│   ├── process_table.py
│   └── gantt_widget.py
│
├── utils/
│   ├── statistics.py
│   └── export.py
│
└── assets/
```

---

## CPU Scheduling Algorithms

### FCFS (First Come First Serve)

Processes are executed in the order they arrive.

### SJF (Shortest Job First)

Processes with the shortest burst time are executed first.

### Round Robin

Each process gets a fixed time quantum before switching to the next process.

---

## Future Improvements

- Custom Login Screen
- Custom Plymouth Boot Screen
- SchedOS Branding
- Dark Theme
- Algorithm Comparison Dashboard
- Resource Monitoring
- Memory Management Visualization
- Deadlock Visualization
- Banker's Algorithm Module

---

## Author

Sadman

---

## License

This project is developed for educational and research purposes.
