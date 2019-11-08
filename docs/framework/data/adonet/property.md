---
title: 속성(property)
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: d1e20a6570c458041ec5d8ececbfa291ca9e4612
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735403"
---
# <a name="property"></a><span data-ttu-id="df78f-102">속성(property)</span><span class="sxs-lookup"><span data-stu-id="df78f-102">property</span></span>
<span data-ttu-id="df78f-103">*속성* 은 [엔터티 형식](entity-type.md) 및 [복합 형식의](complex-type.md)기본적인 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-103">*Properties* are the fundamental building blocks of [entity types](entity-type.md) and [complex types](complex-type.md).</span></span> <span data-ttu-id="df78f-104">속성은 엔터티 형식 인스턴스 또는 복합 형식 인스턴스에 포함될 데이터의 모양과 특징을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="df78f-105">개념적 모델의 속성은 클래스에 정의된 속성과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="df78f-106">클래스의 속성이 클래스의 모양을 정의하고 개체에 대한 정보를 전달하는 것과 동일한 방식으로, 개념적 모델의 속성은 엔터티 형식의 모양을 정의하고 엔터티 형식 인스턴스에 대한 정보를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df78f-107">이 항목에서 설명하는 속성은 탐색 속성과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="df78f-108">자세한 내용은 [탐색 속성](navigation-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df78f-108">For more information, see [navigation properties](navigation-property.md).</span></span>  
  
 <span data-ttu-id="df78f-109">속성 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-109">A property definition contains the following information:</span></span>  
  
- <span data-ttu-id="df78f-110">속성 이름</span><span class="sxs-lookup"><span data-stu-id="df78f-110">A property name.</span></span> <span data-ttu-id="df78f-111">(필수)</span><span class="sxs-lookup"><span data-stu-id="df78f-111">(Required)</span></span>  
  
- <span data-ttu-id="df78f-112">속성 형식</span><span class="sxs-lookup"><span data-stu-id="df78f-112">A property type.</span></span> <span data-ttu-id="df78f-113">(필수)</span><span class="sxs-lookup"><span data-stu-id="df78f-113">(Required)</span></span>  
  
- <span data-ttu-id="df78f-114">[패싯](facet.md)집합입니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-114">A set of [facets](facet.md).</span></span> <span data-ttu-id="df78f-115">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-115">(Optional)</span></span>  
  
 <span data-ttu-id="df78f-116">속성에는 기본 데이터(예: 문자열, 정수 또는 부울 값) 또는 구조적 데이터(예: 복합 형식)가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="df78f-117">기본 형식인 속성을 스칼라 속성이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="df78f-118">자세한 내용은 [엔터티 데이터 모델: 기본 데이터 형식](entity-data-model-primitive-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df78f-118">For more information, see [Entity Data Model: Primitive Data Types](entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df78f-119">복합 형식 자체에 복합 형식인 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df78f-120">예제</span><span class="sxs-lookup"><span data-stu-id="df78f-120">Example</span></span>  
 <span data-ttu-id="df78f-121">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="df78f-122">각 속성의 형식 정보는 다이어그램에 표시되지 않지만 각 엔터티 형식에는 여러 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="df78f-123">[엔터티 키](entity-key.md) 인 속성은 (키)로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-123">Properties that are [entity keys](entity-key.md) are denoted with (Key).</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="df78f-125">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-125">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="df78f-126">다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의하고 XML 특성을 사용하여 각 속성의 형식과 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="df78f-127">선택적 패싯인 `Nullable`도 XML 특성을 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="df78f-128">다이어그램에 표시된 속성 중 하나는 복합 형식 속성일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="df78f-129">예를 들어, `Address` 엔터티 형식의 `Publisher` 속성은 `StreetAddress`, `City`, `StateOrProvince`, `Country` 및 `PostalCode`와 같은 여러 스칼라 속성으로 구성된 복합 형식 속성일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="df78f-130">이러한 복합 형식의 CSDL 표현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df78f-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="df78f-131">참조</span><span class="sxs-lookup"><span data-stu-id="df78f-131">See also</span></span>

- [<span data-ttu-id="df78f-132">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="df78f-132">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="df78f-133">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="df78f-133">Entity Data Model</span></span>](entity-data-model.md)
