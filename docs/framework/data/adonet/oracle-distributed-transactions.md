---
description: '자세한 정보: Oracle 분산 트랜잭션'
title: Oracle 분산 트랜잭션
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: d0c41920f18e0f56ebdf57e3cb82cf829a59c450
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786175"
---
# <a name="oracle-distributed-transactions"></a>Oracle 분산 트랜잭션

<xref:System.Data.OracleClient.OracleConnection> 개체는 트랜잭션이 활성화되어 있다고 판단할 경우 기존 분산 트랜잭션에 자동으로 인리스트먼트합니다. 자동 트랜잭션 인리스트먼트는 연결이 열려 있거나 연결 풀에서 검색되는 경우에 발생합니다. 다음을 수행하여 기존 트랜잭션에서 자동 인리스트먼트를 비활성화할 수 있습니다.  
  
```csharp  
Enlist=false  
```  
  
 위의 코드를 <xref:System.Data.OracleClient.OracleConnection>에 대한 연결 문자열 매개 변수로 지정합니다.  
  
## <a name="see-also"></a>참고 항목

- [Oracle 및 ADO.NET](oracle-and-adonet.md)
- [ADO.NET 개요](ado-net-overview.md)
