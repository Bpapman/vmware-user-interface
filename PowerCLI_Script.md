"<<>>" > tmp.txt
#Setting Variables full of pertanent information
$VMArray = Get-VM
$Server = Get-VMHost
$SwitchArray = Get-VirtualSwitch
$PortGroupArray = Get-VirtualPortGroup

> "

&lt;node&gt;

" >> tmp.txt
> $Server.Name >> tmp.txt

#Constructing the list of nodes
for($i=0;$i -lt $SwitchArray.length; $i++)
{
> "

&lt;node&gt;

" >> tmp.txt
> $SwitchArray[$i].Name >> tmp.txt
}

for($i=0;$i -lt $PortGroupArray.length; $i++)
{
> "

&lt;node&gt;

" >> tmp.txt
> $PortGroupArray[$i].Name >> tmp.txt
}

for($i=0;$i -lt $VMArray.length; $i++)
{
> "

&lt;node&gt;

" >> tmp.txt
> $VMArray[$i].Name >> tmp.txt
}

"<<>>" >> tmp.txt
#Now to print the connections
#Printing connections fomr Server to Switches
for($i=0;$i -lt $SwitchArray.length;$i++)
{
> $tmp = $SwitchArray[$i]
> "<$Server,$tmp>" >> tmp.txt
}
#Printing Connections to VirtualSwitch to Network
for($i=0;$i -lt $SwitchArray.length;$i++)
{
> echo $i
> $tmpSwitch = $SwitchArray[$i].Name
> $Networks = Get-VirtualPortGroup -VirtualSwitch $tmpSwitch

> if(!$Networks.length)
> {
> > "<$tmpSwitch,$Networks>" >> tmp.txt

> }
  1. ote: The above if statment is to check that an array was indeed returned
  1. eed to add these to every for loop, powerCLI returns a single object
  1. f only a single object exists, as opposed to an array of length 1.
  1. hich you know, would make sense.

> for($j=0;$j -lt $Networks.length;$j++)
> {
> > $tmpNetwork = $Networks[$j].Name
> > "<$tmpSwitch,$tmpNetwork>" >> tmp.txt

> }
}
#Network to VM connection.
for($i=0;$i -lt $VMArray.length;$i++)
{
> $tmpVM = $VMArray[$i].Name
> $tmpNetworks = Get-NetworkAdapter -VM $tmpVM
> if(!$tmpNetworks.length)
> {
> > "<$($tmpNetworks.NetworkName),$tmpVM>" >> tmp.txt

> }
> for($j=0;$j -lt $tmpNetworks.length;$j++)
> {
> > $tmpAdapter = $tmpNetworks[$j].NetworkName


> "<$tmpAdapter,$tmpVM>" >> tmp.txt


> }

}