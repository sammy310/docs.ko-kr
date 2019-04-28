---
title: OracleDataReader를 사용하여 여러 Multiple REF CURSOR에서 데이터 검색
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 361e9bd4-447d-44b7-8629-3c11f1a7ffbb
ms.openlocfilehash: a3e2298341d5ea938e0d13df09d3428837f53cec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664274"
---
# <a name="retrieving-data-from-multiple-ref-cursors-using-an-oracledatareader"></a>OracleDataReader를 사용하여 여러 Multiple REF CURSOR에서 데이터 검색
이 Microsoft Visual Basic 예제에서는 REF CURSOR 매개 변수 두 개를 반환하는 PL/SQL 저장 프로시저를 실행하고 <xref:System.Data.OracleClient.OracleDataReader>를 사용하여 값을 읽습니다.  
  
```vb  
Private Sub Button1_Click( _  
  ByVal sender As Object, ByVal e As System.EventArgs)  _  
  Handles Button1.Click  
  
  Dim connString As New String( _  
      "Data Source=Oracle9i;User ID=scott;Password=tiger;")  
  Using conn As New OracleConnection(connString)  
    Dim cmd As New OracleCommand()  
    Dim rdr As OracleDataReader  
  
    conn.Open()  
    cmd.Connection = conn  
    cmd.CommandText = "CURSPKG.OPEN_TWO_CURSORS"  
    cmd.CommandType = CommandType.StoredProcedure  
    cmd.Parameters.Add(New OracleParameter( _  
      "EMPCURSOR", OracleType.Cursor)).Direction = _  
      ParameterDirection.Output  
    cmd.Parameters.Add(New OracleParameter(_  
      "DEPTCURSOR", OracleType.Cursor)).Direction = _  
      ParameterDirection.Output  
  
    rdr = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
    While (rdr.Read())  
        REM do something with the values from the EMP table   
    End While  
  
    rdr.NextResult()  
    While (rdr.Read())  
        REM do something with the values from the DEPT table   
    End While  
    rdr.Close()  
  End Using  
End Sub   
```  
  
## <a name="see-also"></a>참고자료

- [Oracle REF CURSOR](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
