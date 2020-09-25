---
title: XML 스키마 제약 조건 및 관계
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 5861386e42defa189aaa50a3af0bd95d7e9257fd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173707"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="7a8f8-102">XML 스키마 제약 조건 및 관계</span><span class="sxs-lookup"><span data-stu-id="7a8f8-102">XML Schema Constraints and Relationships</span></span>

<span data-ttu-id="7a8f8-103">XSD (XML 스키마 정의 언어) 스키마에서는 **msdata: Relationship** 주석을 사용 하 여 제약 조건 (unique, key 및 keyref 제약 조건) 및 관계를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="7a8f8-104">이 항목에서는 XML 스키마에 지정된 제약 조건과 관계를 해석하여 <xref:System.Data.DataSet>을 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="7a8f8-105">일반적으로 XML 스키마에서 **데이터 집합**의 관계만 생성 하려면 **msdata: Relationship** 주석을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="7a8f8-106">자세한 내용은 [XSD (XML 스키마)에서 데이터 집합 관계 생성](generating-dataset-relations-from-xml-schema-xsd.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="7a8f8-107">**데이터 집합**에서 제약 조건을 생성 하려면 제약 조건 (unique, key 및 keyref)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="7a8f8-108">이 항목의 뒷부분에서 설명하겠지만 KEY 및 KEYREF 제약 조건도 관계를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="7a8f8-109">KEY 및 KEYREF 제약 조건에서 관계 생성</span><span class="sxs-lookup"><span data-stu-id="7a8f8-109">Generating a Relationship from key and keyref Constraints</span></span>  

 <span data-ttu-id="7a8f8-110">**Msdata: Relationship** 주석을 지정 하는 대신 XML 스키마 매핑 프로세스에서 제약 조건 뿐만 아니라 **데이터 집합**의 관계를 생성 하는 데 사용 되는 key 및 keyref 제약 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="7a8f8-111">그러나 `msdata:ConstraintOnly="true"` **keyref** 요소에를 지정 하면 **데이터 집합** 에 제약 조건만 포함 되며 관계는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="7a8f8-112">다음 예제에서는 중첩 되지 않은 **Order** 및 **orderdetail** 요소를 포함 하는 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="7a8f8-113">스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="7a8f8-114">XML 스키마 매핑 프로세스 중에 생성 되는 **데이터 집합** 에는 **Order** 및 **orderdetail** 테이블이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="7a8f8-115">또한 **데이터 집합** 에는 관계와 제약 조건이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="7a8f8-116">다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="7a8f8-117">스키마는 **msdata: Relationship** 주석을 지정 하지 않습니다. 대신 key 및 keyref 제약 조건을 사용 하 여 관계를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```text
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="7a8f8-118">이전 스키마 예제에서 **Order** 및 **orderdetail** 요소는 중첩 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="7a8f8-119">다음 스키마 예제에서는 이들 요소가 중첩됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="7a8f8-120">그러나 **msdata: Relationship** 주석이 지정 되지 않습니다. 따라서 암시적 관계가 가정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="7a8f8-121">자세한 내용은 [중첩 된 스키마 요소 간의 암시적 관계 매핑](map-implicit-relations-between-nested-schema-elements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="7a8f8-122">스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 <span data-ttu-id="7a8f8-123">XML 스키마 매핑 프로세스에서 생성 되는 **데이터 집합** 에는 두 개의 테이블이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="7a8f8-124">**데이터 집합** 에는 두 개의 관계 ( **msdata: relationship** 주석과 key 및 keyref 제약 조건을 기반으로 하는 다른 관계)와 다양 한 제약 조건이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="7a8f8-125">다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-125">The following example shows the relations and constraints.</span></span>  
  
```text
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="7a8f8-126">중첩 테이블을 참조 하는 keyref 제약 조건에 **msdata: isnested = "true"** 주석이 포함 된 경우 **데이터 집합** 은 keyref 제약 조건 및 관련 unique/key 제약 조건을 기반으로 하는 단일 중첩 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f8-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8f8-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a8f8-127">See also</span></span>

- [<span data-ttu-id="7a8f8-128">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="7a8f8-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="7a8f8-129">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="7a8f8-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
