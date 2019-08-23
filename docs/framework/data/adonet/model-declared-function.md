---
title: 모델 선언 함수
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: 73e716f1c42dfbbb91dc6456212de2a331d7c4ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943917"
---
# <a name="model-declared-function"></a><span data-ttu-id="98b16-102">모델 선언 함수</span><span class="sxs-lookup"><span data-stu-id="98b16-102">model-declared function</span></span>
<span data-ttu-id="98b16-103">*모델 선언 함수* 는 개념적 모델에 선언 된 함수 이지만 해당 개념적 모델에는 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="98b16-104">호스팅 또는 스토리지 환경에서 함수를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="98b16-105">예를 들어, 모델 선언 함수를 데이터베이스에 정의된 함수에 매핑하여 개념적 모델에 서버 쪽 기능을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="98b16-106">모델 선언 함수의 선언에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-106">The declaration of a model-declared function contains the following information:</span></span>  
  
- <span data-ttu-id="98b16-107">함수의 이름.</span><span class="sxs-lookup"><span data-stu-id="98b16-107">The name of the function.</span></span> <span data-ttu-id="98b16-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="98b16-108">(Required)</span></span>  
  
- <span data-ttu-id="98b16-109">반환 값의 형식</span><span class="sxs-lookup"><span data-stu-id="98b16-109">The type of the return value.</span></span> <span data-ttu-id="98b16-110">(옵션)</span><span class="sxs-lookup"><span data-stu-id="98b16-110">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="98b16-111">반환 값을 지정하지 않으면 반환 형식은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-111">If no return value is specified, the return type is void.</span></span>  
  
- <span data-ttu-id="98b16-112">매개 변수 이름과 형식을 포함하는 매개 변수 정보</span><span class="sxs-lookup"><span data-stu-id="98b16-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="98b16-113">(옵션)</span><span class="sxs-lookup"><span data-stu-id="98b16-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="98b16-114">예제</span><span class="sxs-lookup"><span data-stu-id="98b16-114">Example</span></span>  
 <span data-ttu-id="98b16-115">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-115">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="98b16-116">CSDL에서 모델 선언 함수의 한 가지 구현은 [FunctionImport 요소](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)를 사용 하는 함수 가져오기입니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-116">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="98b16-117">다음 CSDL에서는 함수 가져오기 정의를 사용하여 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="98b16-118">반환 형식을 지정하지 않았으므로 함수의 반환 형식은 void입니다.</span><span class="sxs-lookup"><span data-stu-id="98b16-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="98b16-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="98b16-119">See also</span></span>

- [<span data-ttu-id="98b16-120">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="98b16-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="98b16-121">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="98b16-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
