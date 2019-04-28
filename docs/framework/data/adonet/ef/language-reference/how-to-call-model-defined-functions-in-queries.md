---
title: '방법: 쿼리에서 모델 정의 함수 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 2fe0360a0548bddb0ebba566eca0d121c9ec9160
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774701"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="69a02-102">방법: 쿼리에서 모델 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="69a02-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="69a02-103">이 항목에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 개념적 모델에 정의된 함수를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-103">This topic describes how to call functions that are defined in the conceptual model from within [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="69a02-104">다음 절차에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 모델에 정의된 함수를 호출하는 방법에 대해 간단히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-104">The procedure below provides a high-level outline for calling a model-defined function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="69a02-105">절차 다음에 나오는 예제에서는 절차의 단계를 보다 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="69a02-106">이 절차에서는 사용자가 개념적 모델에서 함수를 정의했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="69a02-107">자세한 내용은 [방법: 개념적 모델의 사용자 지정 함수 정의](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="69a02-108">개념적 모델에 정의된 함수를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="69a02-108">To call a function defined in the conceptual model</span></span>  
  
1. <span data-ttu-id="69a02-109">개념적 모델에 정의된 함수로 매핑되는 CLR(공용 언어 런타임) 메서드를 응용 프로그램에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="69a02-110">메서드를 매핑하려면 메서드에 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="69a02-111">특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 및 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 각각 개념적 모델의 네임스페이스 이름과 함수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="69a02-112">LINQ에서 함수 이름을 확인할 때는 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2. <span data-ttu-id="69a02-113">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에서 이 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-113">Call the function in a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a02-114">예제</span><span class="sxs-lookup"><span data-stu-id="69a02-114">Example</span></span>  
 <span data-ttu-id="69a02-115">다음 예제에서는 개념적 모델에 정의된 함수를 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="69a02-116">이 예제에서는 School 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-116">The example uses the School model.</span></span> <span data-ttu-id="69a02-117">School 모델에 대 한 정보를 참조 하세요 [School 샘플 데이터베이스 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) 하 고 [School.edmx 파일 생성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-117">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>  
  
 <span data-ttu-id="69a02-118">다음의 개념적 모델 함수는 강사가 고용된 이후 경과된 년 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="69a02-119">개념적 모델에 함수를 추가 하는 방법에 대 한 내용은 [방법: 개념적 모델의 사용자 지정 함수 정의](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span><span class="sxs-lookup"><span data-stu-id="69a02-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="69a02-120">예제</span><span class="sxs-lookup"><span data-stu-id="69a02-120">Example</span></span>  
 <span data-ttu-id="69a02-121">다음에는 응용 프로그램에 아래 메서드를 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 이 메서드를 개념적 모델 함수에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="69a02-122">예제</span><span class="sxs-lookup"><span data-stu-id="69a02-122">Example</span></span>  
 <span data-ttu-id="69a02-123">이제 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 내에서 개념적 모델 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-123">Now you can call the conceptual model function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="69a02-124">다음 코드에서는 고용된 지 10년이 넘은 모든 강사를 표시하는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="69a02-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="69a02-125">See also</span></span>

- <span data-ttu-id="69a02-126">[.edmx 파일 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="69a02-126">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="69a02-127">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="69a02-127">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [<span data-ttu-id="69a02-128">LINQ to Entities 쿼리에서 함수 호출</span><span class="sxs-lookup"><span data-stu-id="69a02-128">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="69a02-129">방법: 개체 메서드로 모델 정의 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a02-129">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
