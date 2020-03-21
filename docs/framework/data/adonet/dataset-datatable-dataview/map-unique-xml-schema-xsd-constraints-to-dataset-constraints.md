---
title: 데이터 세트 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150846"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="f3ceb-102">데이터 세트 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="f3ceb-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="f3ceb-103">XML 스키마 정의 언어(XSD) 스키마에서 **고유** 요소는 요소 또는 특성에 대한 고유 성 제약 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="f3ceb-104">XML 스키마를 관계형 스키마로 변환하는 과정에서, XML 스키마의 요소나 특성에 지정된 UNIQUE 제약 조건은 생성된 해당 <xref:System.Data.DataTable>에 있는 <xref:System.Data.DataSet>의 UNIQUE 제약 조건에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="f3ceb-105">다음 표에서는 **고유한** 요소에서 지정할 수 있는 **msdata** 특성을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="f3ceb-106">특성 이름</span><span class="sxs-lookup"><span data-stu-id="f3ceb-106">Attribute name</span></span>|<span data-ttu-id="f3ceb-107">Description</span><span class="sxs-lookup"><span data-stu-id="f3ceb-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f3ceb-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="f3ceb-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="f3ceb-109">이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="f3ceb-110">그렇지 않으면 **name** 특성은 제약 조건 이름의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="f3ceb-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="f3ceb-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="f3ceb-112">고유 `PrimaryKey="true"` 요소에 있는 **unique** 경우 **IsPrimaryKey** 속성을 **true로**설정한 고유한 제약 조건이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="f3ceb-113">다음 예제에서는 **고유** 요소를 사용하여 고유 제약 조건을 지정하는 XML 스키마를 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="f3ceb-114">스키마의 **고유한** 요소는 문서 인스턴스의 모든 **Customer** 요소에 대해 **CustomerID** 자식 요소의 값이 고유해야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="f3ceb-115">**DataSet을**빌드할 때 매핑 프로세스는 이 스키마를 읽고 다음 테이블을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="f3ceb-116">매핑 프로세스는 다음 **DataSet**에 표시된 대로 **CustomerID** 열에 고유한 제약 조건을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="f3ceb-117">여기에서는 편의를 위해 관련 속성만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="f3ceb-118">생성된 **DataSet에서** **IsPrimaryKey** 속성은 고유한 제약 조건에 대해 **False로** 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="f3ceb-119">열의 **고유** 속성은 **CustomerID** 열 값이 고유해야 함을 나타냅니다(열의 **AllowDBNull** 속성에 의해 지정된 대로 null 참조일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="f3ceb-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="f3ceb-120">스키마를 수정하고 선택적 **msdata:PrimaryKey** 특성 값을 **True로**설정하면 고유한 제약 조건이 테이블에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="f3ceb-121">**AllowDBNull** 열 속성은 **false로**설정되고 제약 조건의 **IsPrimaryKey** 속성은 **True로**설정되므로 **CustomerID** 열을 기본 키 열로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="f3ceb-122">XML 스키마의 요소나 특성의 조합에 UNIQUE 제약 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="f3ceb-123">다음 예제에서는 스키마에 다른 **xs:field** 요소를 추가하여 모든 인스턴스의 **모든 고객에** 대해 **CustomerID** 및 **CompanyName** 값의 조합이 고유해야 함을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="f3ceb-124">결과 **DataSet에서**생성되는 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="f3ceb-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3ceb-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3ceb-125">See also</span></span>

- [<span data-ttu-id="f3ceb-126">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="f3ceb-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="f3ceb-127">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="f3ceb-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="f3ceb-128">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f3ceb-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
