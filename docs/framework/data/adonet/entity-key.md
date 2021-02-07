---
description: '자세히 알아보기: 엔터티 키'
title: 엔터티 키
ms.date: 03/30/2017
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
ms.openlocfilehash: 588f18a2f76ca11c797b9b2aaab00b090c99e345
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724442"
---
# <a name="entity-key"></a><span data-ttu-id="255c7-103">엔터티 키</span><span class="sxs-lookup"><span data-stu-id="255c7-103">entity key</span></span>

<span data-ttu-id="255c7-104">*엔터티 키* 는 id를 확인 하는 데 사용 되는 [엔터티 형식의](entity-type.md) [속성 또는 속성](property.md) 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-104">An *entity key* is a [property](property.md) or a set of properties of an [entity type](entity-type.md) that are used to determine identity.</span></span> <span data-ttu-id="255c7-105">엔터티 키를 구성하는 속성은 디자인 타임에 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-105">The properties that make up an entity key are chosen at design time.</span></span> <span data-ttu-id="255c7-106">엔터티 키 속성의 값은 런타임에 [엔터티 집합](entity-set.md) 내에서 엔터티 형식 인스턴스를 고유 하 게 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-106">The values of entity key properties must uniquely identify an entity type instance within an [entity set](entity-set.md) at run time.</span></span> <span data-ttu-id="255c7-107">엔터티 키를 구성하는 속성을 선택하여 엔터티 집합에서 인스턴스의 고유성을 보장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-107">The properties that make up an entity key should be chosen to guarantee uniqueness of instances in an entity set.</span></span>  
  
 <span data-ttu-id="255c7-108">다음은 속성 집합이 엔터티 키가 되기 위한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-108">The following are the requirements for a set of properties to be an entity key:</span></span>  
  
- <span data-ttu-id="255c7-109">엔터티 집합 내의 두 엔터티 키는 같지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-109">No two entity keys within an entity set can be identical.</span></span> <span data-ttu-id="255c7-110">즉, 엔터티 집합 내의 두 엔터티에서 키를 구성하는 모든 속성 값은 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-110">That is, for any two entities within an entity set, the values for all of the properties that constitute a key cannot be the same.</span></span> <span data-ttu-id="255c7-111">그러나 엔터티 키를 구성하는 일부 값은 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-111">However, some (but not all) of the values that make up an entity key can be the same.</span></span>  
  
- <span data-ttu-id="255c7-112">엔터티 키는 null을 허용 하지 않는, 변경할 수 없는 [기본 형식 속성](entity-data-model-primitive-data-types.md)집합으로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-112">An entity key must consist of a set of non-nullable, immutable, [primitive type properties](entity-data-model-primitive-data-types.md).</span></span>  
  
- <span data-ttu-id="255c7-113">지정된 엔터티 형식의 엔터티 키를 구성하는 속성은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-113">The properties that make up an entity key for a given entity type cannot change.</span></span> <span data-ttu-id="255c7-114">지정된 엔터티 형식에 사용 가능한 엔터티 키를 여러 개 허용할 수는 없습니다. 서로게이트 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-114">You cannot allow more than one possible entity key for a given entity type; surrogate keys are not supported.</span></span>  
  
- <span data-ttu-id="255c7-115">엔터티가 상속 계층 구조에 포함되어 있는 경우 루트 엔터티는 엔터티 키를 구성하는 모든 속성을 포함해야 하며, 루트 엔터티 형식에 엔터티 키를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-115">When an entity is involved in an inheritance hierarchy, the root entity must contain all the properties that make up the entity key, and the entity key must be defined on the root entity type.</span></span> <span data-ttu-id="255c7-116">자세한 내용은 [엔터티 데이터 모델: 상속](entity-data-model-inheritance.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="255c7-116">For more information, see [Entity Data Model: Inheritance](entity-data-model-inheritance.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="255c7-117">예제</span><span class="sxs-lookup"><span data-stu-id="255c7-117">Example</span></span>  

 <span data-ttu-id="255c7-118">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-118">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="255c7-119">엔터티 키를 구성하는 각 엔터티 형식의 속성은 "(키)"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-119">The properties of each entity type that make up its entity key are denoted with "(Key)".</span></span> <span data-ttu-id="255c7-120">`Author` 엔터티 형식에는 두 가지 속성 `Name` 및 `Address`로 구성된 엔터티 키가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-120">Note that the `Author` entity type has an entity key that consists of two properties, `Name` and `Address`.</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/entity-key/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="255c7-122">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="255c7-123">다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-123">The CSDL below defines the `Book` entity type shown in the diagram above.</span></span> <span data-ttu-id="255c7-124">엔터티 키는 엔터티 형식의 `ISBN` 속성을 참조하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-124">Note that the entity key is defined by referencing the `ISBN` property of the entity type.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="255c7-125">ISBN(International Standard Book Number)은 책을 고유하게 식별하므로 엔터티 키에 대해 `ISBN` 속성을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-125">The `ISBN` property is a good choice for the entity key because an International Standard Book Number (ISBN) uniquely identifies a book.</span></span>  
  
 <span data-ttu-id="255c7-126">다음 CSDL에서는 위의 다이어그램에 표시된 `Author` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-126">The CSDL below defines the `Author` entity type shown in the diagram above.</span></span> <span data-ttu-id="255c7-127">엔터티 키는 두 가지 속성 `Name` 및 `Address`로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-127">Note that the entity key consists of two properties, `Name` and `Address`.</span></span>  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 <span data-ttu-id="255c7-128">이름이 같은 두 저자가 같은 주소지에서 거주할 가능성은 없으므로 엔터티 키에 대해 `Name` 및 `Address`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-128">Using `Name` and `Address` for the entity key is a reasonable choice, because two authors of the same name are unlikely to live at the same address.</span></span> <span data-ttu-id="255c7-129">그러나 이러한 엔터티 키 선택이 엔터티 집합에서의 고유한 엔터티 키를 절대적으로 보장하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-129">However, this choice for an entity key does not absolutely guarantee unique entity keys in an entity set.</span></span> <span data-ttu-id="255c7-130">이 경우에는 저자를 고유하게 식별하는 데 사용할 수 있는 `AuthorId`와 같은 속성을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="255c7-130">Adding a property, such as `AuthorId`, that could be used to uniquely identify an author would be recommended in this case.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="255c7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="255c7-131">See also</span></span>

- [<span data-ttu-id="255c7-132">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="255c7-132">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="255c7-133">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="255c7-133">Entity Data Model</span></span>](entity-data-model.md)
