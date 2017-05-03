# Other tools

## [Acrylic DNS Proxy](http://mayakron.altervista.org)

A tool available for windows allowing some performance improvement on DNS caching, and allowing wildcards and regex in the host definition.

### Preparation

As **Acrylic** will take the place of your current DNS provider, you should check its IP so that you can configure **Acrylic** to use it.

To do so, in a Windows console, do:

```bash
ipconfig /all | findstr /R "DNS"
```

This should give you this kind of row:

```bash
DNS servers. . .  . . . . . . . . . . : xxx.xxx.xxx.xxx
```

Keep track of this IP so you can configure **Acrylic** to use it when needed.

### Tools

There is a free tool to help you configure and manage **Acrylic** named **Acrylic DNS Proxy Monitor v2**. The link is available on the [home page](http://mayakron.altervista.org). Yet here is the [direct link](http://dev.arqendra.net/index1.php#adpm).

### Enable **Acrylic**

Don't forget to enable **Acrylic** once it's installed! Just follow the [windows 10 guide](http://mayakron.altervista.org/wikibase/show.php?id=AcrylicWindows10Configuration) to do so. Other guides are available on the [Home page](http://mayakron.altervista.org).

### Configuration

By default, **Acrylic** come with the [Google's Public DNS](https://developers.google.com/speed/public-dns/) configured. If you want to keep using you default DNS provider (can be the case if it's your workplace computer), you will have to configure **Acrylic** to use it.

To do so, you will have to edit the file named `AcrylicConfiguration.ini` and add the IP of your DNS provider next to the value `TertiaryServerAddress` (adding it as the third DNS provider in case of faillure of the 2 first one).

You can also configure **Acrylic** to use [OpenDNS](https://www.opendns.com/) as another DNS provider.

At the end, just configure the order in which your want to use the DNS provider.

To add new host, simply edit the file named `AcrylicHosts.txt`.

To finish this, once you have edited any if these configuration files, don't forget to restart **Acrylic** service.

## [Chocolatey](https://chocolatey.org/)

A package manager for Windows.
