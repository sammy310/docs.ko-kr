---
title: 엔터티 형식(entity type)
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3f99667a06d8aa439232802d4909290dfe9db97c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194780"
---
# <a name="entity-type"></a><span data-ttu-id="12a7a-102">엔터티 형식(entity type)</span><span class="sxs-lookup"><span data-stu-id="12a7a-102">entity type</span></span>

<span data-ttu-id="12a7a-103">*엔터티 형식은* EDM (엔터티 데이터 모델)을 사용 하 여 데이터 구조를 설명 하는 기본 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="12a7a-104">개념적 모델에서 엔터티 형식은 고객이나 주문과 같은 최상위 개념의 구조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="12a7a-105">엔터티 형식은 엔터티 형식 인스턴스의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="12a7a-106">각 템플릿에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-106">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="12a7a-107">고유한 이름</span><span class="sxs-lookup"><span data-stu-id="12a7a-107">A unique name.</span></span> <span data-ttu-id="12a7a-108">(필수)</span><span class="sxs-lookup"><span data-stu-id="12a7a-108">(Required.)</span></span>  
  
- <span data-ttu-id="12a7a-109">하나 이상의 속성으로 정의 된 [엔터티 키](entity-key.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-109">An [entity key](entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="12a7a-110">(필수)</span><span class="sxs-lookup"><span data-stu-id="12a7a-110">(Required.)</span></span>  
  
- <span data-ttu-id="12a7a-111">[속성](property.md)형식의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-111">Data in the form of [properties](property.md).</span></span> <span data-ttu-id="12a7a-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-112">(Optional.)</span></span>  
  
- <span data-ttu-id="12a7a-113">[연결](association-type.md) 의 한 [end](association-end.md) 에서 다른 end로의 탐색을 허용 하는 [탐색 속성](navigation-property.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-113">[Navigation properties](navigation-property.md) that allow for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="12a7a-114">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="12a7a-114">(Optional)</span></span>  
  
 <span data-ttu-id="12a7a-115">애플리케이션에서 엔터티 형식의 인스턴스는 특정 고객 또는 주문과 같은 특정 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="12a7a-116">엔터티 형식의 각 인스턴스에는 [엔터티 집합](entity-set.md)내에 고유한 [엔터티 키](entity-key.md) 가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-116">Each instance of an entity type must have a unique [entity key](entity-key.md) within an [entity set](entity-set.md).</span></span>  
  
 <span data-ttu-id="12a7a-117">두 엔터티 형식 인스턴스는 형식이 동일하고 해당 엔터티 키 값이 동일한 경우에만 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12a7a-118">예제</span><span class="sxs-lookup"><span data-stu-id="12a7a-118">Example</span></span>  

 <span data-ttu-id="12a7a-119">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="12a7a-121">엔터티 키를 구성하는 각 엔터티 형식의 속성은 "(키)"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="12a7a-122">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="12a7a-123">다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="12a7a-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="12a7a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12a7a-124">See also</span></span>

- [<span data-ttu-id="12a7a-125">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="12a7a-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="12a7a-126">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="12a7a-126">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="12a7a-127">패싯에</span><span class="sxs-lookup"><span data-stu-id="12a7a-127">facet</span></span>](facet.md)
