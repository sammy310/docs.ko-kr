---
title: 프로그래밍 가이드
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 0746d14d7be0b67bc9966ae0c5a4af0a3226c1e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546564"
---
# <a name="programming-guide"></a><span data-ttu-id="4049b-102">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4049b-102">Programming Guide</span></span>
<span data-ttu-id="4049b-103">이 단원에는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 생성하고 사용하는 방법에 대한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="4049b-104">Visual Studio를 사용 하는 경우 개체 관계형 디자이너를 사용 하 여 이러한 여러 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="4049b-105">또한 특정 문제에 대 한 Microsoft Docs 검색할 수 있으며, 전문가와 함께 보다 복잡 한 항목을 자세히 논의할 수 있는 [LINQ 포럼](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="4049b-106">마지막으로 [LINQ to SQL: 관계형 데이터에 대 한 .Net 언어 통합 쿼리](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) 백서 정보 기술에 대 한 자세한 내용은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Visual Basic 및 c # 코드 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4049b-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4049b-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4049b-107">In This Section</span></span>  
 [<span data-ttu-id="4049b-108">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="4049b-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="4049b-109">개체 모델을 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="4049b-110">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="4049b-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="4049b-111"><xref:System.Data.Linq.DataContext> 개체를 데이터베이스에 대한 통로로 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="4049b-112">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="4049b-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="4049b-113">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 쿼리를 실행하는 방법에 대해 설명하고 여러 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="4049b-114">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="4049b-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="4049b-115">데이터베이스에서 데이터를 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="4049b-116">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="4049b-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="4049b-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트 디버깅에서 사용 가능한 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="4049b-118">배경 정보</span><span class="sxs-lookup"><span data-stu-id="4049b-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="4049b-119">고급 사용자를 위한 동시성 충돌 해결 방법, 새로운 데이터베이스 생성 등과 같은 추가 항목도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4049b-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4049b-120">Related Sections</span></span>  
 [<span data-ttu-id="4049b-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4049b-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="4049b-122">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에 대해 설명하고 기능을 보여 주는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="4049b-123">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="4049b-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="4049b-124">저장 프로시저를 사용하는 방법을 보여 주는 항목에 대한 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="4049b-125">LINQ 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="4049b-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="4049b-126">C #을 사용 하 여 LINQ to SQL에 대해 알아보는 데 도움이 되는 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="4049b-127">LINQ 소개(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4049b-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="4049b-128">Visual Basic를 사용 하 LINQ to SQL에 대 한 자세한 정보를 제공 하는 데 유용한 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4049b-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
