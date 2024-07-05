# aws-ec2

# rtp-linux
`
sudo perl -pi.bak -e 's|http://(security\|([^.]+\.)*archive)\.ubuntu\.com|http://rtp-linux.cisco.com|g' /etc/apt/sources.list
`
# sjc-linux
`
sudo perl -pi.bak -e 's|http://(security\|([^.]+\.)*archive)\.ubuntu\.com|http://sjc-linux.cisco.com|g' /etc/apt/sources.list
`
# rtp-linux
`
sudo sed -i.bak 's!http://\(security\|\([^.]\+\.\)*archive\)\.ubuntu\.com!http://rtp-linux.cisco.com!g' /etc/apt/sources.list
`
# sjc-linux
`
sudo sed -i.bak 's!http://\(security\|\([^.]\+\.\)*archive\)\.ubuntu\.com!http://sjc-linux.cisco.com!g' /etc/apt/sources.list
`
