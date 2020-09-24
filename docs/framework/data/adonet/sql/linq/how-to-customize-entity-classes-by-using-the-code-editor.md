---
title: '방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정'
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 5e61acc9de1ef2f00d5e81a3c3080a9dc46f074d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147699"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="d4a6b-102">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d4a6b-102">How to: Customize Entity Classes by Using the Code Editor</span></span>

<span data-ttu-id="d4a6b-103">Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 해당 엔터티 클래스를 만들거나 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-103">Developers using Visual Studio can use the Object Relational Designer to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="d4a6b-104">Visual Studio 코드 편집기를 사용 하 여 사용자 고유의 매핑 코드를 작성 하거나 이미 생성 된 코드를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="d4a6b-105">자세한 내용은 [특성 기반 매핑](attribute-based-mapping.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-105">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="d4a6b-106">이 단원의 항목에서는 개체 모델을 사용자 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="d4a6b-107">방법: 데이터베이스 이름 지정</span><span class="sxs-lookup"><span data-stu-id="d4a6b-107">How to: Specify Database Names</span></span>](how-to-specify-database-names.md)  
 <span data-ttu-id="d4a6b-108"><xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-109">방법: 클래스로 테이블 표현</span><span class="sxs-lookup"><span data-stu-id="d4a6b-109">How to: Represent Tables as Classes</span></span>](how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="d4a6b-110"><xref:System.Data.Linq.Mapping.TableAttribute>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="d4a6b-111">방법: 클래스 멤버로 열 표현</span><span class="sxs-lookup"><span data-stu-id="d4a6b-111">How to: Represent Columns as Class Members</span></span>](how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="d4a6b-112"><xref:System.Data.Linq.Mapping.ColumnAttribute>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="d4a6b-113">방법: 기본 키 표현</span><span class="sxs-lookup"><span data-stu-id="d4a6b-113">How to: Represent Primary Keys</span></span>](how-to-represent-primary-keys.md)  
 <span data-ttu-id="d4a6b-114"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-115">방법: 데이터베이스 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="d4a6b-115">How to: Map Database Relationships</span></span>](how-to-map-database-relationships.md)  
 <span data-ttu-id="d4a6b-116"><xref:System.Data.Linq.Mapping.AssociationAttribute> 특성을 사용한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="d4a6b-117">방법: 열을 데이터베이스에서 생성된 열로 표현</span><span class="sxs-lookup"><span data-stu-id="d4a6b-117">How to: Represent Columns as Database-Generated</span></span>](how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="d4a6b-118"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-119">방법: 열을 타임스탬프 또는 버전 열로 표현</span><span class="sxs-lookup"><span data-stu-id="d4a6b-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="d4a6b-120"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-121">방법: 데이터베이스 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="d4a6b-121">How to: Specify Database Data Types</span></span>](how-to-specify-database-data-types.md)  
 <span data-ttu-id="d4a6b-122"><xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-123">방법: 계산 열 표현</span><span class="sxs-lookup"><span data-stu-id="d4a6b-123">How to: Represent Computed Columns</span></span>](how-to-represent-computed-columns.md)  
 <span data-ttu-id="d4a6b-124"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-125">방법: 전용 스토리지 필드 지정</span><span class="sxs-lookup"><span data-stu-id="d4a6b-125">How to: Specify Private Storage Fields</span></span>](how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="d4a6b-126"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-127">방법: 열을 NULL 값을 허용하는 열로 표현</span><span class="sxs-lookup"><span data-stu-id="d4a6b-127">How to: Represent Columns as Allowing Null Values</span></span>](how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="d4a6b-128"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="d4a6b-129">방법: 상속 계층 구조 매핑</span><span class="sxs-lookup"><span data-stu-id="d4a6b-129">How to: Map Inheritance Hierarchies</span></span>](how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="d4a6b-130">상속 계층 구조를 지정할 수 있는 매핑하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="d4a6b-131">방법: 동시성 충돌 확인 지정</span><span class="sxs-lookup"><span data-stu-id="d4a6b-131">How to: Specify Concurrency-Conflict Checking</span></span>](how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="d4a6b-132"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4a6b-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a6b-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4a6b-133">See also</span></span>

- [<span data-ttu-id="d4a6b-134">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="d4a6b-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
