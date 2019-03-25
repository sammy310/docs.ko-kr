---
title: 연결 End
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 7fb9b48c5ed832e83f2a1e344d17d9a9797d393b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410331"
---
# <a name="association-end"></a><span data-ttu-id="1c817-102">연결 End</span><span class="sxs-lookup"><span data-stu-id="1c817-102">association end</span></span>
<span data-ttu-id="1c817-103">*연결 end* 하 게 식별 하는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 한쪽 끝에는 [연결](../../../../docs/framework/data/adonet/association-type.md) 및 연결의 해당 end에 있을 수 있는 인스턴스를 입력 하는 엔터티의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-103">An *association end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) on one end of an [association](../../../../docs/framework/data/adonet/association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="1c817-104">연결 End는 연결의 일부로 정의되고 연결에는 정확히 두 개의 연결 End가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="1c817-105">[탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 다른 끝에서 탐색을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-105">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="1c817-106">연결 End 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-106">An association end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="1c817-107">연결과 관련된 엔터티 형식 중 하나</span><span class="sxs-lookup"><span data-stu-id="1c817-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="1c817-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="1c817-108">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1c817-109">지정된 연결에서 각 연결 End에 지정한 엔터티 형식은 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="1c817-110">이렇게 하면 자체 연결이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-110">This creates a self-association.</span></span>  
  
-   <span data-ttu-id="1c817-111">[연결 end 복합성](../../../../docs/framework/data/adonet/association-end-multiplicity.md) 연결의 한 end에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-111">An [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="1c817-112">연결 end 복합성 하나 (1), 0 개 이상의 값 (0..1) 또는 여러 열에 있을 수 있습니다 (\*).</span><span class="sxs-lookup"><span data-stu-id="1c817-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
-   <span data-ttu-id="1c817-113">연결 End의 이름.</span><span class="sxs-lookup"><span data-stu-id="1c817-113">A name for the association end.</span></span> <span data-ttu-id="1c817-114">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-114">(Optional)</span></span>  
  
-   <span data-ttu-id="1c817-115">삭제 시 계단식 배열과 같이 연결에서 수행되는 작업에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="1c817-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="1c817-116">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c817-117">예제</span><span class="sxs-lookup"><span data-stu-id="1c817-117">Example</span></span>  
 <span data-ttu-id="1c817-118">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="1c817-119">
  `PublishedBy\` 연결의 연결 End는 `Book` 및 `Publisher\` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="1c817-120">다중성 합니다 `Publisher` 끝이 한 개 (1)이 고는 `Book` 끝이 많은 (\*)는 발행자가 많은 책을 책은 하나의 게시자에서 게시를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="1c817-122">ADO.NET Entity Framework 개념적 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="1c817-123">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="1c817-124">각 연결 End의 형식, 이름 및 복합성은 XML 특성(각각 `Type`, `Role` 및 `Multiplicity` 특성)으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="1c817-125">한 End에서 수행되는 작업에 대한 선택적 정보는 XML 요소(`OnDelete` 요소)에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="1c817-126">이 경우 발행자를 삭제하면 연결된 책도 모두 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c817-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="1c817-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="1c817-127">See also</span></span>
- [<span data-ttu-id="1c817-128">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="1c817-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="1c817-129">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="1c817-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
