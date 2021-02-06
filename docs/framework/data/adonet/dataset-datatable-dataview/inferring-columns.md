---
description: '자세히 알아보기: 열 유추'
title: 열 유추
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 528d4ea20260b5f1fbf30536eafcaec8c5f9215a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652252"
---
# <a name="inferring-columns"></a><span data-ttu-id="78328-103">열 유추</span><span class="sxs-lookup"><span data-stu-id="78328-103">Inferring Columns</span></span>

<span data-ttu-id="78328-104">ADO.NET에서 XML 문서로부터 <xref:System.Data.DataSet>의 테이블로 유추할 요소를 결정한 후에는 해당 테이블의 열을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="78328-104">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="78328-105">ADO.NET 2.0에는 각 **simpleType** 요소에 대해 강력한 형식의 데이터 형식을 유추 하는 새로운 스키마 유추 엔진이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="78328-105">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="78328-106">이전 버전에서는 유추 된 **simpleType** 요소의 데이터 형식이 항상 **xsd: string** 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="78328-106">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="78328-107">마이그레이션 및 이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="78328-107">Migration and Backward Compatibility</span></span>  

 <span data-ttu-id="78328-108">**ReadXml** 메서드는 **InferSchema** 형식의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78328-108">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="78328-109">이 인수를 사용하면 이전 버전과 호환되는 유추 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78328-109">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="78328-110">**InferSchema** 열거에 사용할 수 있는 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78328-110">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="78328-111">항상 단순 형식을 <xref:System.String>으로 유추하여 이전 버전과의 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78328-111">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="78328-112">강력한 형식의 데이터 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="78328-112">Infers a strongly typed data type.</span></span> <span data-ttu-id="78328-113"><xref:System.Data.DataTable>과 함께 사용할 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-113">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="78328-114">인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="78328-114">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="78328-115">특성</span><span class="sxs-lookup"><span data-stu-id="78328-115">Attributes</span></span>  

 <span data-ttu-id="78328-116">[테이블 유추](inferring-tables.md)에 정의 된 대로 특성이 있는 요소는 테이블로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-116">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="78328-117">그러면 해당 요소의 특성은 테이블의 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-117">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="78328-118">열의 **ColumnMapping** 속성은 스키마가 XML에 다시 기록 될 경우 열 이름이 특성으로 기록 되도록 mappingtype.attribute로 설정 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="78328-118">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="78328-119">특성 값은 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-119">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="78328-120">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="78328-120">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="78328-121">유추 프로세스는 **attr1** 및 **attr2** 라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="78328-121">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="78328-122">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-122">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="78328-123">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="78328-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="78328-124">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="78328-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="78328-125">attr1</span><span class="sxs-lookup"><span data-stu-id="78328-125">attr1</span></span>|<span data-ttu-id="78328-126">attr2</span><span class="sxs-lookup"><span data-stu-id="78328-126">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="78328-127">value1</span><span class="sxs-lookup"><span data-stu-id="78328-127">value1</span></span>|<span data-ttu-id="78328-128">value2</span><span class="sxs-lookup"><span data-stu-id="78328-128">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="78328-129">특성이나 자식 요소가 없는 요소</span><span class="sxs-lookup"><span data-stu-id="78328-129">Elements Without Attributes or Child Elements</span></span>  

 <span data-ttu-id="78328-130">요소에 자식 요소나 특성이 없으면 해당 요소는 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-130">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="78328-131">열의 **ColumnMapping** 속성은 **mappingtype.attribute** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-131">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="78328-132">자식 요소의 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-132">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="78328-133">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="78328-133">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="78328-134">유추 프로세스는 **ChildElement1** 및 **childelement2 라는** 라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="78328-134">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="78328-135">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78328-135">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="78328-136">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="78328-136">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="78328-137">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="78328-137">**Table:** Element1</span></span>  
  
|<span data-ttu-id="78328-138">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="78328-138">ChildElement1</span></span>|<span data-ttu-id="78328-139">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="78328-139">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="78328-140">Text1</span><span class="sxs-lookup"><span data-stu-id="78328-140">Text1</span></span>|<span data-ttu-id="78328-141">Text2</span><span class="sxs-lookup"><span data-stu-id="78328-141">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78328-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78328-142">See also</span></span>

- [<span data-ttu-id="78328-143">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="78328-143">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="78328-144">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="78328-144">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="78328-145">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="78328-145">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="78328-146">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="78328-146">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="78328-147">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="78328-147">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="78328-148">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="78328-148">ADO.NET Overview</span></span>](../ado-net-overview.md)
