---
description: '자세히 알아보기: 연결 끝'
title: 연결 End
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 4a166c0bdb61d1b5fad07a052518a78a74c54e23
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697662"
---
# <a name="association-end"></a><span data-ttu-id="4f473-103">연결 End</span><span class="sxs-lookup"><span data-stu-id="4f473-103">association end</span></span>

<span data-ttu-id="4f473-104">연결 *end* 는 연결의 한쪽 end에서 [엔터티 형식을](entity-type.md) 식별 하 [고 연결](association-type.md) 의 해당 end에 있을 수 있는 엔터티 형식 인스턴스 수를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-104">An *association end* identifies the [entity type](entity-type.md) on one end of an [association](association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="4f473-105">연결 End는 연결의 일부로 정의되고 연결에는 정확히 두 개의 연결 End가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-105">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="4f473-106">[탐색 속성](navigation-property.md) 을 통해 한 연결 end에서 다른 연결 끝으로 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-106">[Navigation properties](navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="4f473-107">연결 End 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-107">An association end definition contains the following information:</span></span>  
  
- <span data-ttu-id="4f473-108">연결과 관련된 엔터티 형식 중 하나</span><span class="sxs-lookup"><span data-stu-id="4f473-108">One of the entity types involved in the association.</span></span> <span data-ttu-id="4f473-109">(필수)</span><span class="sxs-lookup"><span data-stu-id="4f473-109">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4f473-110">지정된 연결에서 각 연결 End에 지정한 엔터티 형식은 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-110">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="4f473-111">이렇게 하면 자체 연결이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-111">This creates a self-association.</span></span>  
  
- <span data-ttu-id="4f473-112">연결의 한 end에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는 [연결 end 복합성](association-end-multiplicity.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-112">An [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="4f473-113">연결 end 복합성은 1 (1), 0 또는 1 (0 ..1) 또는 다 수 ()의 값을 가질 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="4f473-113">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
- <span data-ttu-id="4f473-114">연결 End의 이름.</span><span class="sxs-lookup"><span data-stu-id="4f473-114">A name for the association end.</span></span> <span data-ttu-id="4f473-115">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="4f473-115">(Optional)</span></span>  
  
- <span data-ttu-id="4f473-116">삭제 시 계단식 배열과 같이 연결에서 수행되는 작업에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="4f473-116">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="4f473-117">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="4f473-117">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f473-118">예제</span><span class="sxs-lookup"><span data-stu-id="4f473-118">Example</span></span>  

 <span data-ttu-id="4f473-119">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-119">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="4f473-120">`PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-120">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="4f473-121">끝의 복합성은 `Publisher` 1이 고, 끝의 복합성은 `Book` 다 수 ()입니다. 즉 \* , 게시자가 많은 책을 게시 하 고 한 출판사에서 책을 게시 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-121">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="4f473-123">ADO.NET Entity Framework에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-123">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="4f473-124">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-124">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="4f473-125">각 연결 End의 형식, 이름 및 복합성은 XML 특성(각각 `Type`, `Role` 및 `Multiplicity` 특성)으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-125">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="4f473-126">한 End에서 수행되는 작업에 대한 선택적 정보는 XML 요소(`OnDelete` 요소)에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-126">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="4f473-127">이 경우 발행자를 삭제하면 연결된 책도 모두 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f473-127">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="4f473-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f473-128">See also</span></span>

- [<span data-ttu-id="4f473-129">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="4f473-129">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="4f473-130">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="4f473-130">Entity Data Model</span></span>](entity-data-model.md)
