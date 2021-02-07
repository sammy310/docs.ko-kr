---
description: '자세히 알아보기: 연결 형식'
title: 연결 형식
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 4df84d97c798e9f2d06e0f5dce442e05cb4c67b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697558"
---
# <a name="association-type"></a><span data-ttu-id="dc4e9-103">연결 형식</span><span class="sxs-lookup"><span data-stu-id="dc4e9-103">association type</span></span>

<span data-ttu-id="dc4e9-104">연결 *형식* (연결이 라고도 함)은 EDM (엔터티 데이터 모델)에서 관계를 설명 하는 기본 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-104">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="dc4e9-105">개념적 모델에서 연결은 두 [엔터티 형식](entity-type.md) (예: 및) 간의 관계를 나타냅니다 `Customer` `Order` .</span><span class="sxs-lookup"><span data-stu-id="dc4e9-105">In a conceptual model, an association represents a relationship between two [entity types](entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="dc4e9-106">애플리케이션에서 연결 인스턴스는 특정 연결(예: `Customer` 인스턴스와 `Order` 인스턴스 간의 연결)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-106">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="dc4e9-107">연결 인스턴스는 [연결 집합](association-set.md)에 논리적으로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-107">Association instances are logically grouped in an [association set](association-set.md).</span></span>  
  
 <span data-ttu-id="dc4e9-108">연결 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-108">An association definition contains the following information:</span></span>  
  
- <span data-ttu-id="dc4e9-109">고유한 이름</span><span class="sxs-lookup"><span data-stu-id="dc4e9-109">A unique name.</span></span> <span data-ttu-id="dc4e9-110">(필수)</span><span class="sxs-lookup"><span data-stu-id="dc4e9-110">(Required)</span></span>  
  
- <span data-ttu-id="dc4e9-111">관계의 각 엔터티 형식에 대해 하나씩, 두 개의 [연결 끝](association-end.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-111">Two [association ends](association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="dc4e9-112">(필수)</span><span class="sxs-lookup"><span data-stu-id="dc4e9-112">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="dc4e9-113">연결은 셋 이상 엔터티 형식 간의 관계를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-113">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="dc4e9-114">그러나 연결은 각 연결 End에 같은 엔터티 형식을 지정하여 자체 관계를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-114">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
- <span data-ttu-id="dc4e9-115">[참조 무결성 제약 조건](referential-integrity-constraint.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-115">A [referential integrity constraint](referential-integrity-constraint.md).</span></span> <span data-ttu-id="dc4e9-116">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="dc4e9-116">(Optional)</span></span>  
  
 <span data-ttu-id="dc4e9-117">각 연결 end는 연결의 한쪽 끝에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는 [연결 end 복합성](association-end-multiplicity.md) 을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-117">Each association end must specify an [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="dc4e9-118">연결 end 복합성은 1 (1), 0 또는 1 (0 ..1) 또는 다 수 ()의 값을 가질 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="dc4e9-118">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span> <span data-ttu-id="dc4e9-119">연결의 한 end에 있는 엔터티 형식 인스턴스는 엔터티 형식에서 노출 된 경우 [탐색 속성](navigation-property.md) 또는 외래 키를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-119">Entity type instances at one end of an association can be accessed through [navigation properties](navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="dc4e9-120">자세한 내용은 [엔터티 데이터 모델: 외래 키](foreign-key-property.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-120">For more information, see [Entity Data Model: Foreign Keys](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc4e9-121">예제</span><span class="sxs-lookup"><span data-stu-id="dc4e9-121">Example</span></span>  

 <span data-ttu-id="dc4e9-122">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-122">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="dc4e9-123">`PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-123">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="dc4e9-124">끝의 복합성은 `Publisher` 1이 고, 끝의 복합성은 `Book` 다 수 ()입니다. 즉 \* , 게시자가 많은 책을 게시 하 고 한 출판사에서 책을 게시 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-124">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/association-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="dc4e9-126">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-126">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="dc4e9-127">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dc4e9-127">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="dc4e9-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc4e9-128">See also</span></span>

- [<span data-ttu-id="dc4e9-129">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="dc4e9-129">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="dc4e9-130">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="dc4e9-130">Entity Data Model</span></span>](entity-data-model.md)
