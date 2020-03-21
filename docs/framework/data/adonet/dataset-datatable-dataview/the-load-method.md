---
title: 로드 메서드
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150729"
---
# <a name="the-load-method"></a>로드 메서드
<xref:System.Data.DataTable.Load%2A> 메서드를 사용하여 데이터 소스의 행과 함께 <xref:System.Data.DataTable>을 로드할 수 있습니다. 이것은 가장 간단한 형태로 단일 매개 변수인 **DataReader를**허용하는 오버로드된 메서드입니다. 이 양식에서는 단순히 행으로 **DataTable을** 로드합니다. 선택적으로 **LoadOption** 매개 변수를 지정하여 **DataTable**에 데이터가 추가되는 방법을 제어할 수 있습니다.  
  
 **LoadOption** 매개 변수는 **DataTable에** 데이터 원본의 들어오는 데이터가 테이블에 있는 데이터와 결합되는 방법을 설명하기 때문에 데이터 테이블이 이미 포함된 경우에 특히 유용합니다. 예를 **들어, PreserveCurrentValues(기본값)는** 행이 **DataTable에** **추가된** 것으로 표시된 **경우, 원본** 값 또는 각 열이 데이터 원본에서 일치하는 행의 내용으로 설정되도록 지정합니다. **현재** 값은 행이 추가될 때 할당된 값을 유지하고 행의 **RowState가** **변경된**로 설정됩니다.  
  
 다음 표에서는 <xref:System.Data.LoadOption> 열거형 값에 대해 간략하게 설명합니다.  
  
|LoadOption 값|Description|  
|----------------------|-----------------|  
|**OverwriteRow**|들어오는 행이 **DataTable에**이미 있는 행과 동일한 **PrimaryKey** 값을 가지면 각 열의 **원본** 및 **현재** 값이 들어오는 행의 값으로 대체되고 **RowState** 속성이 **변경되지 않음으로**설정됩니다.<br /><br /> **DataTable에** 아직 존재하지 않는 데이터 원본의 행은 **변경되지 않음의** **RowState** 값으로 추가됩니다.<br /><br /> 이 옵션은 데이터 원본의 내용과 일치되도록 **DataTable의** 내용을 새로 고칩니다.|  
|**PreserveCurrentValues(기본값)**|들어오는 행이 **DataTable에**이미 있는 행과 동일한 **PrimaryKey** 값을 가지는 경우 **원래** 값은 들어오는 행의 내용으로 설정되고 **현재** 값은 변경되지 않습니다.<br /><br /> **RowState가** **추가또는** **수정된**경우 **은 수정된**로 설정됩니다.<br /><br /> **RowState가** **삭제된**경우 은 **삭제된**상태로 유지됩니다.<br /><br /> **DataTable에** 아직 존재하지 않는 데이터 원본의 행이 추가되고 **RowState가** **변경되지 않음으로**설정됩니다.|  
|**UpdateCurrentValues**|들어오는 행이 **DataTable에**이미 있는 행과 동일한 **PrimaryKey** 값을 가지면 **현재** 값이 **원래** 값으로 복사되고 **현재** 값이 들어오는 행의 내용으로 설정됩니다.<br /><br /> **데이터 테이블의** **RowState가** **추가된**경우 **행 상태가** **추가된**상태로 유지됩니다. **수정됨** 또는 **삭제됨으로**표시된 행의 경우 **RowState가** **수정됩니다.**<br /><br /> **DataTable에** 아직 존재하지 않는 데이터 원본의 행이 추가되고 **RowState가** **추가된**로 설정됩니다.|  
  
 다음 샘플에서는 **Load** 메서드를 사용하여 **Northwind** 데이터베이스의 직원의 생일 목록을 표시합니다.  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a>참고 항목

- [DataTable에서 데이터 조작](manipulating-data-in-a-datatable.md)
- [ADO.NET 개요](../ado-net-overview.md)
