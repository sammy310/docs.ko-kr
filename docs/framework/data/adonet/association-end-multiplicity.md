---
title: 연결 End 복합성
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 59eed56204543adf405cfc7c71a49697a9e18374
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135033"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="51895-102">연결 End 복합성</span><span class="sxs-lookup"><span data-stu-id="51895-102">association end multiplicity</span></span>
<span data-ttu-id="51895-103">*연결 end 복합성* 개수를 정의 [엔터티 형식의](../../../../docs/framework/data/adonet/entity-type.md) 한쪽 끝에 있을 수 있는 인스턴스를 [연결](../../../../docs/framework/data/adonet/association-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51895-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="51895-104">연결 End 복합성은 다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51895-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="51895-105">일 (1): 연결 end에는 정확히 하나의 엔터티 형식 인스턴스가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51895-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="51895-106">0 또는 1 (0..1): 연결 end에 0 개 이상의 엔터티 형식 인스턴스가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51895-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="51895-107">많은 (\*): 연결 end에 0, 1 또는 더 많은 엔터티 형식 인스턴스가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51895-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="51895-108">연결은 대체로 연결 End 복합성 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51895-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="51895-109">예를 들어 연결의 end 복합성이 한 개 및 여러 (\*)에 연결-일대다 연결 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="51895-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="51895-110">다음 예에서 `PublishedBy` 연결은 일대다 연결입니다. 즉, 한 명의 발행자가 많은 책을 출판하고 책 하나는 한 명의 발행자에 의해 출판됩니다.</span><span class="sxs-lookup"><span data-stu-id="51895-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="51895-111">`WrittenBy` 연결은 다대다 연결입니다. 한 권의 책에 저자가 여러 명일 수 있고 한 명의 저자가 여러 책을 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51895-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51895-112">예제</span><span class="sxs-lookup"><span data-stu-id="51895-112">Example</span></span>  
 <span data-ttu-id="51895-113">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51895-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="51895-114">`PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="51895-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="51895-115">다중성을 `Publisher` 끝이 한 개 (1)이 고는 `Book` 끝이 많은 (\*).</span><span class="sxs-lookup"><span data-stu-id="51895-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="51895-117">ADO.NET Entity Framework 개념적 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="51895-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="51895-118">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51895-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="51895-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="51895-119">See also</span></span>

- [<span data-ttu-id="51895-120">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="51895-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="51895-121">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="51895-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
