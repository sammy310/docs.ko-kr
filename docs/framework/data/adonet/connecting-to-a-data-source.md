---
title: 데이터 원본에 연결
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: b9e69b029ad37c583e51c219f87ff9d7d8e7315c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203776"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>데이터 원본에 연결(ADO.NET)

ADO.NET에서는 연결 문자열에 필요한 인증 정보를 제공 하 여 **연결** 개체를 사용 하 여 특정 데이터 원본에 연결 합니다. 사용 하는 **연결** 개체는 데이터 원본 유형에 따라 달라 집니다.  
  
 .NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [연결 설정](establishing-the-connection.md)\
 **Connection** 개체를 사용 하 여 데이터 원본에 대 한 연결을 설정 하는 방법을 설명 합니다.  
  
 [연결 이벤트](connection-events.md)\
 **InfoMessage** 이벤트를 사용 하 여 데이터 소스에서 정보 메시지를 검색 하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참고 항목

- [연결 문자열](connection-strings.md)
- [연결 풀링](connection-pooling.md)
- [명령 및 매개 변수](commands-and-parameters.md)
- [DataAdapters 및 DataReaders](dataadapters-and-datareaders.md)
- [트랜잭션 및 동시성](transactions-and-concurrency.md)
- [ADO.NET 개요](ado-net-overview.md)
