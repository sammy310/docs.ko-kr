---
description: SQL Server Compact 및 LINQ to SQL에 대해 자세히 알아보세요.
title: SQL Server Compact 및 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: ae7965db1685d7682b643662df8fb1c1376a7154
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803713"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="76609-103">SQL Server Compact 및 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="76609-103">SQL Server Compact and LINQ to SQL</span></span>

<span data-ttu-id="76609-104">SQL Server Compact는 Visual Studio와 함께 설치 되는 기본 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="76609-104">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="76609-105">자세한 내용은 [SQL Server Compact 사용 (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76609-105">For more information, see [Using SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="76609-106">이 항목에서는 사용, 구성, 기능 집합 및 지원 범위의 주요 차이점에 대해 간략하게 설명 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76609-106">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="76609-107">LINQ to SQL과 관련된 SQL Server Compact의 특성</span><span class="sxs-lookup"><span data-stu-id="76609-107">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  

 <span data-ttu-id="76609-108">기본적으로 SQL Server Compact는 모든 Visual Studio 버전에 대해 설치 되므로에서 사용할 수 있도록 개발 컴퓨터에서 사용할 수 있습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76609-108">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="76609-109">그러나 SQL Server Compact를 사용 하는 응용 프로그램의 배포는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL Server 응용 프로그램의 경우와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="76609-109">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="76609-110">SQL Server Compact는 .NET Framework의 일부가 아니므로 애플리케이션과 함께 패키지하거나 Microsoft 사이트에서 별도로 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76609-110">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="76609-111">다음 특성에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="76609-111">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="76609-112">SQL Server Compact는 데이터베이스 파일(.sdf 확장명)에 대해 직접 사용할 수 있는 DLL로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="76609-112">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="76609-113">SQL Server Compact는 클라이언트 응용 프로그램과 동일한 프로세스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="76609-113">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="76609-114">따라서 SQL Server Compact과의 통신 효율성이 SQL Server와의 통신 보다 훨씬 더 높을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76609-114">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="76609-115">반면, SQL Server Compact에서는 관리 코드와 비관리 코드 간에 상호 운용성이 요구되므로 부수적인 비용이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="76609-115">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="76609-116">SQL Server Compact DLL의 크기가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="76609-116">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="76609-117">이로 인해 전체 애플리케이션 크기가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="76609-117">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="76609-118">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임 및 SQLMetal 명령줄 도구에서 SQL Server Compact를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="76609-118">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="76609-119">개체 관계형 디자이너에서 SQL Server Compact를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76609-119">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="76609-120">기능 집합</span><span class="sxs-lookup"><span data-stu-id="76609-120">Feature Set</span></span>  

 <span data-ttu-id="76609-121">SQL Server Compact 기능 집합은 응용 프로그램에 영향을 줄 수 있는 다음과 같은 방법으로 SQL Server 기능 집합 보다 훨씬 더 간단 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76609-121">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="76609-122">SQL Server Compact에서는 저장 프로시저나 뷰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76609-122">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="76609-123">SQL Server Compact에서는 데이터 형식 및 SQL 함수의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="76609-123">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="76609-124">SQL Server Compact에서는 SQL 구문의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="76609-124">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="76609-125">SQL Server Compact에서는 최소한의 최적화 프로그램을 제공하므로</span><span class="sxs-lookup"><span data-stu-id="76609-125">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="76609-126">일부 쿼리의 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76609-126">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="76609-127">SQL Server Compact는 부분 신뢰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76609-127">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76609-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76609-128">See also</span></span>

- [<span data-ttu-id="76609-129">참조</span><span class="sxs-lookup"><span data-stu-id="76609-129">Reference</span></span>](reference.md)
