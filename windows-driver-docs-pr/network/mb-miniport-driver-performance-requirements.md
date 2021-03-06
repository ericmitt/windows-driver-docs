---
title: MB Miniport Driver Performance Requirements
description: MB Miniport Driver Performance Requirements
ms.assetid: 16986208-7572-412d-8839-71f1a66b074f
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# MB Miniport Driver Performance Requirements


The following table describes the expectations for MB miniport drivers to respond to different MB operations. For the best experience, miniport drivers should complete operations within the time identified in the "Best case time (sec)" column.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">MB operation</th>
<th align="left">Best case time (sec)</th>
<th align="left">Worst case time (sec)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Time for device to initialize (to reach [<strong>WwanReadyStateInitialized</strong>](https://msdn.microsoft.com/library/windows/hardware/ff571227)) after being inserted into the machine ( [OID_WWAN_READY_INFO](https://msdn.microsoft.com/library/windows/hardware/ff569833))</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Manual network registration ( [OID_WWAN_REGISTER_STATE](https://msdn.microsoft.com/library/windows/hardware/ff569834))</p></td>
<td align="left"><p>0</p></td>
<td align="left"><p>50</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Network scan operation ( [OID_WWAN_VISIBLE_PROVIDERS](https://msdn.microsoft.com/library/windows/hardware/ff569843))</p></td>
<td align="left"><p>2</p></td>
<td align="left"><p>200</p></td>
</tr>
<tr class="even">
<td align="left"><p>Packet-attach operation ( [OID_WWAN_PACKET_SERVICE](https://msdn.microsoft.com/library/windows/hardware/ff569827))</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>5</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Packet-detach operation (OID_WWAN_PACKET_SERVICE)</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>5</p></td>
</tr>
<tr class="even">
<td align="left"><p>PDP activation ( [OID_WWAN_CONNECT](https://msdn.microsoft.com/library/windows/hardware/ff569823))</p></td>
<td align="left"><p>2</p></td>
<td align="left"><p>10</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PDP deactivation (OID_WWAN_CONNECT)</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>10</p></td>
</tr>
<tr class="even">
<td align="left"><p>Update system with IP address, default gateway, and DNS address</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>5</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[<strong>NDIS_STATUS_LINK_STATE</strong>](https://msdn.microsoft.com/library/windows/hardware/ff567391) notification after PDP activation</p></td>
<td align="left"><p>2</p></td>
<td align="left"><p>10</p></td>
</tr>
<tr class="even">
<td align="left"><p>Completion of the following PIN operations ( [OID_WWAN_PIN](https://msdn.microsoft.com/library/windows/hardware/ff569828)):</p>
<p>Enter</p>
<p>Enable</p>
<p>Disable</p>
<p>Change</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>4</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Query OID_WWAN_PIN to get the current PIN state of the MB device</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>4</p></td>
</tr>
<tr class="even">
<td align="left"><p>[OID_WWAN_PIN_LIST](https://msdn.microsoft.com/library/windows/hardware/ff569829) response to get a list of supported PIN types</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>4</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Time for SMS subsystem to be ready (should send the NDIS_STATUS_WWAN_SMS_CONFIGURATION unsolicited indication)</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>60</p></td>
</tr>
<tr class="even">
<td align="left"><p>Time for miniport driver to complete all other WWAN OIDs except OID_WWAN_VENDOR_SPECIFIC which are not covered in this table</p></td>
<td align="left"><p>1</p></td>
<td align="left"><p>15</p></td>
</tr>
</tbody>
</table>

 

 

 





