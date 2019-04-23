---
title: SQL Server Compact 및 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: db3f7aef082d965dc27b69f5a966ff038c0ffac0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145719"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="31ee8-102">SQL Server Compact 및 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="31ee8-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="31ee8-103">SQL Server Compact는 기본 데이터베이스를 Visual Studio를 사용 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="31ee8-104">자세한 내용은 [를 사용 하 여 SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110))합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="31ee8-105">이 항목의 사용, 구성, 기능 집합 및 범위의 주요 차이점을 간략하게 설명 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="31ee8-106">LINQ to SQL과 관련된 SQL Server Compact의 특성</span><span class="sxs-lookup"><span data-stu-id="31ee8-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="31ee8-107">기본적으로 SQL Server Compact는 모든 Visual Studio 버전에 대 한 설치 이므로 사용에 대 한 개발 컴퓨터에서 사용할 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="31ee8-108">하지만 SQL Server Compact를 사용 하는 응용 프로그램 배포 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 는 SQL 서버 응용 프로그램에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="31ee8-109">SQL Server Compact는 .NET Framework의 일부가 아니므로 응용 프로그램과 함께 패키지하거나 Microsoft 사이트에서 별도로 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="31ee8-110">다음 특성에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="31ee8-111">SQL Server Compact는 데이터베이스 파일(.sdf 확장명)에 대해 직접 사용할 수 있는 DLL로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="31ee8-112">SQL Server Compact는 클라이언트 응용 프로그램과 동일한 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="31ee8-113">SQL Server Compact와 통신 효율성 SQL Server와의 통신 보다 훨씬 더 높은 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="31ee8-114">반면에 SQL Server Compact는 해당 되므로 부수적인 비용이 발생을 사용 하 여 관리 및 비관리 코드 간의 상호 운용성을 필요지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="31ee8-115">SQL Server Compact DLL의 크기가 작습니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="31ee8-116">이로 인해 전체 응용 프로그램 크기가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="31ee8-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임 및 SQLMetal 명령줄 도구에서 SQL Server Compact를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="31ee8-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 SQL Server Compact를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="31ee8-119">기능 집합</span><span class="sxs-lookup"><span data-stu-id="31ee8-119">Feature Set</span></span>  
 <span data-ttu-id="31ee8-120">영향을 주는 다음과 같은 방법으로 SQL Server Compact 기능 집합은 SQL Server 기능 집합 보다 훨씬 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="31ee8-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="31ee8-121">SQL Server Compact에서는 저장 프로시저나 뷰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="31ee8-122">SQL Server Compact에서는 데이터 형식 및 SQL 함수의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="31ee8-123">SQL Server Compact에서는 SQL 구문의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="31ee8-124">SQL Server Compact에서는 최소한의 최적화 프로그램을 제공하므로</span><span class="sxs-lookup"><span data-stu-id="31ee8-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="31ee8-125">일부 쿼리의 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="31ee8-126">SQL Server Compact는 부분 신뢰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31ee8-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ee8-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="31ee8-127">See also</span></span>

- [<span data-ttu-id="31ee8-128">참조</span><span class="sxs-lookup"><span data-stu-id="31ee8-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
