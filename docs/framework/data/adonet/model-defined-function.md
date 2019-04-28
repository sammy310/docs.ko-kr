---
title: 모델 정의 함수
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 77152e8f37b009cbc3e72f053ead867914768d3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772246"
---
# <a name="model-defined-function"></a><span data-ttu-id="e2e86-102">모델 정의 함수</span><span class="sxs-lookup"><span data-stu-id="e2e86-102">model-defined function</span></span>
<span data-ttu-id="e2e86-103">A *모델 정의 함수* 는 개념적 모델에 정의 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="e2e86-104">모델 정의 함수의 본문을 단위로 [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)함수와 독립적으로 표현할 수를 허용 하는 규칙, 데이터 원본에서 언어를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="e2e86-105">모델 정의 함수 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-105">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="e2e86-106">함수 이름</span><span class="sxs-lookup"><span data-stu-id="e2e86-106">A function name.</span></span> <span data-ttu-id="e2e86-107">(필수)</span><span class="sxs-lookup"><span data-stu-id="e2e86-107">(Required)</span></span>  
  
- <span data-ttu-id="e2e86-108">반환 값의 형식</span><span class="sxs-lookup"><span data-stu-id="e2e86-108">The type of the return value.</span></span> <span data-ttu-id="e2e86-109">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2e86-110">반환 형식을 지정하지 않으면 반환 값은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-110">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="e2e86-111">매개 변수 정보</span><span class="sxs-lookup"><span data-stu-id="e2e86-111">Parameter information.</span></span> <span data-ttu-id="e2e86-112">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-112">(Optional)</span></span>  
  
- <span data-ttu-id="e2e86-113">[Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) 함수의 본문을 정의 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="e2e86-114">모델 정의 함수는 출력 매개 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="e2e86-115">모델 정의 함수를 작성할 수 있도록 이러한 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2e86-116">예제</span><span class="sxs-lookup"><span data-stu-id="e2e86-116">Example</span></span>  
 <span data-ttu-id="e2e86-117">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![게시 된 날짜를 사용 하 여 모델을 보여 주는 스크린샷.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="e2e86-119">합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e2e86-120">다음 CSDL에서는 위 다이어그램의 `Book` 인스턴스가 출판된 이후의 년 수를 반환하는 함수를 개념적 모델에 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e2e86-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="e2e86-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="e2e86-121">See also</span></span>

- [<span data-ttu-id="e2e86-122">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="e2e86-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="e2e86-123">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="e2e86-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="e2e86-124">엔터티 데이터 모델: 기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e2e86-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
