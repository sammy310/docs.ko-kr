---
title: 데이터베이스 쿼리
ms.date: 03/30/2017
ms.assetid: eefb8b0c-ff07-4e86-a3d3-567479523fe9
ms.openlocfilehash: 3c48879d8e3ae699ef749fc14923358174010aae
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782076"
---
# <a name="querying-the-database"></a><span data-ttu-id="f9cc2-102">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="f9cc2-102">Querying the Database</span></span>
<span data-ttu-id="f9cc2-103">이 항목 그룹에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트에서 쿼리를 개발하고 실행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-103">This group of topics describes how to develop and execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9cc2-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f9cc2-104">In This Section</span></span>  
 [<span data-ttu-id="f9cc2-105">방법: 정보에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="f9cc2-105">How to: Query for Information</span></span>](how-to-query-for-information.md)  
 <span data-ttu-id="f9cc2-106">일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리가 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 쿼리와 기본적으로 어떻게 동일한지를 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-106">Briefly shows how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are basically the same as [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries generally.</span></span>  
  
 [<span data-ttu-id="f9cc2-107">방법: 읽기 전용으로 정보 검색</span><span class="sxs-lookup"><span data-stu-id="f9cc2-107">How to: Retrieve Information As Read-Only</span></span>](how-to-retrieve-information-as-read-only.md)  
 <span data-ttu-id="f9cc2-108">데이터 변경이 예정되어 있지 않은 경우 쿼리 성능을 향상시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-108">Describes how to increase query performance when no change to the data is planned.</span></span>  
  
 [<span data-ttu-id="f9cc2-109">방법: 검색 되는 관련 데이터의 양을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-109">How to: Control How Much Related Data Is Retrieved</span></span>](how-to-control-how-much-related-data-is-retrieved.md)  
 <span data-ttu-id="f9cc2-110">주 대상과 함께 검색되는 관련 데이터를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-110">Describes how to control which related data is retrieved together with the main target.</span></span>  
  
 [<span data-ttu-id="f9cc2-111">방법: 관련 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="f9cc2-111">How to: Filter Related Data</span></span>](how-to-filter-related-data.md)  
 <span data-ttu-id="f9cc2-112">하위 쿼리를 사용하여 관련 데이터를 검색하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-112">Describes how to retrieve related data by using a sub-query.</span></span>  
  
 [<span data-ttu-id="f9cc2-113">방법: 지연 된 로드 해제</span><span class="sxs-lookup"><span data-stu-id="f9cc2-113">How to: Turn Off Deferred Loading</span></span>](how-to-turn-off-deferred-loading.md)  
 <span data-ttu-id="f9cc2-114">지연된 로드를 해제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-114">Describes how to turn off deferred loading.</span></span>  
  
 [<span data-ttu-id="f9cc2-115">방법: SQL 쿼리 직접 실행</span><span class="sxs-lookup"><span data-stu-id="f9cc2-115">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)  
 <span data-ttu-id="f9cc2-116">SQL 언어를 사용하여 쿼리를 전송하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-116">Describes how to submit queries by using SQL language.</span></span>  
  
 [<span data-ttu-id="f9cc2-117">방법: 쿼리 저장 및 다시 사용</span><span class="sxs-lookup"><span data-stu-id="f9cc2-117">How to: Store and Reuse Queries</span></span>](how-to-store-and-reuse-queries.md)  
 <span data-ttu-id="f9cc2-118">쿼리를 한 번만 컴파일하는 방법과 서로 다른 매개 변수를 이용하여 여러 번 사용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-118">Describes how to compile a query one time but use it multiple times with different parameters.</span></span>  
  
 [<span data-ttu-id="f9cc2-119">방법: 쿼리에서 복합 키 처리</span><span class="sxs-lookup"><span data-stu-id="f9cc2-119">How to: Handle Composite Keys in Queries</span></span>](how-to-handle-composite-keys-in-queries.md)  
 <span data-ttu-id="f9cc2-120">연산자가 단일 인수만을 갖는 쿼리에서 둘 이상의 열을 포함하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-120">Describes how to include more than one column in a query where the operator takes only a single argument.</span></span>  
  
 [<span data-ttu-id="f9cc2-121">방법: 한 번에 여러 개체 검색</span><span class="sxs-lookup"><span data-stu-id="f9cc2-121">How to: Retrieve Many Objects At Once</span></span>](how-to-retrieve-many-objects-at-once.md)  
 <span data-ttu-id="f9cc2-122"><xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-122">Describes how to use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="f9cc2-123">방법: DataContext 수준에서 필터링</span><span class="sxs-lookup"><span data-stu-id="f9cc2-123">How to: Filter at the DataContext Level</span></span>](how-to-filter-at-the-datacontext-level.md)  
 <span data-ttu-id="f9cc2-124"><xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>의 다른 사용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-124">Describes another use of <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="f9cc2-125">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="f9cc2-125">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="f9cc2-126">다양한 쿼리 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9cc2-126">Provides many examples of queries.</span></span>
