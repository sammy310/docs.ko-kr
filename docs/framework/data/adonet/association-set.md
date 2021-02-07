---
description: '자세히 알아보기: 연결 집합'
title: 연결 집합(association set)
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: aeddf3e898aecc2b283a941e844a6dbe810357f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697584"
---
# <a name="association-set"></a><span data-ttu-id="f9e52-103">연결 집합(association set)</span><span class="sxs-lookup"><span data-stu-id="f9e52-103">association set</span></span>

<span data-ttu-id="f9e52-104">*연결 집합* 은 같은 형식의 [연결](association-type.md) 인스턴스에 대 한 논리적 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-104">An *association set* is a logical container for [association](association-type.md) instances of the same type.</span></span> <span data-ttu-id="f9e52-105">연결 집합은 데이터 모델링 구문이 아니므로 데이터 또는 관계의 구조를 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-105">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="f9e52-106">대신 연결 집합은 연결 인스턴스를 그룹화하여 데이터 스토리지에 매핑할 수 있도록 호스팅 또는 스토리지 환경(예: 공용 언어 런타임 또는 SQL Server 데이터베이스)에 대한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-106">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="f9e52-107">연결 집합은 엔터티 [집합](entity-set.md) 및 연결 집합의 논리적 그룹인 [엔터티 컨테이너](entity-container.md)내에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-107">An association set is defined within an [entity container](entity-container.md), which is a logical grouping of [entity sets](entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="f9e52-108">연결 집합 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-108">A definition for an association set contains the following information:</span></span>  
  
- <span data-ttu-id="f9e52-109">연결 집합 이름</span><span class="sxs-lookup"><span data-stu-id="f9e52-109">The association set name.</span></span> <span data-ttu-id="f9e52-110">(필수)</span><span class="sxs-lookup"><span data-stu-id="f9e52-110">(Required)</span></span>  
  
- <span data-ttu-id="f9e52-111">연결 집합에 인스턴스가 포함될 연결</span><span class="sxs-lookup"><span data-stu-id="f9e52-111">The association of which it will contain instances.</span></span> <span data-ttu-id="f9e52-112">(필수)</span><span class="sxs-lookup"><span data-stu-id="f9e52-112">(Required)</span></span>  
  
- <span data-ttu-id="f9e52-113">두 [연결 집합이 끝납니다](association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="f9e52-113">Two [association set ends](association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9e52-114">예제</span><span class="sxs-lookup"><span data-stu-id="f9e52-114">Example</span></span>  

 <span data-ttu-id="f9e52-115">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-115">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="f9e52-116">연결 집합에 대한 정보는 다이어그램에 표시되지 않지만 다음 다이어그램에서는 이 모델을 기반으로 하여 연결 집합 및 엔터티 집합의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-116">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/association-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="f9e52-118">다음 예제에서는 위에 표시된 개념적 모델을 기반으로 하여 연결 집합(`PublishedBy`) 및 엔터티 집합 두 개(`Books` 및 `Publishers`)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-118">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="f9e52-119">엔터티 집합의 Bi는 `Books` `Book` 런타임에 엔터티 형식의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-119">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="f9e52-120">마찬가지로 Pj는 `Publisher` 엔터티 집합의 인스턴스를 나타냅니다 `Publishers` .</span><span class="sxs-lookup"><span data-stu-id="f9e52-120">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="f9e52-121">BiPj `PublishedBy` 는 연결 집합에서 연결의 인스턴스를 나타냅니다 `PublishedBy` .</span><span class="sxs-lookup"><span data-stu-id="f9e52-121">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![집합 예제를 보여 주는 스크린샷](./media/association-set/sets-example-association.gif)  
  
 <span data-ttu-id="f9e52-123">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="f9e52-124">다음 CSDL에서는 위의 다이어그램에 있는 각 연결에 대한 하나의 연결 집합을 사용하여 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-124">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="f9e52-125">각 연결 집합의 이름과 연결은 XML 특성을 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-125">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="f9e52-126">연결 [집합 end](association-set-end.md)를 공유 하는 두 개의 연결 집합이 없으면 연결 당 여러 연결 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-126">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](association-set-end.md).</span></span> <span data-ttu-id="f9e52-127">다음 CSDL에서는 `WrittenBy` 연결에 대한 두 개의 연결 집합이 있는 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-127">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="f9e52-128">`Book` 및 `Author` 엔터티 형식에 대해 엔터티 집합이 여러 개 정의되었으며 어떤 연결 집합도 연결 집합 End를 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e52-128">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="f9e52-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9e52-129">See also</span></span>

- [<span data-ttu-id="f9e52-130">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="f9e52-130">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="f9e52-131">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="f9e52-131">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="f9e52-132">외래 키 속성</span><span class="sxs-lookup"><span data-stu-id="f9e52-132">foreign key property</span></span>](foreign-key-property.md)
