---
description: '자세히 알아보기: 모델 선언 함수'
title: 모델 선언 함수
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: c9a5cedb8c9706aa0d299635f60f762b92ca6d78
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786266"
---
# <a name="model-declared-function"></a><span data-ttu-id="c7e79-103">모델 선언 함수</span><span class="sxs-lookup"><span data-stu-id="c7e79-103">model-declared function</span></span>

<span data-ttu-id="c7e79-104">*모델 선언 함수* 는 개념적 모델에 선언 된 함수 이지만 해당 개념적 모델에는 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-104">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="c7e79-105">호스팅 또는 스토리지 환경에서 함수를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-105">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="c7e79-106">예를 들어, 모델 선언 함수를 데이터베이스에 정의된 함수에 매핑하여 개념적 모델에 서버 쪽 기능을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-106">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="c7e79-107">모델 선언 함수의 선언에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-107">The declaration of a model-declared function contains the following information:</span></span>  
  
- <span data-ttu-id="c7e79-108">함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-108">The name of the function.</span></span> <span data-ttu-id="c7e79-109">(필수)</span><span class="sxs-lookup"><span data-stu-id="c7e79-109">(Required)</span></span>  
  
- <span data-ttu-id="c7e79-110">반환 값의 형식</span><span class="sxs-lookup"><span data-stu-id="c7e79-110">The type of the return value.</span></span> <span data-ttu-id="c7e79-111">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c7e79-111">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c7e79-112">반환 값을 지정하지 않으면 반환 형식은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-112">If no return value is specified, the return type is void.</span></span>  
  
- <span data-ttu-id="c7e79-113">매개 변수 이름과 형식을 포함하는 매개 변수 정보</span><span class="sxs-lookup"><span data-stu-id="c7e79-113">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="c7e79-114">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c7e79-114">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7e79-115">예제</span><span class="sxs-lookup"><span data-stu-id="c7e79-115">Example</span></span>  

 <span data-ttu-id="c7e79-116">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-116">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="c7e79-117">CSDL에서 모델 선언 함수의 한 가지 구현은 [FunctionImport 요소](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)를 사용 하는 함수 가져오기입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-117">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="c7e79-118">다음 CSDL에서는 함수 가져오기 정의를 사용하여 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-118">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="c7e79-119">반환 형식을 지정하지 않았으므로 함수의 반환 형식은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e79-119">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="c7e79-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7e79-120">See also</span></span>

- [<span data-ttu-id="c7e79-121">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="c7e79-121">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="c7e79-122">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="c7e79-122">Entity Data Model</span></span>](entity-data-model.md)
