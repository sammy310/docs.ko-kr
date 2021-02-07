---
description: '다음에 대 한 자세한 정보: 패싯'
title: 패싯
ms.date: 03/30/2017
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
ms.openlocfilehash: 195cb34b6de603859d592ee24140aec27a51418f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724312"
---
# <a name="facet"></a><span data-ttu-id="802ae-103">패싯</span><span class="sxs-lookup"><span data-stu-id="802ae-103">facet</span></span>

<span data-ttu-id="802ae-104">*패싯은* 기본 형식 속성 정의에 세부 정보를 추가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-104">A *facet* is used to add detail to a primitive type property definition.</span></span> <span data-ttu-id="802ae-105">속성 [정의에](property.md) 는 속성 형식에 대 한 정보가 포함 되어 있지만 종종 더 자세한 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-105">A [property](property.md) definition contains information about the property type, but often more detail is necessary.</span></span> <span data-ttu-id="802ae-106">예를 들어, 개념적 모델의 엔터티 형식에는 값을 null로 설정할 수 없는 `String` 형식의 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-106">For example, an entity type in a conceptual model might have a property of type `String` whose value cannot be set to null.</span></span> <span data-ttu-id="802ae-107">패싯을 사용하면 이 수준의 세부 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-107">Facets allow you to specify this level of detail.</span></span>  
  
 <span data-ttu-id="802ae-108">다음 표에서는 EDM에서 지원되는 패싯에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-108">The table below describes the facets that are supported in the EDM.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="802ae-109">패싯의 정확한 값과 동작은 EDM 구현을 사용하는 런타임 환경에서 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-109">The exact values and behaviors of facets are determined by the run-time environment that uses an EDM implementation.</span></span>  
  
|<span data-ttu-id="802ae-110">패싯</span><span class="sxs-lookup"><span data-stu-id="802ae-110">Facet</span></span>|<span data-ttu-id="802ae-111">설명</span><span class="sxs-lookup"><span data-stu-id="802ae-111">Description</span></span>|<span data-ttu-id="802ae-112">적용 대상</span><span class="sxs-lookup"><span data-stu-id="802ae-112">Applies to</span></span>|  
|-----------|-----------------|----------------|  
|`Collation`|<span data-ttu-id="802ae-113">속성 값에 대한 비교 및 순서 지정 작업을 수행할 때 사용할 데이터 정렬 순서 또는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-113">Specifies the collating sequence (or sorting sequence) to be used when performing comparison and ordering operations on values of the property.</span></span>|`String`|  
|`ConcurrencyMode`|<span data-ttu-id="802ae-114">속성 값을 낙관적 동시성 검사에 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-114">Indicates that the value of the property should be used for optimistic concurrency checks.</span></span>|<span data-ttu-id="802ae-115">모든 기본 형식 속성</span><span class="sxs-lookup"><span data-stu-id="802ae-115">All primitive type properties</span></span>|  
|`Default`|<span data-ttu-id="802ae-116">인스턴스화 시 값이 제공되지 않는 경우 속성의 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-116">Specifies the default value of the property if no value is supplied upon instantiation.</span></span>|<span data-ttu-id="802ae-117">모든 기본 형식 속성</span><span class="sxs-lookup"><span data-stu-id="802ae-117">All primitive type properties</span></span>|  
|`FixedLength`|<span data-ttu-id="802ae-118">속성 값 길이가 다양할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-118">Specifies whether the length of the property value can vary.</span></span>|<span data-ttu-id="802ae-119">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="802ae-119">`Binary`, `String`</span></span>|  
|`MaxLength`|<span data-ttu-id="802ae-120">속성 값의 최대 길이를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-120">Specifies the maximum length of the property value.</span></span>|<span data-ttu-id="802ae-121">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="802ae-121">`Binary`, `String`</span></span>|  
|`Nullable`|<span data-ttu-id="802ae-122">속성 값이 null일 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-122">Specifies whether the property can have a null value.</span></span>|<span data-ttu-id="802ae-123">모든 기본 형식 속성</span><span class="sxs-lookup"><span data-stu-id="802ae-123">All primitive type properties</span></span>|  
|`Precision`|<span data-ttu-id="802ae-124">형식이 `Decimal`인 속성의 경우 속성 값에 포함할 수 있는 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-124">For properties of type `Decimal`, specifies the number of digits a property value can have.</span></span> <span data-ttu-id="802ae-125">형식이 `Time`, `DateTime` 및 `DateTimeOffset`인 속성의 경우 속성 값에 대한 초의 소수 부분 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-125">For properties of type `Time`, `DateTime`, and `DateTimeOffset`, specifies the number of digits for the fractional part of seconds of the property value.</span></span>|<span data-ttu-id="802ae-126">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span><span class="sxs-lookup"><span data-stu-id="802ae-126">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span></span>|  
|`Scale`|<span data-ttu-id="802ae-127">속성 값에 대한 소수점 오른쪽의 자릿수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-127">Specifies the number of digits to the right of the decimal point for the property value.</span></span>|<span data-ttu-id="802ae-128">Decimal</span><span class="sxs-lookup"><span data-stu-id="802ae-128">Decimal</span></span>|  
|`Unicode`|<span data-ttu-id="802ae-129">속성 값을 유니코드로 저장할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-129">Indicates whether the property value is stored as Unicode.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="802ae-130">예제</span><span class="sxs-lookup"><span data-stu-id="802ae-130">Example</span></span>  

 <span data-ttu-id="802ae-131">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-131">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="802ae-132">다음 CSDL에서는 `Book` 엔터티 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-132">The following CSDL defines a `Book` entity type.</span></span> <span data-ttu-id="802ae-133">패싯은 XML 특성으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-133">Note that facets are implemented as XML attributes.</span></span> <span data-ttu-id="802ae-134">패싯 값은 속성을 null로 설정할 수 없으며 `Scale` 속성의 `Precision` 및 `Revision`이 각각 29로 설정됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="802ae-134">The facet values indicate that no property can be set to null, and that the `Scale` and `Precision` of the `Revision` property are each set to 29.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="802ae-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="802ae-135">See also</span></span>

- [<span data-ttu-id="802ae-136">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="802ae-136">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="802ae-137">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="802ae-137">Entity Data Model</span></span>](entity-data-model.md)
