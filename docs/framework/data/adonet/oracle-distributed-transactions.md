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
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="33770-103">Oracle 분산 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="33770-103">Oracle Distributed Transactions</span></span>

<span data-ttu-id="33770-104"><xref:System.Data.OracleClient.OracleConnection> 개체는 트랜잭션이 활성화되어 있다고 판단할 경우 기존 분산 트랜잭션에 자동으로 인리스트먼트합니다.</span><span class="sxs-lookup"><span data-stu-id="33770-104">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="33770-105">자동 트랜잭션 인리스트먼트는 연결이 열려 있거나 연결 풀에서 검색되는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="33770-105">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="33770-106">다음을 수행하여 기존 트랜잭션에서 자동 인리스트먼트를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33770-106">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```csharp  
Enlist=false  
```  
  
 <span data-ttu-id="33770-107">위의 코드를 <xref:System.Data.OracleClient.OracleConnection>에 대한 연결 문자열 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33770-107">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33770-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33770-108">See also</span></span>

- [<span data-ttu-id="33770-109">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="33770-109">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="33770-110">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="33770-110">ADO.NET Overview</span></span>](ado-net-overview.md)
