mitmpcap
========

This is a [mitmproxy addon][] script, it exports traffic to PCAP file, so you can view the decoded HTTPS or HTTP/2 traffic in other programs.

[mitmproxy addon]: https://docs.mitmproxy.org/stable/addons-overview/

Usage
-----

Use as addon for mitmproxy/mitmweb/mitmdump command:

```
mitmweb -s mitmpcap.pcap
```

By default, it exports to filename `output.pcap`.

Setting
-------

Edit the `mitmpcap.py` file, change the `File` class argument at the end of file:

```
addons = [Addon(lambda: File('output.pcap'))]
```

You also can pipe the PCAP data to other program, use the `Pipe` class:

```
addons = [Addon(lambda: Pipe('weer -'))]
```

This will start [Weer][] as child process to receive the PCAP data.

[Weer]: https://weerdbg.com/

License
-------

MIT
