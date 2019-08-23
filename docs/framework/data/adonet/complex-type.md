---
title: 복합 형식
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: fac25ace69938e1245200e10285f4460ac216780
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948723"
---
# <a name="complex-type"></a><span data-ttu-id="a996c-102">복합 형식</span><span class="sxs-lookup"><span data-stu-id="a996c-102">complex type</span></span>
<span data-ttu-id="a996c-103">*복합 형식은* [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 또는 다른 복합 형식에 대 한 다양 한 구조적 속성을 정의 하기 위한 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="a996c-104">각 템플릿에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-104">Each template contains the following:</span></span>  
  
- <span data-ttu-id="a996c-105">고유한 이름</span><span class="sxs-lookup"><span data-stu-id="a996c-105">A unique name.</span></span> <span data-ttu-id="a996c-106">(필수)</span><span class="sxs-lookup"><span data-stu-id="a996c-106">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a996c-107">복합 형식의 이름은 동일한 네임스페이스 내의 엔터티 형식 이름과 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
- <span data-ttu-id="a996c-108">하나 이상의 [속성](../../../../docs/framework/data/adonet/property.md)형식으로 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="a996c-109">필요에 따라</span><span class="sxs-lookup"><span data-stu-id="a996c-109">(Optional.)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a996c-110">복합 형식의 속성은 다른 복합 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="a996c-111">복합 형식은 기본 형식 속성이나 다른 복합 형식의 형태로 데이터 페이로드를 전달할 수 있다는 점에서 엔터티 형식과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="a996c-112">그러나 복합 형식과 엔터티 형식 사이에는 약간의 중요한 차이점이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-112">However, there are some key differences between complex types and entity types:</span></span>  
  
- <span data-ttu-id="a996c-113">복합 형식은 식별자를 포함하지 않으므로 독립적으로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="a996c-114">복합 형식은 엔터티 형식 또는 다른 복합 형식의 속성으로만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
- <span data-ttu-id="a996c-115">복합 형식은 [연결](../../../../docs/framework/data/adonet/association-type.md)에 참여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="a996c-116">연결의 끝은 복합 형식이 될 수 없으므로 복합 형식에 대해 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a996c-117">예제</span><span class="sxs-lookup"><span data-stu-id="a996c-117">Example</span></span>  
 <span data-ttu-id="a996c-118">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 에서는[CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="a996c-119">다음 CSDL에서는 기본 형식 속성 `StreetAddress`, `City`, `StateOrProvince`, `Country` 및 `PostalCode`가 있는 복합 형식 Address를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="a996c-120">위의 `Address` 복합 형식을 엔터티 형식의 속성으로 정의하려면 엔터티 형식 정의에서 속성 형식을 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="a996c-121">다음 CSDL에서는 `Address` 속성을 엔터티 형식(Publisher)의 복합 형식으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a996c-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="a996c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="a996c-122">See also</span></span>

- [<span data-ttu-id="a996c-123">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="a996c-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="a996c-124">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="a996c-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
