---
title: XSD(XML 스키마)에서 데이터 세트 관계 생성
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151132"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="31bad-102">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="31bad-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="31bad-103"><xref:System.Data.DataSet>에서는 부모-자식 관계를 만들어 둘 이상의 열을 연결시킵니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="31bad-104">XML 스키마 정의 언어(XSD) 스키마 내에서 **데이터 집합** 관계를 나타내는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="31bad-105">중첩된 복합 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="31bad-106">**msdata:관계** 추가를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="31bad-107">**msdata:ConstraintOnly** 추가 가 없는 **xs:keyref를** 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="31bad-108">중첩된 복합 형식</span><span class="sxs-lookup"><span data-stu-id="31bad-108">Nested Complex Types</span></span>  
 <span data-ttu-id="31bad-109">스키마에서 중첩된 복합 형식의 정의는 요소의 부모-자식 관계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="31bad-110">다음 XML 스키마 조각은 **OrderDetail이** **Order** 요소의 자식 요소임을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="31bad-111">XML 스키마 매핑 프로세스는 스키마에 중첩된 복합 형식에 해당하는 **DataSet의** 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="31bad-112">또한 생성된 테이블에 대한 상위**-** 자식 열로 사용되는 추가 열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="31bad-113">이러한 상위**-** 자식 열은 기본 키/외래 키 제약 조건을 지정하는 것과 같지 않은 관계를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="31bad-114">msdata:Relationship 주석</span><span class="sxs-lookup"><span data-stu-id="31bad-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="31bad-115">**msdata:Relationship** 기능을 사용하면 중첩되지 않은 스키마의 요소 간에 부모-자식 관계를 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="31bad-116">다음 예제에서는 **관계** 요소의 구조를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="31bad-117">**msdata:Relationship** 추가의 특성은 부모-자식 관계에 관련된 요소뿐만 아니라 관계에 관련된 **부모 키** 및 **자식 키** 요소 및 특성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="31bad-118">매핑 프로세스는 이 정보를 사용하여 **DataSet에서** 테이블을 생성하고 이러한 테이블 간의 기본 키/외래 키 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="31bad-119">예를 들어 다음 스키마 조각은 **동일한** 수준(중첩되지 않음)에서 Order 및 **OrderDetail** 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="31bad-120">스키마는 **msdata:Relationship** 추가를 지정하여 이러한 두 요소 간의 부모-자식 관계를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="31bad-121">이 경우 **msdata:Relationship** 설명을 사용하여 명시적 관계를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="31bad-122">매핑 프로세스는 **관계** 요소를 사용하여 **OrderNumber** 테이블의 **OrderNumber** 열과 **DataSet의** **OrderDetail** 테이블의 **OrderNo** 열 간의 부모-자식 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="31bad-123">매핑 프로세스에서는 관계만 지정합니다. 즉, 관계형 데이터베이스의 기본 키/외래 키 제약 조건처럼 이러한 열의 값에 대해 제약 조건을 자동으로 지정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="31bad-124">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="31bad-124">In This Section</span></span>  
 [<span data-ttu-id="31bad-125">중첩된 스키마 요소 사이에 암시적 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="31bad-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="31bad-126">XML 스키마에서 중첩된 요소가 발생할 때 **DataSet에서** 암시적으로 생성되는 제약 조건 및 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="31bad-127">중첩된 요소에 지정된 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="31bad-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="31bad-128">XML 스키마의 중첩 된 요소에 대 한 **DataSet에서** 관계를 명시적으로 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="31bad-129">중첩 없이 요소 사이에 관계 지정</span><span class="sxs-lookup"><span data-stu-id="31bad-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="31bad-130">중첩되지 않은 XML 스키마 요소 간의 **DataSet에서** 관계를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="31bad-131">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="31bad-131">Related Sections</span></span>  
 [<span data-ttu-id="31bad-132">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="31bad-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="31bad-133">XML 스키마 정의 언어(XSD) 스키마에서 만든 **DataSet의** 관계형 구조 또는 스키마에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="31bad-134">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="31bad-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="31bad-135">**DataSet에서**고유 및 외래 키 제약 조건을 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31bad-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31bad-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31bad-136">See also</span></span>

- [<span data-ttu-id="31bad-137">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="31bad-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
