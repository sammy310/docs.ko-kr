---
description: '자세히 알아보기: 초기화 식'
title: 초기화 식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 02f2ea6953291641516b1daffbb2b75931ffb3cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748559"
---
# <a name="initialization-expressions"></a><span data-ttu-id="2bb7e-103">초기화 식</span><span class="sxs-lookup"><span data-stu-id="2bb7e-103">Initialization Expressions</span></span>

<span data-ttu-id="2bb7e-104">초기화 식은 새 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-104">An initialization expression initializes a new object.</span></span> <span data-ttu-id="2bb7e-105">최신 C# 3.0 및 Visual Basic 9.0 초기화 식을 포함하여 대부분의 초기화 식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-105">Most initialization expressions are supported, including most new C# 3.0 and Visual Basic 9.0 initialization expressions.</span></span> <span data-ttu-id="2bb7e-106">LINQ to Entities 쿼리를 통해 다음 형식을 초기화하고 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-106">The following types can be initialized and returned by a LINQ to Entities query:</span></span>  
  
- <span data-ttu-id="2bb7e-107">개념적 모델에 정의된 0개 이상의 형식화된 엔터티 개체 컬렉션 또는 복합 형식의 프로젝션</span><span class="sxs-lookup"><span data-stu-id="2bb7e-107">A collection of zero or more typed entity objects or a projection of complex types that are defined in the conceptual model.</span></span>  
  
- <span data-ttu-id="2bb7e-108">Entity Framework에서 지 원하는 CLR 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-108">CLR types supported by the Entity Framework.</span></span>
  
- <span data-ttu-id="2bb7e-109">인라인 컬렉션</span><span class="sxs-lookup"><span data-stu-id="2bb7e-109">Inline collections.</span></span>  
  
- <span data-ttu-id="2bb7e-110">익명 형식</span><span class="sxs-lookup"><span data-stu-id="2bb7e-110">Anonymous types.</span></span>  
  
 <span data-ttu-id="2bb7e-111">다음 쿼리 식 구문 예제에서는 익명 형식 초기화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-111">Anonymous type initialization is shown in the following example in query expression syntax:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 <span data-ttu-id="2bb7e-112">다음 메서드 기반 쿼리 구문의 예제에서는 익명 형식 초기화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-112">The following example in method-based query syntax shows anonymous type initialization:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 <span data-ttu-id="2bb7e-113">사용자 정의 클래스 초기화도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-113">User-defined class initialization is also supported.</span></span> <span data-ttu-id="2bb7e-114">C# 3.0 및 Visual Basic 9.0 초기화 패턴이 지원되며, 속성 getter 및 setter가 대칭이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-114">The C# 3.0 and Visual Basic 9.0 initialization pattern is supported and assumes that the property getter and setter are symmetric.</span></span> <span data-ttu-id="2bb7e-115">다음 쿼리 식 구문 예제에서는 쿼리에서의 사용자 지정 클래스 초기화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-115">The following example in query expression syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 <span data-ttu-id="2bb7e-116">다음 메서드 기반 쿼리 구문 예제에서는 쿼리에서의 사용자 지정 클래스 초기화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bb7e-116">The following example in method-based query syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="2bb7e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bb7e-117">See also</span></span>

- [<span data-ttu-id="2bb7e-118">LINQ to Entities 쿼리의 식</span><span class="sxs-lookup"><span data-stu-id="2bb7e-118">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
