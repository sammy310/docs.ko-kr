---
title: '방법: 쿼리에서 모델 정의 함수 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 38c43fa509b5259aa94ca416aadb51b405fc5dc7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542400"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="a17a1-102">방법: 쿼리에서 모델 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="a17a1-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="a17a1-103">이 항목에서는 LINQ to Entities 쿼리 내에서 개념적 모델에 정의 된 함수를 호출 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-103">This topic describes how to call functions that are defined in the conceptual model from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="a17a1-104">다음 절차에서는 LINQ to Entities 쿼리 내에서 모델 정의 함수를 호출 하는 방법에 대 한 개략적인 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-104">The procedure below provides a high-level outline for calling a model-defined function from within a LINQ to Entities query.</span></span> <span data-ttu-id="a17a1-105">절차 다음에 나오는 예제에서는 절차의 단계를 보다 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="a17a1-106">이 절차에서는 사용자가 개념적 모델에서 함수를 정의했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="a17a1-107">자세한 내용은 [방법: 개념적 모델에서 사용자 지정 함수 정의](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a17a1-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="a17a1-108">개념적 모델에 정의된 함수를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="a17a1-108">To call a function defined in the conceptual model</span></span>  
  
1. <span data-ttu-id="a17a1-109">개념적 모델에 정의된 함수로 매핑되는 CLR(공용 언어 런타임) 메서드를 애플리케이션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="a17a1-110">메서드를 매핑하려면 메서드에 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="a17a1-111">특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 및 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 각각 개념적 모델의 네임스페이스 이름과 함수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="a17a1-112">LINQ에서 함수 이름을 확인할 때는 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2. <span data-ttu-id="a17a1-113">LINQ to Entities 쿼리에서 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-113">Call the function in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a17a1-114">예제</span><span class="sxs-lookup"><span data-stu-id="a17a1-114">Example</span></span>  
 <span data-ttu-id="a17a1-115">다음 예제에서는 LINQ to Entities 쿼리 내에서 개념적 모델에 정의 된 함수를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a LINQ to Entities query.</span></span> <span data-ttu-id="a17a1-116">이 예제에서는 School 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-116">The example uses the School model.</span></span> <span data-ttu-id="a17a1-117">School 모델에 대 한 자세한 내용은 [School 샘플 데이터베이스 만들기](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) 및 [School .edmx 파일 생성](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a17a1-117">For information about the School model, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>  
  
 <span data-ttu-id="a17a1-118">다음의 개념적 모델 함수는 강사가 고용된 이후 경과된 년 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="a17a1-119">개념적 모델에 함수를 추가 하는 방법에 대 한 자세한 내용은 [방법: 개념적 모델에서 사용자 지정 함수 정의](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a17a1-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="a17a1-120">예제</span><span class="sxs-lookup"><span data-stu-id="a17a1-120">Example</span></span>  
 <span data-ttu-id="a17a1-121">다음에는 애플리케이션에 아래 메서드를 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 이 메서드를 개념적 모델 함수에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="a17a1-122">예제</span><span class="sxs-lookup"><span data-stu-id="a17a1-122">Example</span></span>  
 <span data-ttu-id="a17a1-123">이제 LINQ to Entities 쿼리 내에서 개념적 모델 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-123">Now you can call the conceptual model function from within a LINQ to Entities query.</span></span> <span data-ttu-id="a17a1-124">다음 코드에서는 고용된 지 10년이 넘은 모든 강사를 표시하는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a17a1-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a17a1-125">참조</span><span class="sxs-lookup"><span data-stu-id="a17a1-125">See also</span></span>

- <span data-ttu-id="a17a1-126">[.edmx 파일 개요](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a17a1-126">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="a17a1-127">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="a17a1-127">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="a17a1-128">LINQ to Entities 쿼리에서 함수 호출</span><span class="sxs-lookup"><span data-stu-id="a17a1-128">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="a17a1-129">방법: 개체 메서드로 모델 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="a17a1-129">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)
