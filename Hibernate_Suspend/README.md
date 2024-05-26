# Enabling and Disabling Hibernat/Suspend modes

** https://wiki.debian.org/Suspend **

# For systems that should NEVER suspend in any way (ie active servers)
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
# and deactivating that:
sudo systemctl unmask sleep.target suspend.target hibernate.target hybrid-sleep.target

# Alternatively you can create /etc/systemd/sleep.conf.d/nosuspend.conf as follows
[Sleep]
AllowSuspend=no
AllowHibernation=no
AllowSuspendThenHibernate=no
AllowHybridSleep=no

# ( Close and still connect to Laptop )
# If you just want to prevent suspending when the lid is closed you can set the following options in 
# /etc/systemd/logind.conf 

[Login]
HandleLidSwitch=ignore
HandleLidSwitchDocked=ignore
