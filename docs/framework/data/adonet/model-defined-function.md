---
description: '자세히 알아보기: 모델 정의 함수'
title: 모델 정의 함수
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 146ef4a8ad8c38897b8e56b6bc1485e1e40754cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723740"
---
# <a name="model-defined-function"></a><span data-ttu-id="28601-103">모델 정의 함수</span><span class="sxs-lookup"><span data-stu-id="28601-103">model-defined function</span></span>

<span data-ttu-id="28601-104">*모델 정의 함수* 는 개념적 모델에 정의 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="28601-104">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="28601-105">모델 정의 함수의 본문은 함수를 데이터 소스에서 지원 되는 규칙이 나 언어와는 독립적으로 표현할 수 있도록 하는 [Entity SQL](./ef/language-reference/entity-sql-language.md)으로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28601-105">The body of a model-defined function is expressed in [Entity SQL](./ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="28601-106">모델 정의 함수 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28601-106">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="28601-107">함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="28601-107">A function name.</span></span> <span data-ttu-id="28601-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="28601-108">(Required)</span></span>  
  
- <span data-ttu-id="28601-109">반환 값의 형식</span><span class="sxs-lookup"><span data-stu-id="28601-109">The type of the return value.</span></span> <span data-ttu-id="28601-110">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="28601-110">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="28601-111">반환 형식을 지정하지 않으면 반환 값은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="28601-111">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="28601-112">매개 변수 정보</span><span class="sxs-lookup"><span data-stu-id="28601-112">Parameter information.</span></span> <span data-ttu-id="28601-113">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="28601-113">(Optional)</span></span>  
  
- <span data-ttu-id="28601-114">함수의 본문을 정의 하는 [Entity SQL](./ef/language-reference/entity-sql-language.md) 식입니다.</span><span class="sxs-lookup"><span data-stu-id="28601-114">An [Entity SQL](./ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="28601-115">모델 정의 함수는 출력 매개 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28601-115">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="28601-116">모델 정의 함수를 작성할 수 있도록 이러한 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28601-116">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28601-117">예제</span><span class="sxs-lookup"><span data-stu-id="28601-117">Example</span></span>  

 <span data-ttu-id="28601-118">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28601-118">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![게시 된 날짜가 있는 모델을 보여 주는 스크린샷](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="28601-120">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="28601-120">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="28601-121">다음 CSDL에서는 위 다이어그램의 `Book` 인스턴스가 출판된 이후의 년 수를 반환하는 함수를 개념적 모델에 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28601-121">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="28601-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28601-122">See also</span></span>

- [<span data-ttu-id="28601-123">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="28601-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="28601-124">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="28601-124">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="28601-125">엔터티 데이터 모델: 기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="28601-125">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)
