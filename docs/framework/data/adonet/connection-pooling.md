---
title: 연결 풀링
description: ADO.NET에서 데이터 원본에 대 한 연결을 여는 데 드는 비용을 최소화 하기 위해 사용 하는 최적화 방법인 연결 풀링을 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: f16b3ba733cce4a1efe72e3f4eee48a431a96fb7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198719"
---
# <a name="connection-pooling"></a>연결 풀링

데이터 소스에 연결하는 작업은 시간이 많이 걸릴 수 있습니다. 연결을 여는 비용을 최소화 하기 위해 ADO.NET에서는 연결 *풀링*이라는 최적화 기법을 사용 하 여 연결을 반복적으로 열고 닫는 데 드는 비용을 최소화 합니다. 연결 풀링은 .NET Framework 데이터 공급자마다 각각 다른 방식으로 처리됩니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [SQL Server 연결 풀링(ADO.NET)](sql-server-connection-pooling.md)  
 연결 풀링의 개요를 제공 하 고 SQL Server 연결 풀링이 작동 하는 방식을 설명 합니다.  
  
 [OLE DB, ODBC 및 Oracle 연결 풀링](ole-db-odbc-and-oracle-connection-pooling.md)  
 .NET Framework Data Provider for OLE DB, .NET Framework Data Provider for ODBC 및 .NET Framework Data Provider for Oracle의 연결 풀링에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목

- [ADO.NET에서 데이터 검색 및 수정](retrieving-and-modifying-data.md)
- [ADO.NET 개요](ado-net-overview.md)
