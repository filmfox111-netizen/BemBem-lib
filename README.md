# bam/__init__.py

import subprocess
import os

def scan_wifi_linux():
    try:
        result = subprocess.check_output(["iwlist", "wlan0", "scan"], stderr=subprocess.DEVNULL).decode("utf-8", errors="ignore")
        return result
    except:
        return None

def bam_official():
    return scan_wifi_linux()

def bam_7x5(interface="wlan0"):
    try:
        result = subprocess.check_output(["iwlist", interface, "scan"], stderr=subprocess.DEVNULL).decode("utf-8", errors="ignore")
        return result
    except:
        return None
