---
title: 샘플 공급자의 SQL 생성
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 88223930b65ccec9d030104c62d8b4b2e77ddbe2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079424"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="21486-102">샘플 공급자의 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="21486-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="21486-103">합니다 [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) 지 원하는 ADO.NET 데이터 공급자의 새 구성 요소를 보여 줍니다는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="21486-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="21486-104">샘플 공급자는 SQL Server 2005 데이터베이스와 작동하며 System.Data.SqlClient ADO.NET 2.0 데이터 공급자에 대한 래퍼로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="21486-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="21486-105">샘플 공급자의 SQL 생성 모듈(DmlSqlGenerator.cs 파일을 제외하고 SQL Generation 폴더에 있음)은 DbQueryCommandTree 입력을 사용하고 단일 SQL SELECT 문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="21486-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21486-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="21486-106">In This Section</span></span>  
 <span data-ttu-id="21486-107">이 단원에 포함된 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21486-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="21486-108">아키텍처 및 디자인</span><span class="sxs-lookup"><span data-stu-id="21486-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="21486-109">연습: SQL 생성</span><span class="sxs-lookup"><span data-stu-id="21486-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="21486-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="21486-110">See also</span></span>

- [<span data-ttu-id="21486-111">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="21486-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
