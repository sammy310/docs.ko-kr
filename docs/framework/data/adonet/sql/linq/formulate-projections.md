---
description: '자세히 알아보기: 프로젝션 작성'
title: 프로젝션 작성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 591bc175426f08aa4273376e4c5efe370d2be756
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672077"
---
# <a name="formulate-projections"></a><span data-ttu-id="b3fc2-103">프로젝션 작성</span><span class="sxs-lookup"><span data-stu-id="b3fc2-103">Formulate Projections</span></span>

<span data-ttu-id="b3fc2-104">다음 예에서는 `select` c #의 문과 `Select` Visual Basic 문을 다른 기능과 결합 하 여 쿼리 프로젝션을 구성할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-104">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3fc2-105">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-105">Example</span></span>  

 <span data-ttu-id="b3fc2-106">다음 예제에서는 `Select` Visual Basic (c #의 절)에서 절을 사용 하 여 `select` 에 대 한 연락처 이름의 시퀀스를 반환 합니다 `Customers` .</span><span class="sxs-lookup"><span data-stu-id="b3fc2-106">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-107">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-107">Example</span></span>  

 <span data-ttu-id="b3fc2-108">다음 예제에서는 `Select` Visual Basic ( `select` c #의 절) 및 *익명 형식* 에서 절을 사용 하 여에 대 한 연락처 이름 및 전화 번호의 시퀀스를 반환 합니다 `Customers` .</span><span class="sxs-lookup"><span data-stu-id="b3fc2-108">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-109">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-109">Example</span></span>  

 <span data-ttu-id="b3fc2-110">다음 예제에서는 `Select` Visual Basic ( `select` c #의 절) 및 *익명 형식* 에서 절을 사용 하 여 직원에 대 한 이름 및 전화 번호의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-110">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="b3fc2-111">결과 시퀀스에서 `FirstName`과 `LastName` 필드는 단일 필드(`Name`)로 결합되고 `HomePhone` 필드는 `Phone`으로 이름이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-111">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-112">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-112">Example</span></span>  

 <span data-ttu-id="b3fc2-113">다음 예제에서는 `Select` Visual Basic ( `select` c #의 절) 및 *무명 형식의* 절을 사용 하 여 모든의 시퀀스 `ProductID` 와 이라는 계산 된 값을 반환 `HalfPrice` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-113">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="b3fc2-114">이 값은 2로 나누어진 `UnitPrice`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-114">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-115">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-115">Example</span></span>  

 <span data-ttu-id="b3fc2-116">다음 예에서는 `Select` Visual Basic ( `select` c #의 절)과 *조건문* 을 사용 하 여 제품 이름 및 제품 가용성의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-116">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-117">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-117">Example</span></span>  

 <span data-ttu-id="b3fc2-118">다음 예제에서는 Visual Basic `Select` 절 ( `select` c #의 절)과 *알려진 형식* (Name)을 사용 하 여 직원 이름의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-118">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-119">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-119">Example</span></span>  

 <span data-ttu-id="b3fc2-120">다음 예제에서는 `Select` 및 `Where` ( `select` c #의 경우) Visual Basic에서 및를 사용 하 여 `where` 런던에 있는 고객에 대 한 연락처 이름의 *필터링 된 시퀀스* 를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-120">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-121">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-121">Example</span></span>  

 <span data-ttu-id="b3fc2-122">다음 예제에서는 `Select` Visual Basic ( `select` c #의 절) 및 *익명 형식* 에서 절을 사용 하 여 고객에 대 한 데이터의 모양이 지정 된 *하위 집합* 을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-122">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="b3fc2-123">예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-123">Example</span></span>  

 <span data-ttu-id="b3fc2-124">다음 예제에서는 중첩된 쿼리를 사용하여 다음 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-124">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="b3fc2-125">모든 주문의 시퀀스와 해당 `OrderID`입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-125">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="b3fc2-126">할인이 있는 주문 항목에 대한 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-126">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="b3fc2-127">운송 비용이 포함되지 않은 총 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fc2-127">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="b3fc2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3fc2-128">See also</span></span>

- [<span data-ttu-id="b3fc2-129">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="b3fc2-129">Query Examples</span></span>](query-examples.md)
