---
description: User-Defined 함수에 대해 자세히 알아보세요.
title: 사용자 정의 함수
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: d27abd78e15ad6cb5ce4e9440ac425159a0b5bdc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680943"
---
# <a name="user-defined-functions"></a><span data-ttu-id="c3326-103">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="c3326-103">User-Defined Functions</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c3326-104">에서는 개체 모델에 메서드를 사용하여 사용자 정의 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-104">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="c3326-105">필요한 위치에 <xref:System.Data.Linq.Mapping.FunctionAttribute> 특성과 <xref:System.Data.Linq.Mapping.ParameterAttribute> 특성을 적용하여 메서드를 함수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-105">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="c3326-106">자세한 내용은 [LINQ to SQL 개체 모델](the-linq-to-sql-object-model.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c3326-106">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="c3326-107"><xref:System.InvalidOperationException>을 방지하려면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 사용자 정의 함수는 다음 폼 중 하나에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-107">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="c3326-108">올바른 매핑 특성이 있는 메서드 호출로 래핑된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-108">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="c3326-109">자세한 내용은 [특성 기반 매핑](attribute-based-mapping.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c3326-109">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="c3326-110">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 관련된 정적 SQL 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-110">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="c3326-111">.NET Framework 메서드에서 지 원하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-111">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="c3326-112">이 단원의 항목에서는 코드를 사용자가 직접 작성하는 경우 애플리케이션에서 이러한 메서드를 만들어 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-112">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="c3326-113">Visual Studio를 사용 하는 개발자는 일반적으로 개체 관계형 디자이너를 사용 하 여 사용자 정의 함수를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-113">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3326-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c3326-114">In This Section</span></span>  

 [<span data-ttu-id="c3326-115">방법: 스칼라 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="c3326-115">How to: Use Scalar-Valued User-Defined Functions</span></span>](how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="c3326-116">스칼라 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-116">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="c3326-117">방법: 테이블 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="c3326-117">How to: Use Table-Valued User-Defined Functions</span></span>](how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="c3326-118">표 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-118">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="c3326-119">방법: 사용자 정의 함수 인라인 호출</span><span class="sxs-lookup"><span data-stu-id="c3326-119">How to: Call User-Defined Functions Inline</span></span>](how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="c3326-120">함수를 인라인 호출하는 방법과 인라인 호출을 통한 실행의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3326-120">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
