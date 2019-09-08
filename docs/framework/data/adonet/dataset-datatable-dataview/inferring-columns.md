---
title: 열 유추
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 2718cbcf29799f99c8648b129fdb6079a6f6d344
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786183"
---
# <a name="inferring-columns"></a><span data-ttu-id="0e2d2-102">열 유추</span><span class="sxs-lookup"><span data-stu-id="0e2d2-102">Inferring Columns</span></span>
<span data-ttu-id="0e2d2-103">ADO.NET에서 XML 문서로부터 <xref:System.Data.DataSet>의 테이블로 유추할 요소를 결정한 후에는 해당 테이블의 열을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="0e2d2-104">ADO.NET 2.0에는 각 **simpleType** 요소에 대해 강력한 형식의 데이터 형식을 유추 하는 새로운 스키마 유추 엔진이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="0e2d2-105">이전 버전에서는 유추 된 **simpleType** 요소의 데이터 형식이 항상 **xsd: string**이었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="0e2d2-106">마이그레이션 및 이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="0e2d2-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="0e2d2-107">**ReadXml** 메서드는 **InferSchema**형식의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="0e2d2-108">이 인수를 사용하면 이전 버전과 호환되는 유추 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="0e2d2-109">**InferSchema** 열거에 사용할 수 있는 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="0e2d2-110">항상 단순 형식을 <xref:System.String>으로 유추하여 이전 버전과의 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="0e2d2-111">강력한 형식의 데이터 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="0e2d2-112"><xref:System.Data.DataTable>과 함께 사용할 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="0e2d2-113">인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="0e2d2-114">특성</span><span class="sxs-lookup"><span data-stu-id="0e2d2-114">Attributes</span></span>  
 <span data-ttu-id="0e2d2-115">[테이블 유추](inferring-tables.md)에 정의 된 대로 특성이 있는 요소는 테이블로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-115">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="0e2d2-116">그러면 해당 요소의 특성은 테이블의 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="0e2d2-117">열의 **ColumnMapping** 속성은 스키마가 XML에 다시 기록 될 경우 열 이름이 특성으로 기록 되도록 mappingtype.attribute로 설정 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="0e2d2-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="0e2d2-118">특성 값은 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="0e2d2-119">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="0e2d2-120">유추 프로세스는 **attr1** 및 **attr2**라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="0e2d2-121">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="0e2d2-122">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="0e2d2-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="0e2d2-123">**테이블** Element1</span><span class="sxs-lookup"><span data-stu-id="0e2d2-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="0e2d2-124">attr1</span><span class="sxs-lookup"><span data-stu-id="0e2d2-124">attr1</span></span>|<span data-ttu-id="0e2d2-125">attr2</span><span class="sxs-lookup"><span data-stu-id="0e2d2-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="0e2d2-126">value1</span><span class="sxs-lookup"><span data-stu-id="0e2d2-126">value1</span></span>|<span data-ttu-id="0e2d2-127">value2</span><span class="sxs-lookup"><span data-stu-id="0e2d2-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="0e2d2-128">특성이나 자식 요소가 없는 요소</span><span class="sxs-lookup"><span data-stu-id="0e2d2-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="0e2d2-129">요소에 자식 요소나 특성이 없으면 해당 요소는 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="0e2d2-130">열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="0e2d2-131">자식 요소의 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="0e2d2-132">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="0e2d2-133">유추 프로세스는 **ChildElement1** 및 **childelement2 라는**라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="0e2d2-134">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2d2-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="0e2d2-135">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="0e2d2-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="0e2d2-136">**테이블** Element1</span><span class="sxs-lookup"><span data-stu-id="0e2d2-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="0e2d2-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="0e2d2-137">ChildElement1</span></span>|<span data-ttu-id="0e2d2-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="0e2d2-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="0e2d2-139">Text1</span><span class="sxs-lookup"><span data-stu-id="0e2d2-139">Text1</span></span>|<span data-ttu-id="0e2d2-140">Text2</span><span class="sxs-lookup"><span data-stu-id="0e2d2-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e2d2-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e2d2-141">See also</span></span>

- [<span data-ttu-id="0e2d2-142">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="0e2d2-142">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="0e2d2-143">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="0e2d2-143">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="0e2d2-144">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="0e2d2-144">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="0e2d2-145">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="0e2d2-145">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="0e2d2-146">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="0e2d2-146">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="0e2d2-147">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="0e2d2-147">ADO.NET Overview</span></span>](../ado-net-overview.md)
