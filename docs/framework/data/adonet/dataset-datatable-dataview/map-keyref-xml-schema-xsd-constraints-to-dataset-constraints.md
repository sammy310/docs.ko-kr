---
description: '자세히 알아보기: 데이터 집합 제약 조건에 keyref XSD (XML 스키마) 제약 조건 매핑'
title: 데이터 세트 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: f9925cf68e0c8fd1258eeeb509664e0527e58526
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651979"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="8cb25-103">데이터 세트 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="8cb25-103">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="8cb25-104">**Keyref** 요소를 사용 하면 문서 내의 요소 간에 링크를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-104">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="8cb25-105">이 링크는 관계형 데이터베이스의 외래 키 관계와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-105">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="8cb25-106">스키마에서 **keyref** 요소를 지정 하는 경우 요소는 스키마 매핑 프로세스 중에의 테이블에 있는 열에 대 한 해당 foreign key 제약 조건으로 변환 됩니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="8cb25-106">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="8cb25-107">기본적으로 **keyref** 요소는 관계에 지정 된 **parenttable**, **Childtable**, **parenttable** 및 **childtable** 속성을 사용 하 여 관계를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-107">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="8cb25-108">다음 표에서는 **keyref** 요소에 지정할 수 있는 **msdata** 특성을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-108">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="8cb25-109">특성 이름</span><span class="sxs-lookup"><span data-stu-id="8cb25-109">Attribute name</span></span>|<span data-ttu-id="8cb25-110">설명</span><span class="sxs-lookup"><span data-stu-id="8cb25-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8cb25-111">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="8cb25-111">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="8cb25-112">스키마의 **keyref** 요소에 **ConstraintOnly = "true"** 를 지정 하면 제약 조건이 만들어지지만 관계는 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-112">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="8cb25-113">이 특성을 지정 하지 않거나 **False** 로 설정 하면 **데이터 집합** 에 제약 조건과 관계가 모두 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-113">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="8cb25-114">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="8cb25-114">**msdata:ConstraintName**</span></span>|<span data-ttu-id="8cb25-115">**ConstraintName** 특성을 지정 하면 해당 값이 제약 조건의 이름으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-115">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="8cb25-116">그렇지 않으면 스키마에서 **keyref** 요소의 **Name** 특성은 **데이터 집합** 에 제약 조건 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-116">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="8cb25-117">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="8cb25-117">**msdata:UpdateRule**</span></span>|<span data-ttu-id="8cb25-118">**UpdateRule** 특성이 스키마의 **keyref** 요소에 지정 된 경우 해당 값은 **데이터 집합** 의 **UpdateRule** 제약 조건 속성에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-118">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="8cb25-119">그렇지 않으면 **UpdateRule** 속성이 **Cascade** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-119">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="8cb25-120">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="8cb25-120">**msdata:DeleteRule**</span></span>|<span data-ttu-id="8cb25-121">**DeleteRule** 특성이 스키마의 **keyref** 요소에 지정 된 경우 해당 값은 **데이터 집합** 의 **DeleteRule** 제약 조건 속성에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-121">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="8cb25-122">그렇지 않으면 **DeleteRule** 속성이 **Cascade** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-122">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="8cb25-123">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="8cb25-123">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="8cb25-124">**AcceptRejectRule** 특성이 스키마의 **keyref** 요소에 지정 된 경우 해당 값은 **데이터 집합** 의 **AcceptRejectRule** 제약 조건 속성에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-124">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="8cb25-125">그렇지 않으면 **AcceptRejectRule** 속성을 **None** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-125">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="8cb25-126">다음 예제에는 **Order** 요소의 **ordernumber** 자식 요소와 **ordernumber** 요소의 **ordernumber** 자식 요소 간에 **key** 및 **keyref** 관계를 지정 하는 스키마가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-126">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="8cb25-127">예제에서 **Ordernumber** 요소의 **ordernumber** 자식 요소는 **Order** 요소의 **ordernumber** 키 자식 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-127">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="8cb25-128">XSD (XML 스키마 정의 언어) 스키마 매핑 프로세스에서는 두 개의 테이블이 포함 된 다음 **데이터 집합** 을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-128">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="8cb25-129">또한 **데이터 집합** 은 다음과 같은 제약 조건을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-129">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="8cb25-130">**Order** 테이블에 대 한 unique 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-130">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="8cb25-131">**Order** 및 **orderdetail** 테이블 간의 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-131">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="8cb25-132">두 요소가 스키마에 중첩 되지 않으므로 **중첩** 된 속성은 **False** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-132">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="8cb25-133">**Orderdetail** 테이블의 foreign key 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb25-133">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8cb25-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cb25-134">See also</span></span>

- [<span data-ttu-id="8cb25-135">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="8cb25-135">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="8cb25-136">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="8cb25-136">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="8cb25-137">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="8cb25-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
