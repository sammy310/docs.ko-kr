---
title: 데이터 원본에 연결(ADO.NET)
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: c04624be758e4bc7c8b1981ad6a9dc44430d62b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879985"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>데이터 원본에 연결(ADO.NET)
ADO.NET 사용 하 여는 **연결** 개체에 연결 문자열에 필요한 인증 정보를 제공 하 여 특정 데이터 원본에 연결 합니다. 합니다 **연결** 개체를 사용 하면 데이터 원본의 유형에 따라 다릅니다.  
  
 .NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [연결 설정](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 사용 하는 방법에 설명 합니다는 **연결** 개체 데이터 원본에 연결 합니다.  
  
 [연결 이벤트](../../../../docs/framework/data/adonet/connection-events.md)  
 사용 하는 방법에 설명 합니다는 **InfoMessage** 이벤트 데이터 원본에서 정보 메시지를 검색 합니다.  
  
## <a name="see-also"></a>참고자료

- [연결 문자열](../../../../docs/framework/data/adonet/connection-strings.md)
- [연결 풀링](../../../../docs/framework/data/adonet/connection-pooling.md)
- [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [DataAdapter 및 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
