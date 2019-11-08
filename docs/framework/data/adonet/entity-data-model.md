---
title: 엔터티 데이터 모델
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: ed834c57104e9f03ac337f6c1d30a0498bd42a06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738415"
---
# <a name="entity-data-model"></a><span data-ttu-id="66403-102">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="66403-102">Entity Data Model</span></span>
<span data-ttu-id="66403-103">EDM(엔터티 데이터 모델)은 저장된 폼에 관계없이 데이터 구조를 설명하는 개념 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="66403-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="66403-104">EDM은 Peter Chen이 1976년에 설명한 엔터티-관계 모델에서 차용하지만 엔터티-관계 모델을 기반으로 하여 기존의 사용을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="66403-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="66403-105">EDM은 데이터가 여러 폼에 저장되어 있을 경우 발생하는 문제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="66403-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="66403-106">예를 들어, 관계형 데이터베이스, 텍스트 파일, XML 파일, 스프레드시트 및 보고서에 데이터를 저장하는 비즈니스를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="66403-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="66403-107">이 경우 데이터 모델링, 애플리케이션 디자인 및 데이터 액세스가 상당히 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="66403-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="66403-108">데이터 지향 애플리케이션을 디자인하는 경우 효율적인 데이터 액세스, 스토리지 및 확장성의 손실 없이 효율적이고 유지 관리 가능한 코드를 작성하는 것이 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="66403-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="66403-109">데이터가 관계형 구조이면 데이터 액세스, 스토리지 및 확장성이 매우 효율적이지만 효율적이고 유지 관리 가능한 코드를 작성하기가 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="66403-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="66403-110">데이터가 개체 구조이면 이러한 상쇄는 반대가 됩니다. 효율적인 데이터 액세스, 스토리지 및 확장성이 저하되면 효율적이고 유지 관리 가능한 코드를 작성하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="66403-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="66403-111">이러한 상쇄 간에 적절한 균형을 찾을 수 있다고 해도 한 폼에서 다른 폼으로 데이터를 이동하는 경우 새로운 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="66403-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="66403-112">엔터티 데이터 모델은 스토리지 스키마에 독립적인 엔터티 및 관계를 기준으로 데이터 구조를 설명하여 이러한 문제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="66403-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="66403-113">이렇게 하면 저장된 데이터 폼이 애플리케이션 디자인 및 개발과 관련이 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="66403-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="66403-114">그리고 저장된 폼이 아니라 엔터티와 관계가 애플리케이션에서 사용되는 데이터 구조를 설명하기 때문에 애플리케이션 개발에 따라 엔터티와 관계도 개발될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66403-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="66403-115">`conceptual model`은 엔터티 및 관계로서의 특정 데이터 구조 표현이며, 일반적으로 EDM의 개념을 구현하는 DSL(Domain-Specific Language)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="66403-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="66403-116">[CSDL (개념 스키마 정의 언어)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) 은 이러한 도메인별 언어의 한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="66403-116">[Conceptual schema definition language (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) is an example of such a domain-specific language.</span></span> <span data-ttu-id="66403-117">개념적 모델에서 설명되는 엔터티와 관계를 애플리케이션의 개체 및 연결 추상화로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66403-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="66403-118">이렇게 하면 개발자가 스토리지 스키마에 대해 염려하지 않고 개념적 모델에 집중할 수 있으며 효율성과 유지 관리 기능을 고려하여 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66403-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="66403-119">한편, 스토리지 스키마 디자이너는 효율적인 데이터 액세스, 저장 및 확장성에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66403-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66403-120">단원 내용</span><span class="sxs-lookup"><span data-stu-id="66403-120">In This Section</span></span>  
 <span data-ttu-id="66403-121">이 단원의 항목에서는 엔터티 데이터 모델의 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66403-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="66403-122">EDM을 구현하는 모든 DSL에는 여기에 설명된 개념이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66403-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="66403-123">[ADO.NET Entity Framework](./ef/index.md) 는 CSDL을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="66403-123">Note that the [ADO.NET Entity Framework](./ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="66403-124">자세한 내용은 [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="66403-124">For more information, see [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span></span>  
  
 [<span data-ttu-id="66403-125">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="66403-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="66403-126">엔터티 데이터 모델: 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="66403-126">Entity Data Model: Namespaces</span></span>](entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="66403-127">엔터티 데이터 모델: 기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="66403-127">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="66403-128">엔터티 데이터 모델: 상속</span><span class="sxs-lookup"><span data-stu-id="66403-128">Entity Data Model: Inheritance</span></span>](entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="66403-129">연결 끝</span><span class="sxs-lookup"><span data-stu-id="66403-129">association end</span></span>](association-end.md)  
  
 [<span data-ttu-id="66403-130">연결 끝 다중성</span><span class="sxs-lookup"><span data-stu-id="66403-130">association end multiplicity</span></span>](association-end-multiplicity.md)  
  
 [<span data-ttu-id="66403-131">연결 집합</span><span class="sxs-lookup"><span data-stu-id="66403-131">association set</span></span>](association-set.md)  
  
 [<span data-ttu-id="66403-132">연결 집합 끝</span><span class="sxs-lookup"><span data-stu-id="66403-132">association set end</span></span>](association-set-end.md)  
  
 [<span data-ttu-id="66403-133">연결 형식</span><span class="sxs-lookup"><span data-stu-id="66403-133">association type</span></span>](association-type.md)  
  
 [<span data-ttu-id="66403-134">복합 형식</span><span class="sxs-lookup"><span data-stu-id="66403-134">complex type</span></span>](complex-type.md)  
  
 [<span data-ttu-id="66403-135">엔터티 컨테이너</span><span class="sxs-lookup"><span data-stu-id="66403-135">entity container</span></span>](entity-container.md)  
  
 [<span data-ttu-id="66403-136">엔터티 키</span><span class="sxs-lookup"><span data-stu-id="66403-136">entity key</span></span>](entity-key.md)  
  
 [<span data-ttu-id="66403-137">엔터티 집합</span><span class="sxs-lookup"><span data-stu-id="66403-137">entity set</span></span>](entity-set.md)  
  
 [<span data-ttu-id="66403-138">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="66403-138">entity type</span></span>](entity-type.md)  
  
 [<span data-ttu-id="66403-139">facet</span><span class="sxs-lookup"><span data-stu-id="66403-139">facet</span></span>](facet.md)  
  
 [<span data-ttu-id="66403-140">외래 키 속성</span><span class="sxs-lookup"><span data-stu-id="66403-140">foreign key property</span></span>](foreign-key-property.md)  
  
 [<span data-ttu-id="66403-141">모델 선언 함수</span><span class="sxs-lookup"><span data-stu-id="66403-141">model-declared function</span></span>](model-declared-function.md)  
  
 [<span data-ttu-id="66403-142">모델 정의 함수</span><span class="sxs-lookup"><span data-stu-id="66403-142">model-defined function</span></span>](model-defined-function.md)  
  
 [<span data-ttu-id="66403-143">탐색 속성</span><span class="sxs-lookup"><span data-stu-id="66403-143">navigation property</span></span>](navigation-property.md)  
  
 [<span data-ttu-id="66403-144">속성</span><span class="sxs-lookup"><span data-stu-id="66403-144">property</span></span>](property.md)  
  
 [<span data-ttu-id="66403-145">참조 무결성 제약 조건</span><span class="sxs-lookup"><span data-stu-id="66403-145">referential integrity constraint</span></span>](referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="66403-146">참조</span><span class="sxs-lookup"><span data-stu-id="66403-146">See also</span></span>

- <span data-ttu-id="66403-147">[ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="66403-147">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="66403-148">[.edmx 파일 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="66403-148">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="66403-149">CSDL 사양</span><span class="sxs-lookup"><span data-stu-id="66403-149">CSDL Specification</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
