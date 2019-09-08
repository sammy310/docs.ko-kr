---
title: 참조 무결성 제약 조건
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 28880c7085f8b4e3dd2e51b5633c1f0e2a984a4b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794447"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="51871-102">참조 무결성 제약 조건</span><span class="sxs-lookup"><span data-stu-id="51871-102">referential integrity constraint</span></span>
<span data-ttu-id="51871-103">EDM (엔터티 데이터 모델)의 *참조 무결성 제약 조건은* 관계형 데이터베이스의 참조 무결성 제약 조건과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="51871-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="51871-104">데이터베이스 테이블의 열이 다른 테이블의 기본 키를 참조할 수 있는 것과 동일한 방식으로 [엔터티 형식의](entity-type.md) [속성](property.md) 은 다른 엔터티 형식의 [엔터티 키](entity-key.md) 를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51871-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](property.md) (or properties) of an [entity type](entity-type.md) can reference the [entity key](entity-key.md) of another entity type.</span></span> <span data-ttu-id="51871-105">참조 되는 엔터티 형식을 제약 조건의 *주 끝* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="51871-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="51871-106">주 끝을 참조 하는 엔터티 형식을 제약 조건의 *종속 끝* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="51871-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="51871-107">참조 무결성 제약 조건은 두 엔터티 형식 간의 [연결](association-type.md) 의 일부로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51871-107">A referential integrity constraint is defined as part of an [association](association-type.md) between two entity types.</span></span> <span data-ttu-id="51871-108">참조 무결성 제약 조건 정의에서는 다음 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51871-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="51871-109">제약 조건의 주 끝</span><span class="sxs-lookup"><span data-stu-id="51871-109">The principal end of the constraint.</span></span> <span data-ttu-id="51871-110">(엔터티 키가 종속 끝에서 참조되는 엔터티 형식)</span><span class="sxs-lookup"><span data-stu-id="51871-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="51871-111">주 끝의 엔터티 키</span><span class="sxs-lookup"><span data-stu-id="51871-111">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="51871-112">제약 조건의 종속 끝</span><span class="sxs-lookup"><span data-stu-id="51871-112">The dependent end of the constraint.</span></span> <span data-ttu-id="51871-113">(주 끝의 엔터티 키를 참조하는 속성이 있는 엔터티 형식)</span><span class="sxs-lookup"><span data-stu-id="51871-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="51871-114">종속 끝의 참조 속성</span><span class="sxs-lookup"><span data-stu-id="51871-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="51871-115">EDM의 참조 무결성 제약 조건은 항상 올바른 연결이 존재하도록 보장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51871-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="51871-116">자세한 내용은 [외래 키 속성](foreign-key-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51871-116">For more information, see [foreign key property](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51871-117">예제</span><span class="sxs-lookup"><span data-stu-id="51871-117">Example</span></span>  
 <span data-ttu-id="51871-118">다음 다이어그램에서는 두 연결 `WrittenBy` 및 `PublishedBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51871-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="51871-119">`Book` 엔터티 형식에는 `PublisherId` 연결에 참조 무결성 제약 조건을 정의할 때 `Publisher` 엔터티 형식의 엔터티 키를 참조하는 `PublishedBy` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51871-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="51871-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "참조 제약 조건 모델 예")</span><span class="sxs-lookup"><span data-stu-id="51871-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="51871-121">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](./ef/language-reference/csdl-specification.md)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="51871-121">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="51871-122">다음 CSDL에서는 위의 개념적 모델에 표시된 `PublishedBy` 연결에 참조 무결성 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51871-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="51871-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="51871-123">See also</span></span>

- [<span data-ttu-id="51871-124">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="51871-124">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="51871-125">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="51871-125">Entity Data Model</span></span>](entity-data-model.md)
