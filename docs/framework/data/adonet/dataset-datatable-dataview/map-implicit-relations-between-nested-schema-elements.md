---
title: 중첩된 스키마 요소 사이에 암시적 관계 매핑
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 6fcb0b9bb7c947359c2334d3d116f5317f84af83
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586814"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="84590-102">중첩된 스키마 요소 사이에 암시적 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="84590-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="84590-103">XSD(XML 스키마 정의 언어) 스키마에는 다른 형식 내부에 중첩된 복합 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84590-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="84590-104">이 경우 매핑 프로세스에서는 기본 매핑을 적용하며 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84590-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="84590-105">각 복합 형식(부모 및 자식)에 대해 하나의 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84590-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="84590-106">부모에 unique 제약 조건이 없는 있으면 하나 라는 추가 기본 키 열 테이블 정의 *TableName*_Id 위치 *TableName* 부모 테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="84590-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="84590-107">기본 키로 추가 열을 식별 하 고 부모 테이블에서 기본 키 제약 조건 (설정 하 여 합니다 **IsPrimaryKey** 속성을 **True**).</span><span class="sxs-lookup"><span data-stu-id="84590-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="84590-108">제약 조건은 Constraint\#으로 명명되며, 여기서 \#은 1, 2, 3 등을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84590-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="84590-109">예를 들어, 첫 번째 제약 조건의 기본 이름은 Constraint1입니다.</span><span class="sxs-lookup"><span data-stu-id="84590-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="84590-110">추가 열을 부모 테이블의 기본 키를 참조하는 외래 키로 식별하는 외래 키 제약 조건을 자식 테이블에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84590-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="84590-111">제약 조건 이름은 *ParentTable_ChildTable* 여기서 *ParentTable* 은 부모 테이블의 이름 및 *ChildTable* 자식 테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="84590-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="84590-112">부모와 자식 테이블 간의 데이터 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84590-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="84590-113">다음 예제에서는 스키마를 보여 줍니다. 여기서 **OrderDetail** 의 자식 요소인 **순서**합니다.</span><span class="sxs-lookup"><span data-stu-id="84590-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="84590-114">XML 스키마 매핑 프로세스의 다음 항목을 만듭니다는 **데이터 집합**:</span><span class="sxs-lookup"><span data-stu-id="84590-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="84590-115">**순서** 와 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="84590-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="84590-116">Unique 제약 조건 합니다 **순서** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="84590-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="84590-117">유의 합니다 **IsPrimaryKey** 속성이 **True**합니다.</span><span class="sxs-lookup"><span data-stu-id="84590-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="84590-118">foreign key 제약 조건 합니다 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="84590-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
- <span data-ttu-id="84590-119">간의 관계는 **순서** 하 고 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="84590-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="84590-120">**중첩** 이 관계에 대 한 속성 **True** 때문에 **순서** 하 고 **OrderDetail** 요소가 스키마에서 중첩 .</span><span class="sxs-lookup"><span data-stu-id="84590-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="84590-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="84590-121">See also</span></span>

- [<span data-ttu-id="84590-122">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="84590-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="84590-123">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="84590-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="84590-124">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="84590-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
