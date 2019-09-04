---
title: 샘플 공급자의 SQL 생성
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: d0e058cdc4dd3f7a1a04ab6eea5acf4d3deabb89
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248504"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="0eb59-102">샘플 공급자의 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="0eb59-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="0eb59-103">[Entity Framework 샘플 공급자](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) 는를 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]지 원하는 ADO.NET 데이터 공급자의 새로운 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0eb59-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="0eb59-104">샘플 공급자는 SQL Server 2005 데이터베이스와 작동하며 System.Data.SqlClient ADO.NET 2.0 데이터 공급자에 대한 래퍼로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb59-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="0eb59-105">샘플 공급자의 SQL 생성 모듈(DmlSqlGenerator.cs 파일을 제외하고 SQL Generation 폴더에 있음)은 DbQueryCommandTree 입력을 사용하고 단일 SQL SELECT 문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb59-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0eb59-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0eb59-106">In This Section</span></span>  
 <span data-ttu-id="0eb59-107">이 섹션에서는 다음 항목을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="0eb59-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="0eb59-108">아키텍처 및 디자인</span><span class="sxs-lookup"><span data-stu-id="0eb59-108">Architecture and Design</span></span>](architecture-and-design.md)  
  
 [<span data-ttu-id="0eb59-109">연습: SQL 생성</span><span class="sxs-lookup"><span data-stu-id="0eb59-109">Walkthrough: SQL Generation</span></span>](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="0eb59-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="0eb59-110">See also</span></span>

- [<span data-ttu-id="0eb59-111">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="0eb59-111">SQL Generation</span></span>](sql-generation.md)
