
nRF Connect SDK Thread Certification
####################################

Placeholder for NCS Thread Certification related information.

Build the certification image
*****************************

The 'openthread/cli' sample is used as a base, modifiying it with an overlay file.

::

 cd nrf/samples/openthread/cli/
 west build -b nrf52840dk_nrf52840 -- -DCONF_FILE="prj.conf overlay-cert_mi.conf"

Prepare Thread Harness
**********************

Copy the provided ``nrf52840-ncs.py`` file into ``C:\GRL\Thread1.1\Thread_Harness\THCI``.

Copy the provided ``nrf52840.jpg into`` ``C:\GRL\Thread1.1\Web\images``.

Edit ``C:\GRL\Thread1.1\Web\data\deviceInputFields.xml`` and prepend this:

::

    <DEVICE name="nRF52840-ncs" thumbnail="nRF52840.jpg" description = "Nordic Semiconductor: nRF52840 (NCS) Baudrate:115200" THCI="nRF52840-ncs">
        <ITEM label="Serial Line"
              type="text"
              forParam="SerialPort"
              validation="COM"
              hint="eg: COM1">COM
        </ITEM>
        <ITEM label="Speed"
              type="text"
              forParam="SerialBaudRate"
              validation="baud-rate"
              hint="eg: 115200">115200
        </ITEM>
    </DEVICE>
```

Beyond Certification
********************

This is the list of included features for nRF5 SDK Master Image:

* BORDER_AGENT=1
* BORDER_ROUTER=1
* COAP=1
* COMMISSIONER=1
* DISABLE_BUILTIN_MBEDTLS=1 (optional)
* DNS_CLIENT=1
* DIAGNOSTIC=1
* EXTERNAL_HEAP=1
* JOINER=1
* LINK_RAW=1
* MAC_FILTER=1
* MTD_NETDIAG=1
* SERVICE=1
* UDP_FORWARD=1
* ECDSA=1
* SNTP_CLIENT=1
* COAPS=1
* DHCP6_SERVER=1
* DHCP6_CLIENT=1
* JAM_DETECTION=1
* CHILD_SUPERVISION=1

Ideally we should support all of them in NCS as well.
