---
title: 프로그래밍 가이드
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 102d2ecba162e19258b707c1c902c29b0a7f2f02
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490038"
---
# <a name="programming-guide"></a><span data-ttu-id="17f97-102">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="17f97-102">Programming Guide</span></span>
<span data-ttu-id="17f97-103">이 단원에는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 생성하고 사용하는 방법에 대한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="17f97-104">Visual Studio를 사용 하는 경우 사용할 수도 있습니다는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 이러한 동일한 작업을 수행 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-104">If you are using Visual Studio, you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="17f97-105">Microsoft Docs 특정 문제를 검색할 수도 있습니다 및 참여할 수 있습니다 합니다 [LINQ 포럼](https://go.microsoft.com/fwlink/?LinkId=76488)전문가 함께 보다 복잡 한 주제를 자세히 논의할 수 있는, 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="17f97-106">마지막으로, 합니다 [LINQ to SQL:.net language-integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) 백서에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술, Visual Basic 및 C# 코드 예제를 사용 하 여 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17f97-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="17f97-107">In This Section</span></span>  
 [<span data-ttu-id="17f97-108">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="17f97-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="17f97-109">개체 모델을 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="17f97-110">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="17f97-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="17f97-111"><xref:System.Data.Linq.DataContext> 개체를 데이터베이스에 대한 통로로 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="17f97-112">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="17f97-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="17f97-113">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 쿼리를 실행하는 방법에 대해 설명하고 여러 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="17f97-114">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="17f97-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="17f97-115">데이터베이스에서 데이터를 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="17f97-116">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="17f97-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="17f97-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트 디버깅에서 사용 가능한 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="17f97-118">배경 정보</span><span class="sxs-lookup"><span data-stu-id="17f97-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="17f97-119">고급 사용자를 위한 동시성 충돌 해결 방법, 새로운 데이터베이스 생성 등과 같은 추가 항목도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="17f97-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="17f97-120">Related Sections</span></span>  
 [<span data-ttu-id="17f97-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="17f97-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="17f97-122">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에 대해 설명하고 기능을 보여 주는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="17f97-123">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="17f97-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="17f97-124">저장 프로시저를 사용하는 방법을 보여 주는 항목에 대한 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="17f97-125">LINQ 소개 (C#)</span><span class="sxs-lookup"><span data-stu-id="17f97-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="17f97-126">리소스를 사용 하 여 SQL에 LINQ를 배우는데 도움이 제공 C#입니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="17f97-127">LINQ 소개(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17f97-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="17f97-128">Visual Basic을 사용 하 여 SQL LINQ를 배우는데 도움이 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f97-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
