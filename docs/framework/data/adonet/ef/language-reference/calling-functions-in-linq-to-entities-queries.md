---
title: LINQ to Entities 쿼리에서 함수 호출
description: 이러한 문서를 사용 하 여 EntityFunctions SqlFunctions 클래스가 Entity Framework의 일부로 정식 함수와 데이터베이스 함수에 액세스를 제공 하는 방법을 확인할 수 있습니다.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: faa6406713592f10e5e7371cd73f29bec4b03b7b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286859"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="77b54-103">LINQ to Entities 쿼리에서 함수 호출</span><span class="sxs-lookup"><span data-stu-id="77b54-103">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="77b54-104">이 단원의 항목에서는 LINQ to Entities 쿼리에서 함수를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77b54-104">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="77b54-105"><xref:System.Data.Objects.EntityFunctions> 및 <xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스를 사용하여 Entity Framework의 일부인 정식 함수와 데이터베이스 함수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77b54-105">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="77b54-106">자세한 내용은 [방법: 정식 함수 호출](how-to-call-canonical-functions.md) 및 [방법: 데이터베이스 함수 호출](how-to-call-database-functions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77b54-106">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="77b54-107">사용자 지정 함수를 호출하는 과정은 다음의 기본적인 세 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="77b54-107">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="77b54-108">개념적 모델에서 함수를 정의하거나 스토리지 모델에서 함수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="77b54-108">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="77b54-109">애플리케이션에 메서드를 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 이 메서드를 모델의 함수에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="77b54-109">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="77b54-110">LINQ to Entities 쿼리에서 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="77b54-110">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="77b54-111">자세한 내용은 이 단원의 해당 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77b54-111">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77b54-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="77b54-112">In This Section</span></span>  
 [<span data-ttu-id="77b54-113">방법: 호출 정식 함수</span><span class="sxs-lookup"><span data-stu-id="77b54-113">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="77b54-114">방법: 데이터베이스 함수 호출</span><span class="sxs-lookup"><span data-stu-id="77b54-114">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="77b54-115">방법: 사용자 지정 데이터베이스 함수 호출</span><span class="sxs-lookup"><span data-stu-id="77b54-115">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="77b54-116">방법: 쿼리에서 모델 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="77b54-116">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="77b54-117">방법: 개체 메서드로 모델 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="77b54-117">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="77b54-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77b54-118">See also</span></span>

- [<span data-ttu-id="77b54-119">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="77b54-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="77b54-120">정식 함수</span><span class="sxs-lookup"><span data-stu-id="77b54-120">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="77b54-121">[.edmx 파일 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="77b54-121">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="77b54-122">[방법: 개념적 모델의 사용자 지정 함수 정의](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="77b54-122">[How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
