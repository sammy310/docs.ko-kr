---
description: '자세한 정보: XML 스키마에서 데이터 집합 관계 생성 (XSD)'
title: XSD(XML 스키마)에서 데이터 세트 관계 생성
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: e18ae451085f536e7fe35053fadab35e30dbc225
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652460"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="11241-103">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="11241-103">Generating DataSet Relations from XML Schema (XSD)</span></span>

<span data-ttu-id="11241-104"><xref:System.Data.DataSet>에서는 부모-자식 관계를 만들어 둘 이상의 열을 연결시킵니다.</span><span class="sxs-lookup"><span data-stu-id="11241-104">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="11241-105">XSD (XML 스키마 정의 언어) 스키마 내에서는 세 가지 방법으로 **데이터 집합** 관계를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11241-105">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="11241-106">중첩된 복합 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-106">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="11241-107">**Msdata: Relationship** 주석을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-107">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="11241-108">**Msdata: ConstraintOnly** 주석을 사용 하지 않고 **xs: keyref** 를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-108">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="11241-109">중첩된 복합 형식</span><span class="sxs-lookup"><span data-stu-id="11241-109">Nested Complex Types</span></span>  

 <span data-ttu-id="11241-110">스키마에서 중첩된 복합 형식의 정의는 요소의 부모-자식 관계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11241-110">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="11241-111">다음 XML 스키마 조각에서는 **Orderdetail** 이 **Order** 요소의 자식 요소 임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11241-111">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="11241-112">XML 스키마 매핑 프로세스에서는 스키마의 중첩 된 복합 형식에 해당 하는 **데이터 집합** 에 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11241-112">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="11241-113">또한 **-** 생성 된 테이블에 대 한 부모 자식 열로 사용 되는 추가 열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11241-113">It also creates additional columns that are used as parent **-** child columns for the generated tables.</span></span> <span data-ttu-id="11241-114">이러한 부모 **-** 자식 열은 관계를 지정 하며이는 기본 키/외래 키 제약 조건을 지정 하는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="11241-114">Note that these parent **-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="11241-115">msdata:Relationship 주석</span><span class="sxs-lookup"><span data-stu-id="11241-115">msdata:Relationship Annotation</span></span>  

 <span data-ttu-id="11241-116">**Msdata: Relationship** 주석을 사용 하면 중첩 되지 않은 스키마의 요소 간에 부모-자식 관계를 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11241-116">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="11241-117">다음 예에서는 **Relationship** 요소의 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11241-117">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="11241-118">**Msdata: relationship** 주석의 특성은 부모-자식 관계와 관련 된 요소 뿐만 아니라 **parentkey** 및 **childkey** 요소와 관계에 포함 된 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-118">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="11241-119">매핑 프로세스에서는이 정보를 사용 하 여 **데이터 집합** 에 테이블을 생성 하 고 이러한 테이블 간에 기본 키/외래 키 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11241-119">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="11241-120">예를 들어 다음 스키마 조각은 동일한 수준 (중첩 되지 않음)에서 **Order** 및 **orderdetail** 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-120">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="11241-121">이 스키마는 이러한 두 요소 간의 부모-자식 관계를 지정 하는 **msdata: Relationship** 주석을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-121">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="11241-122">이 경우 **msdata: relationship** 주석을 사용 하 여 명시적 관계를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-122">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="11241-123">매핑 프로세스에서는 **Relationship** 요소를 사용 하 여 **Order** 테이블의 **Ordernumber** 열과 **데이터 집합** 에 있는 **ordernumber** 테이블의 **ordernumber** 열 간에 부모-자식 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11241-123">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="11241-124">매핑 프로세스에서는 관계만 지정합니다. 즉, 관계형 데이터베이스의 기본 키/외래 키 제약 조건처럼 이러한 열의 값에 대해 제약 조건을 자동으로 지정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11241-124">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="11241-125">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="11241-125">In This Section</span></span>  

 [<span data-ttu-id="11241-126">중첩된 스키마 요소 사이에 암시적 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="11241-126">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="11241-127">XML 스키마에서 중첩 된 요소가 발견 될 때 **데이터 집합** 에서 암시적으로 만들어지는 제약 조건 및 관계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-127">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="11241-128">중첩된 요소에 지정된 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="11241-128">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="11241-129">XML 스키마의 중첩 된 요소에 대 한 **데이터 집합** 에서 관계를 명시적으로 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-129">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="11241-130">중첩 없이 요소 사이에 관계 지정</span><span class="sxs-lookup"><span data-stu-id="11241-130">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="11241-131">중첩 되지 않은 XML 스키마 요소 간에 **데이터 집합** 에서 관계를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-131">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="11241-132">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="11241-132">Related Sections</span></span>  

 [<span data-ttu-id="11241-133">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="11241-133">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="11241-134">XSD (XML 스키마 정의 언어) 스키마에서 생성 되는 **데이터 집합** 의 관계형 구조 또는 스키마에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-134">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="11241-135">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="11241-135">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="11241-136">**데이터 집합** 에서 unique 및 foreign key 제약 조건을 만드는 데 사용 되는 XML 스키마 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11241-136">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11241-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11241-137">See also</span></span>

- [<span data-ttu-id="11241-138">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="11241-138">ADO.NET Overview</span></span>](../ado-net-overview.md)
