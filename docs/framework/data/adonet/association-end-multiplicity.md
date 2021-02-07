---
description: '자세한 정보: 연결 end 복합성'
title: 연결 End 복합성
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 4b708406192e8a6e34119b47261d8986829f2a43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697701"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="7cf29-103">연결 End 복합성</span><span class="sxs-lookup"><span data-stu-id="7cf29-103">association end multiplicity</span></span>

<span data-ttu-id="7cf29-104">*연결 end 복합성* 은 [연결](association-type.md)의 한 end에 있을 수 있는 [엔터티 형식](entity-type.md) 인스턴스 수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-104">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="7cf29-105">연결 End 복합성은 다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-105">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="7cf29-106">한 개(1): 연결 End에 엔터티 형식 인스턴스가 정확히 한 개 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-106">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="7cf29-107">0개 또는 한 개(0..1): 연결 End에 엔터티 형식 인스턴스가 0개 또는 한 개 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-107">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="7cf29-108">many ( \* ): 연결 end에 엔터티 형식 인스턴스가 0 개 이상 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-108">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="7cf29-109">연결은 대체로 연결 End 복합성 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-109">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="7cf29-110">예를 들어 연결의 끝에 복합성 one (1) 및 many ()가 있는 경우 연결을 일대다 \* 연결 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-110">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="7cf29-111">다음 예에서 `PublishedBy` 연결은 일대다 연결입니다. 즉, 한 명의 발행자가 많은 책을 출판하고 책 하나는 한 명의 발행자에 의해 출판됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-111">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="7cf29-112">`WrittenBy` 연결은 다대다 연결입니다. 한 권의 책에 저자가 여러 명일 수 있고 한 명의 저자가 여러 책을 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-112">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cf29-113">예제</span><span class="sxs-lookup"><span data-stu-id="7cf29-113">Example</span></span>  

 <span data-ttu-id="7cf29-114">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-114">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="7cf29-115">`PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-115">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="7cf29-116">끝의 복합성은 `Publisher` 1이 고, 끝의 복합성은 `Book` 다 수 ( \* )입니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-116">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="7cf29-118">ADO.NET Entity Framework에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-118">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="7cf29-119">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf29-119">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="7cf29-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7cf29-120">See also</span></span>

- [<span data-ttu-id="7cf29-121">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="7cf29-121">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="7cf29-122">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="7cf29-122">Entity Data Model</span></span>](entity-data-model.md)
