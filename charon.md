# Download Charon
Stromasys.CHARON-AXP.v4.2.Build.142-01.68704122.Retail.GNU.Linux.x64.Cracked-VLF.tar

# Extract the file to /opt/charon
tar -xvf Stromasys.CHARON-AXP.v4.2.Build.142-01.68704122.Retail.GNU.Linux.x64.Cracked-VLF.tar -C /opt/charon

# Create /etc/ld.so.conf.d/charon.conf
echo "/opt/charon/lib/axp" > /etc/ld.so.conf.d/charon.conf

# Run ldconfig
ldconfig

# Use the libre.sh script
/opt/charon/libre.sh

### Note: this has to be done as root.
