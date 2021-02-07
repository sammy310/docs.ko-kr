---
description: '자세한 정보: 외래 키 속성'
title: 외래 키 속성
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 1666e4477c09dd5d0ed3d2c35a93ca21824e8a0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724130"
---
# <a name="foreign-key-property"></a><span data-ttu-id="4e164-103">외래 키 속성</span><span class="sxs-lookup"><span data-stu-id="4e164-103">foreign key property</span></span>

<span data-ttu-id="4e164-104">EDM (엔터티 데이터 모델)의 *외래 키 속성* 은 다른 엔터티 형식의 [엔터티 키](entity-key.md) 를 포함 하는 [엔터티 형식](entity-type.md) 에 대 한 기본 형식 [속성](property.md) (또는 기본 형식 속성 집합)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-104">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](property.md) (or a set of primitive type properties) on an [entity type](entity-type.md) that contains the [entity key](entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="4e164-105">외래 키 속성은 관계형 데이터베이스의 외래 키 열과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-105">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="4e164-106">관계형 데이터베이스에서 외래 키 열을 사용 하 여 테이블의 행 간 관계를 만드는 것과 마찬가지로 개념적 모델의 외래 키 속성은 엔터티 형식 간의 [연결](association-type.md) 을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-106">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](association-type.md) between entity types.</span></span> <span data-ttu-id="4e164-107">[참조 무결성 제약 조건은](referential-integrity-constraint.md) 형식 중 하나에 외래 키 속성이 있는 경우 두 엔터티 형식 간의 연결을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-107">A [referential integrity constraint](referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e164-108">예제</span><span class="sxs-lookup"><span data-stu-id="4e164-108">Example</span></span>  

 <span data-ttu-id="4e164-109">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-109">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="4e164-110">`Book` 엔터티 형식에는 `PublisherId` 연결에 참조 무결성 제약 조건을 정의할 때 `Publisher` 엔터티 형식의 엔터티 키를 참조하는 `PublishedBy` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-110">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="4e164-111">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "참조 제약 조건 모델 예")</span><span class="sxs-lookup"><span data-stu-id="4e164-111">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="4e164-112">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-112">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="4e164-113">다음 CSDL에서는 외래 키 속성 `PublisherId`를 사용하여 위의 개념적 모델에 표시된 `PublishedBy` 연결에 참조 무결성 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4e164-113">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="4e164-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e164-114">See also</span></span>

- [<span data-ttu-id="4e164-115">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="4e164-115">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="4e164-116">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="4e164-116">Entity Data Model</span></span>](entity-data-model.md)
