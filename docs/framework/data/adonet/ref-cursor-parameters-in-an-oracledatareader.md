---
title: OracleDataReader의 REF CURSOR 매개 변수
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 801dff0f-2508-45aa-9416-f45d6887740c
ms.openlocfilehash: 32285c78bfe8e8c24e70109cbf82a63a4d42848e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166471"
---
# <a name="ref-cursor-parameters-in-an-oracledatareader"></a><span data-ttu-id="25b44-102">OracleDataReader의 REF CURSOR 매개 변수</span><span class="sxs-lookup"><span data-stu-id="25b44-102">REF CURSOR Parameters in an OracleDataReader</span></span>

<span data-ttu-id="25b44-103">이 Microsoft Visual Basic 예제에서는 REF CURSOR 매개 변수를 반환하는 PL/SQL 저장 프로시저를 실행하고 값을 <xref:System.Data.OracleClient.OracleDataReader>로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="25b44-103">This Microsoft Visual Basic example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
```vb  
Private Sub Button1_Click(ByVal sender As Object, _  
  ByVal e As System.EventArgs) Handles Button1.Click  
  
  Dim connString As New String(_  
      "Data Source=Oracle9i;User ID=scott;Password=tiger;")  
  Using conn As New OracleConnection(connString)  
    Dim cmd As New OracleCommand()  
    Dim rdr As OracleDataReader  
  
    conn.Open()  
    cmd.Connection = conn  
    cmd.CommandText = "CURSPKG.OPEN_ONE_CURSOR"  
    cmd.CommandType = CommandType.StoredProcedure  
    cmd.Parameters.Add(New OracleParameter(  
      "N_EMPNO", OracleType.Number)).Value = 7369  
    cmd.Parameters.Add(New OracleParameter(  
      "IO_CURSOR", OracleType.Cursor)).Direction = ParameterDirection.Output  
  
    rdr = cmd.ExecuteReader()  
    While (rdr.Read())  
        REM do something with the values  
    End While  
  
    rdr.Close()  
  End Using  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="25b44-104">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25b44-104">See also</span></span>

- [<span data-ttu-id="25b44-105">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="25b44-105">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)
- [<span data-ttu-id="25b44-106">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="25b44-106">ADO.NET Overview</span></span>](ado-net-overview.md)
