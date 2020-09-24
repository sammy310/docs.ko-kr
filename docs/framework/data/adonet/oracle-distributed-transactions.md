---
title: Oracle 분산 트랜잭션
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: a21134c3283d3d9d8d7660eecaaf74d60ecf6662
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166523"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="04089-102">Oracle 분산 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="04089-102">Oracle Distributed Transactions</span></span>

<span data-ttu-id="04089-103"><xref:System.Data.OracleClient.OracleConnection> 개체는 트랜잭션이 활성화되어 있다고 판단할 경우 기존 분산 트랜잭션에 자동으로 인리스트먼트합니다.</span><span class="sxs-lookup"><span data-stu-id="04089-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="04089-104">자동 트랜잭션 인리스트먼트는 연결이 열려 있거나 연결 풀에서 검색되는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="04089-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="04089-105">다음을 수행하여 기존 트랜잭션에서 자동 인리스트먼트를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04089-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```csharp  
Enlist=false  
```  
  
 <span data-ttu-id="04089-106">위의 코드를 <xref:System.Data.OracleClient.OracleConnection>에 대한 연결 문자열 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04089-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04089-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04089-107">See also</span></span>

- [<span data-ttu-id="04089-108">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="04089-108">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="04089-109">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="04089-109">ADO.NET Overview</span></span>](ado-net-overview.md)
