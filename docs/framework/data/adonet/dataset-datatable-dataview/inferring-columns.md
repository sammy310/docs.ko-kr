---
title: 열 유추
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 45d27b78b5d83d333c16192e172e7b7e3dd88c10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164703"
---
# <a name="inferring-columns"></a><span data-ttu-id="30466-102">열 유추</span><span class="sxs-lookup"><span data-stu-id="30466-102">Inferring Columns</span></span>

<span data-ttu-id="30466-103">ADO.NET에서 XML 문서로부터 <xref:System.Data.DataSet>의 테이블로 유추할 요소를 결정한 후에는 해당 테이블의 열을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="30466-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="30466-104">ADO.NET 2.0에는 각 **simpleType** 요소에 대해 강력한 형식의 데이터 형식을 유추 하는 새로운 스키마 유추 엔진이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30466-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="30466-105">이전 버전에서는 유추 된 **simpleType** 요소의 데이터 형식이 항상 **xsd: string**이었습니다.</span><span class="sxs-lookup"><span data-stu-id="30466-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="30466-106">마이그레이션 및 이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="30466-106">Migration and Backward Compatibility</span></span>  

 <span data-ttu-id="30466-107">**ReadXml** 메서드는 **InferSchema**형식의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30466-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="30466-108">이 인수를 사용하면 이전 버전과 호환되는 유추 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30466-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="30466-109">**InferSchema** 열거에 사용할 수 있는 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30466-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="30466-110">항상 단순 형식을 <xref:System.String>으로 유추하여 이전 버전과의 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30466-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="30466-111">강력한 형식의 데이터 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="30466-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="30466-112"><xref:System.Data.DataTable>과 함께 사용할 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="30466-113">인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="30466-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="30466-114">특성</span><span class="sxs-lookup"><span data-stu-id="30466-114">Attributes</span></span>  

 <span data-ttu-id="30466-115">[테이블 유추](inferring-tables.md)에 정의 된 대로 특성이 있는 요소는 테이블로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-115">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="30466-116">그러면 해당 요소의 특성은 테이블의 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="30466-117">열의 **ColumnMapping** 속성은 스키마가 XML에 다시 기록 될 경우 열 이름이 특성으로 기록 되도록 mappingtype.attribute로 설정 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="30466-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="30466-118">특성 값은 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="30466-119">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="30466-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="30466-120">유추 프로세스는 **attr1** 및 **attr2**라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="30466-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="30466-121">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="30466-122">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="30466-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="30466-123">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="30466-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="30466-124">attr1</span><span class="sxs-lookup"><span data-stu-id="30466-124">attr1</span></span>|<span data-ttu-id="30466-125">attr2</span><span class="sxs-lookup"><span data-stu-id="30466-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="30466-126">value1</span><span class="sxs-lookup"><span data-stu-id="30466-126">value1</span></span>|<span data-ttu-id="30466-127">value2</span><span class="sxs-lookup"><span data-stu-id="30466-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="30466-128">특성이나 자식 요소가 없는 요소</span><span class="sxs-lookup"><span data-stu-id="30466-128">Elements Without Attributes or Child Elements</span></span>  

 <span data-ttu-id="30466-129">요소에 자식 요소나 특성이 없으면 해당 요소는 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="30466-130">열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="30466-131">자식 요소의 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="30466-132">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="30466-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="30466-133">유추 프로세스는 **ChildElement1** 및 **childelement2 라는**라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="30466-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="30466-134">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30466-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="30466-135">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="30466-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="30466-136">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="30466-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="30466-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="30466-137">ChildElement1</span></span>|<span data-ttu-id="30466-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="30466-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="30466-139">Text1</span><span class="sxs-lookup"><span data-stu-id="30466-139">Text1</span></span>|<span data-ttu-id="30466-140">Text2</span><span class="sxs-lookup"><span data-stu-id="30466-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30466-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30466-141">See also</span></span>

- [<span data-ttu-id="30466-142">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="30466-142">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="30466-143">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="30466-143">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="30466-144">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="30466-144">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="30466-145">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="30466-145">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="30466-146">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="30466-146">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="30466-147">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="30466-147">ADO.NET Overview</span></span>](../ado-net-overview.md)
