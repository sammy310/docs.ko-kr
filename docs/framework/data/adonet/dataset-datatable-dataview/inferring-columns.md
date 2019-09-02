---
title: 열 유추
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 651d132fd76ba9015d4730a5e519bc679608e275
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203598"
---
# <a name="inferring-columns"></a><span data-ttu-id="94485-102">열 유추</span><span class="sxs-lookup"><span data-stu-id="94485-102">Inferring Columns</span></span>
<span data-ttu-id="94485-103">ADO.NET에서 XML 문서로부터 <xref:System.Data.DataSet>의 테이블로 유추할 요소를 결정한 후에는 해당 테이블의 열을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="94485-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="94485-104">ADO.NET 2.0에는 각 **simpleType** 요소에 대해 강력한 형식의 데이터 형식을 유추 하는 새로운 스키마 유추 엔진이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94485-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="94485-105">이전 버전에서는 유추 된 **simpleType** 요소의 데이터 형식이 항상 **xsd: string**이었습니다.</span><span class="sxs-lookup"><span data-stu-id="94485-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="94485-106">마이그레이션 및 이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="94485-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="94485-107">**ReadXml** 메서드는 **InferSchema**형식의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94485-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="94485-108">이 인수를 사용하면 이전 버전과 호환되는 유추 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94485-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="94485-109">**InferSchema** 열거에 사용할 수 있는 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94485-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="94485-110">항상 단순 형식을 <xref:System.String>으로 유추하여 이전 버전과의 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94485-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="94485-111">강력한 형식의 데이터 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="94485-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="94485-112"><xref:System.Data.DataTable>과 함께 사용할 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="94485-113">인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="94485-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="94485-114">특성</span><span class="sxs-lookup"><span data-stu-id="94485-114">Attributes</span></span>  
 <span data-ttu-id="94485-115">[테이블 유추](inferring-tables.md)에 정의 된 대로 특성이 있는 요소는 테이블로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-115">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="94485-116">그러면 해당 요소의 특성은 테이블의 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="94485-117">열의 **ColumnMapping** 속성은 스키마가 XML에 다시 기록 될 경우 열 이름이 특성으로 기록 되도록 mappingtype.attribute로 설정 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="94485-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="94485-118">특성 값은 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="94485-119">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="94485-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="94485-120">유추 프로세스는 **attr1** 및 **attr2**라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="94485-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="94485-121">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="94485-122">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="94485-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="94485-123">**테이블** Element1</span><span class="sxs-lookup"><span data-stu-id="94485-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="94485-124">attr1</span><span class="sxs-lookup"><span data-stu-id="94485-124">attr1</span></span>|<span data-ttu-id="94485-125">attr2</span><span class="sxs-lookup"><span data-stu-id="94485-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="94485-126">value1</span><span class="sxs-lookup"><span data-stu-id="94485-126">value1</span></span>|<span data-ttu-id="94485-127">value2</span><span class="sxs-lookup"><span data-stu-id="94485-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="94485-128">특성이나 자식 요소가 없는 요소</span><span class="sxs-lookup"><span data-stu-id="94485-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="94485-129">요소에 자식 요소나 특성이 없으면 해당 요소는 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="94485-130">열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="94485-131">자식 요소의 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="94485-132">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="94485-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="94485-133">유추 프로세스는 **ChildElement1** 및 **childelement2 라는**라는 두 개의 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="94485-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="94485-134">두 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94485-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="94485-135">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="94485-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="94485-136">**테이블** Element1</span><span class="sxs-lookup"><span data-stu-id="94485-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="94485-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="94485-137">ChildElement1</span></span>|<span data-ttu-id="94485-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="94485-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="94485-139">Text1</span><span class="sxs-lookup"><span data-stu-id="94485-139">Text1</span></span>|<span data-ttu-id="94485-140">Text2</span><span class="sxs-lookup"><span data-stu-id="94485-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94485-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="94485-141">See also</span></span>

- [<span data-ttu-id="94485-142">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="94485-142">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="94485-143">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="94485-143">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="94485-144">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="94485-144">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="94485-145">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="94485-145">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="94485-146">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="94485-146">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="94485-147">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="94485-147">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
