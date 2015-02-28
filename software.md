# Software Installation

Sonic Pi v2.0 has been included in Raspbian since September 2014 so if
you're using a recent image you should have this version installed.

To check you have version 2, double click the `Sonic Pi` icon on the
desktop or find it in the application menu under **Programming**. The
splash screen shown while loading shows the version number.

If you don't have Sonic Pi at all, type the following command in to
LXTerminal which you can access by clicking on **Main Menu**,
**Accessories** and **Terminal**:

First ensure your Raspberry Pi knows about all the latest software:

```bash
sudo apt-get update
```

Now ensure you have the latest version of Sonic Pi:

```bash
sudo apt-get install sonic-pi
```

Note: You will need to be connected to the internet to install or upgrade.
