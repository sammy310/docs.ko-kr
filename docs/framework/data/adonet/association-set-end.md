---
description: '자세히 알아보기: 연결 집합 끝'
title: 연결 집합 End
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 12e01a3fb947f6fabd5e1a93ef475132418963df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697675"
---
# <a name="association-set-end"></a><span data-ttu-id="87ad9-103">연결 집합 End</span><span class="sxs-lookup"><span data-stu-id="87ad9-103">association set end</span></span>

<span data-ttu-id="87ad9-104">*연결 집합 end* 는 [연결 집합](association-set.md)의 끝에 있는 [엔터티 형식](entity-type.md) 및 [엔터티 집합](entity-set.md) 을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-104">An *association set end* identifies the [entity type](entity-type.md) and the [entity set](entity-set.md) at the end of an [association set](association-set.md).</span></span> <span data-ttu-id="87ad9-105">연결 집합 End는 연결 집합의 일부로 정의되고 연결 집합에는 정확히 두 개의 연결 집합 End가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-105">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="87ad9-106">연결 집합 End 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-106">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="87ad9-107">연결 집합과 관련된 엔터티 형식 중 하나</span><span class="sxs-lookup"><span data-stu-id="87ad9-107">One of the entity types involved in the association set.</span></span> <span data-ttu-id="87ad9-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="87ad9-108">(Required)</span></span>  
  
- <span data-ttu-id="87ad9-109">연결 집합과 관련된 엔터티 형식에 대한 엔터티 집합</span><span class="sxs-lookup"><span data-stu-id="87ad9-109">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="87ad9-110">(필수)</span><span class="sxs-lookup"><span data-stu-id="87ad9-110">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="87ad9-111">예제</span><span class="sxs-lookup"><span data-stu-id="87ad9-111">Example</span></span>  

 <span data-ttu-id="87ad9-112">다음 다이어그램에서는 두 연결 `WrittenBy` 및 `PublishedBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-112">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="87ad9-114">다음 다이어그램에서는 위에 나온 개념적 모델을 기반으로 하여 하나의 연결 집합(`PublishedBy`) 및 두 개의 엔터티 집합(`Books` 및 `Publishers`)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-114">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="87ad9-115">연결 집합 End는 `Books` 및 `Publishers` 엔터티 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-115">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="87ad9-116">엔터티 집합의 Bi는 `Books` `Book` 런타임에 엔터티 형식의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-116">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="87ad9-117">마찬가지로 Pj는 `Publisher` 엔터티 집합의 인스턴스를 나타냅니다 `Publishers` .</span><span class="sxs-lookup"><span data-stu-id="87ad9-117">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="87ad9-118">BiPj `PublishedBy` 는 연결 집합에서 연결의 인스턴스를 나타냅니다 `PublishedBy` .</span><span class="sxs-lookup"><span data-stu-id="87ad9-118">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![집합 예제를 보여 주는 스크린샷](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="87ad9-120">[ADO.NET Entity Framework](./ef/index.md) 는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-120">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="87ad9-121">다음 CSDL에서는 위의 다이어그램에 있는 각 연결에 대한 하나의 연결 집합을 사용하여 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-121">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="87ad9-122">연결 집합 End는 각 연결 집합 정의의 일부로 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad9-122">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="87ad9-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87ad9-123">See also</span></span>

- [<span data-ttu-id="87ad9-124">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="87ad9-124">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="87ad9-125">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="87ad9-125">Entity Data Model</span></span>](entity-data-model.md)
