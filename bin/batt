#!/bin/bash

# Scrape percentage of battery remiaining
p_batt=$(upower -d | grep -m1 percentage | tr -d [:space:] | awk '{gsub("percentage:", "");print}')

# Scrape the current status (AC or BATT)
s_batt=$(upower -d | grep -m1 state | tr -d [:space:] | awk '{gsub("state:", "");print}')

# Scrape time left on BATT
r_batt=$(upower -d | grep -m1 "time to empty:" | awk '{gsub("time to empty:", "");print}' | tr -s " ")

# If battery is discharging, display time to empty
if [ "$s_batt" = "discharging" ]
   then
     echo "[ BATT: $p_batt | $s_batt |$r_batt ]"
   else
     echo "[ BATT: $p_batt | $s_batt ]"
fi
