---
title: XML 스키마 제약 조건 및 관계
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150716"
---
# <a name="xml-schema-constraints-and-relationships"></a>XML 스키마 제약 조건 및 관계
XML 스키마 정의 언어(XSD) 스키마에서 제약 조건(고유, 키 및 키레프 제약 조건)과 **관계(msdata:Relationship** 추가)를 지정할 수 있습니다. 이 항목에서는 XML 스키마에 지정된 제약 조건과 관계를 해석하여 <xref:System.Data.DataSet>을 생성하는 방법을 설명합니다.  
  
 일반적으로 XML 스키마에서 **dataSet에서**관계만 생성하려는 경우 **msdata:Relationship** 어노팅을 지정합니다. 자세한 내용은 [XML 스키마(XSD)에서 데이터 집합 관계 생성을](generating-dataset-relations-from-xml-schema-xsd.md)참조하십시오. **DataSet**에서 구속조건을 생성하려는 경우 구속조건(고유, 키 및 키 참조)을 지정합니다. 이 항목의 뒷부분에서 설명하겠지만 KEY 및 KEYREF 제약 조건도 관계를 생성하는 데 사용됩니다.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>KEY 및 KEYREF 제약 조건에서 관계 생성  
 **msdata:Relationship** 추가를 지정하는 대신 XML 스키마 매핑 프로세스 중에 사용되는 키 및 키참조 제약 조건을 지정하여 제약 조건뿐만 아니라 **DataSet의**관계도 생성할 수 있습니다. 그러나 `msdata:ConstraintOnly="true"` **keyref** 요소에 지정하는 경우 **DataSet에는** 제약 조건만 포함되며 관계가 포함되지 않습니다.  
  
 다음 예제에서는 중첩되지 않은 **주문** 및 **OrderDetail** 요소를 포함하는 XML 스키마를 보여 주어집니다. 스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.  
  
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
  
 XML 스키마 매핑 프로세스 중에 생성되는 **DataSet에는** **주문** 및 **OrderDetail** 테이블이 포함됩니다. 또한 **DataSet에는** 관계 및 제약 조건이 포함됩니다. 다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다. 스키마는 **msdata:관계** 추가를 지정하지 않습니다. 대신 키 및 키레프 제약 조건이 관계를 생성하는 데 사용됩니다.  
  
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
  
 이전 스키마 예제에서는 **Order** 및 **OrderDetail** 요소가 중첩되지 않습니다. 다음 스키마 예제에서는 이들 요소가 중첩됩니다. 그러나 **msdata:관계** 추가는 지정되지 않습니다. 따라서 암시적 관계가 가정됩니다. 자세한 내용은 [중첩 스키마 요소 간의 암시적 관계 맵을](map-implicit-relations-between-nested-schema-elements.md)참조하십시오. 스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.  
  
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
  
 XML 스키마 매핑 프로세스에서 생성된 **DataSet에는** 다음 두 개의 테이블이 포함됩니다.  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 **DataSet에는** 두 **관계(msdata:관계** 별추가를 기반으로 한 관계 및 키 및 키레프 제약 조건에 기반한 관계)와 다양한 제약 조건도 포함됩니다. 다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.  
  
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
  
 중첩된 테이블을 참조하는 키리프 제약 조건에 **msdata:IsNested="true"** 별표가 포함된 경우 **DataSet은** 키레프 제약 조건 및 관련 고유/키 제약 조건을 기반으로 하는 단일 중첩 관계를 만듭니다.  
  
## <a name="see-also"></a>참고 항목

- [XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [ADO.NET 개요](../ado-net-overview.md)
