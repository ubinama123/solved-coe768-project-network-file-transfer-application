Download Link: https://assignmentchef.com/product/solved-coe768-project-network-file-transfer-application
<br>
In this project, you will implement a file transfer application based on TCP_ The server is a concurrent server that can handle multiple file transfer sessions. The client can both upload files to and download files from the server. In addition, the client can request the change of directory and list the files in a given directory. Figure 1 shows the PDU format to be used in the implementation_

size of the Data field_ The data field contains the data, there are eight PDU types_

<ul>

 <li><sup>.</sup>1<sup>–</sup>ype – — This PDU is sent by the client to request a file download. The Data field</li>

</ul>

contains the file name and the length field indicates the length of the name_

<ul>

 <li>Type — This PDU is sent by the client to request a file upload. The Data field containsthe file name and the length field indicate the length of the name.</li>

 <li>Type ‘R.’ <strong>— </strong>This PDU is sent by the server to indicate that it is ready</li>

 <li>Type ‘F’ — This PDU contains the file data. The length field indicates the size of the file.</li>

 <li>Type *E’ — This PDU is used to report error. The Data field contains the error message and the length field indicates the size of the message_</li>

 <li>Type <sup>.</sup>P’ — This PDU is sent by the client to request the change of directory_ The Data field contains the directory path <strong>name</strong></li>

 <li>Type <strong>— </strong>This PDU is sent by the client to request the list of files in a given directory.The Data field contains the directory path name</li>

 <li>Type — This PDU is sent by the server_ The data field contains the list of file names_</li>

</ul>




<strong><u>Flow Diagrams</u></strong>

<strong>Figures 2, 3, 4, 5 and 6 show the PDLT exchange scenarios for the file download, file upload, error reporting, change directory and list directory, respectively.</strong>




<table width="100%">

 <tbody>

  <tr>

   <td><strong>TCP                                             Server</strong></td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>Client</td>

  </tr>

 </tbody>

</table>




<table width="100%">

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>.40</td>

  </tr>

 </tbody>

</table>

<strong>PDU(0.1ength.filename)</strong><strong>PDU(F.length.Data)</strong>

<strong>Fig 2: File Download</strong>

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Client</strong></td>

  </tr>

 </tbody>

</table>

<strong>TCP                               </strong><strong>Server</strong>

<strong>–     _   _</strong>

<strong>PD U(U,Iength,filename)</strong>




<table>

 <tbody>

  <tr>

   <td width="43">•</td>

   <td width="151"><strong>PDU(R,O)</strong></td>

  </tr>

 </tbody>

</table>




<strong>PDU(F,length,Data)</strong><strong>•</strong>

<strong>– –</strong>

<strong>Fig 3: File Upload</strong>

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Client</strong></td>

  </tr>

 </tbody>

</table>

<strong>TCP                          Server</strong>

<strong>PDU(UID.Iength,filename)</strong>

<strong>PDU(Elength,message)</strong>

<strong>Fig 4: Error Reporting</strong>




<table width="100%">

 <tbody>

  <tr>

   <td><strong>Server</strong><strong>Change directory</strong><strong>Server</strong></td>

  </tr>

 </tbody>

</table>

<strong>Client                                          </strong><strong>TCP</strong>

<strong>PDU(P,length,dir_path)</strong>

<strong><sup>—</sup></strong><strong>–a.</strong>

<strong>—-</strong><strong><sup>–4</sup></strong>

<strong>4——-                 —</strong>

<strong>PDU(R,0</strong><strong><sup>—</sup></strong>

<strong>Fig 5: Change directory</strong>




<table width="100%">

 <tbody>

  <tr>

   <td><strong>Client</strong></td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td><strong>TCP</strong></td>

  </tr>

 </tbody>

</table>




<strong>—-____</strong>

<strong>POU(L,Iength,dir_path)</strong>

<sup>—-</sup>-III■

<strong>_…–</strong>

<strong>PDU(1,1ength,list_of_files) </strong><strong>.4-<sup>—–</sup></strong>

<strong>Fig 6: List Directory</strong>