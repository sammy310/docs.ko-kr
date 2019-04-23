---
title: 엔터티 형식(entity type)
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 026b0aef7cf2de8fe222721191afa459859701ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108266"
---
# <a name="entity-type"></a><span data-ttu-id="da441-102">엔터티 형식(entity type)</span><span class="sxs-lookup"><span data-stu-id="da441-102">entity type</span></span>
<span data-ttu-id="da441-103">합니다 *엔터티 형식* 엔터티 데이터 모델 (EDM)를 사용 하 여 데이터의 구조를 설명 하기 위한 기본적인 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="da441-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="da441-104">개념적 모델에서 엔터티 형식은 고객이나 주문과 같은 최상위 개념의 구조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da441-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="da441-105">엔터티 형식은 엔터티 형식 인스턴스의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="da441-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="da441-106">각 템플릿에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da441-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="da441-107">고유한 이름</span><span class="sxs-lookup"><span data-stu-id="da441-107">A unique name.</span></span> <span data-ttu-id="da441-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="da441-108">(Required.)</span></span>  
  
-   <span data-ttu-id="da441-109">[엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 하나 이상의 속성으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da441-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="da441-110">(필수)</span><span class="sxs-lookup"><span data-stu-id="da441-110">(Required.)</span></span>  
  
-   <span data-ttu-id="da441-111">데이터의 형태로 [속성](../../../../docs/framework/data/adonet/property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="da441-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="da441-112">필요에 따라</span><span class="sxs-lookup"><span data-stu-id="da441-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="da441-113">[탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 간에 탐색할 수 있도록 [끝](../../../../docs/framework/data/adonet/association-end.md) 의 [연결](../../../../docs/framework/data/adonet/association-type.md) 다른 end로 합니다.</span><span class="sxs-lookup"><span data-stu-id="da441-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="da441-114">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da441-114">(Optional)</span></span>  
  
 <span data-ttu-id="da441-115">응용 프로그램에서 엔터티 형식의 인스턴스는 특정 고객 또는 주문과 같은 특정 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da441-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="da441-116">엔터티 형식의 각 인스턴스는 고유 해야 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 안에 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="da441-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="da441-117">두 엔터티 형식 인스턴스는 형식이 동일하고 해당 엔터티 키 값이 동일한 경우에만 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="da441-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da441-118">예제</span><span class="sxs-lookup"><span data-stu-id="da441-118">Example</span></span>  
 <span data-ttu-id="da441-119">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da441-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="da441-121">엔터티 키를 구성하는 각 엔터티 형식의 속성은 "(키)"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da441-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="da441-122">합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da441-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="da441-123">다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="da441-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="da441-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="da441-124">See also</span></span>

- [<span data-ttu-id="da441-125">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="da441-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="da441-126">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="da441-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="da441-127">facet</span><span class="sxs-lookup"><span data-stu-id="da441-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
