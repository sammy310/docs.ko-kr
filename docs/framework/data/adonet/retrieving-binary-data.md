---
title: 이진 데이터 검색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: c914a9b0780e2e87e177502b0f9faff0e7c4b617
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149052"
---
# <a name="retrieving-binary-data"></a>이진 데이터 검색
기본적으로 **DataReader는** 전체 데이터 행을 사용할 수 있는 즉시 들어오는 데이터를 행으로 로드합니다. 그러나 BLOB(Binary Large Object)는 단일 행에 포함할 수 없는 기가바이트 데이터를 포함할 수 있으므로 다르게 처리되어야 합니다. **Command.ExecuteReader** 메서드에는 <xref:System.Data.CommandBehavior> **인수가 수행되어 DataReader**의 기본 동작을 수정하는 오버로드가 있습니다. **ExecuteReader** <xref:System.Data.CommandBehavior.SequentialAccess> 메서드를 전달하여 **DataReader의** 기본 동작을 수정하여 데이터 행을 로드하는 대신 수신될 때 데이터를 순차적으로 로드할 수 있습니다. 이것은 BLOB 또는 기타 대형 데이터 구조를 로드하는 데 적합합니다. 이 동작은 데이터 소스에 따라 다를 수 있습니다. 예를 들어, Microsoft Access에서 BLOB를 반환할 경우에는 BLOB를 받을 때 데이터를 순서대로 로드하는 것이 아니라 전체 BLOB를 메모리에 로드합니다.  
  
 **DataReader를** 사용하도록 설정할 때 **SequenceAccess를**사용할 때 반환된 필드에 액세스하는 순서를 기록하는 것이 중요합니다. 전체 행을 사용할 수 있는 즉시 로드하는 **DataReader의**기본 동작을 사용하면 다음 행을 읽을 때까지 원하는 순서로 반환되는 필드에 액세스할 수 있습니다. 그러나 **시퀀셜 액세스를** 사용하는 경우 **DataReader에서** 반환하는 필드에 순서대로 액세스해야 합니다. 예를 들어, 쿼리에서 세 열을 반환하고 그 셋째 열이 BLOB이면 셋째 필드의 BLOB 데이터에 액세스하기 전에 첫째와 둘째 필드의 값을 반환해야 합니다. 첫째나 둘째 필드에 액세스하기 전에 셋째 필드에 액세스하면 첫째와 둘째 필드 값을 더 이상 사용할 수 없습니다. **이는 SequenceAccess가** 데이터를 순서대로 반환하도록 **DataReader를** 수정했으며 **DataReader가** 데이터를 읽은 후 데이터를 사용할 수 없기 때문입니다.  
  
 BLOB 필드의 데이터에 액세스할 때 데이터로 배열을 채우는 **DataReader의**GetBytes 또는 **GetChars** 형식의 접근자(getBytes)를 사용합니다. **GetBytes** 문자 데이터에 **GetString을** 사용할 수도 있습니다. 그러나. 하지만 시스템 리소스를 절약하기 위해 전체 BLOB 값을 단일 문자열 변수에 로드하지 않을 수도 있습니다. 대신 반환될 데이터의 특정 버퍼 크기와 반환된 데이터에서 읽은 첫째 바이트 또는 문자의 시작 위치를 지정할 수 있습니다. **GetBytes** 및 **GetChars** `long` 반환 된 바이트 또는 문자 수를 나타내는 값을 반환 합니다. null 배열을 **GetBytes** 또는 **GetChars에**전달하는 경우 반환되는 긴 값은 BLOB의 총 바이트 또는 문자 수입니다. 배열의 인덱스를 읽고 있는 데이터의 시작 위치로서 선택적으로 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 Microsoft SQL Server의 pubs 샘플 데이터베이스에서 게시자 ID 및 **로고를 반환합니다.** 게시자 ID(`pub_id`)는 문자 필드이고 로고는 BLOB 이미지입니다. **로고** 필드는 비트맵이므로 예제에서는 **GetBytes**를 사용하여 이진 데이터를 반환합니다. 필드에 순차적으로 액세스해야 하므로 현재 데이터 행에 대해 게시자 ID가 로고에 앞서 액세스됩니다.  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte
' The bytes returned from GetBytes.  
Dim retval As Long
' The starting position in the BLOB output.  
Dim startIndex As Long = 0
  
' The publisher id to use in the file name.  
Dim pubID As String = ""
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;
  
// Size of the BLOB buffer.  
int bufferSize = 100;
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];
// The bytes returned from GetBytes.  
long retval;
// The starting position in the BLOB output.  
long startIndex = 0;
  
// The publisher id to use in the file name.  
string pubID = "";
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a>참고 항목

- [SQL 서버 바이너리 및 대값 데이터](./sql/sql-server-binary-and-large-value-data.md)
- [ADO.NET 개요](ado-net-overview.md)
