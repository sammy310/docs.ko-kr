---
title: 중첩된 스키마 요소 사이에 암시적 관계 매핑
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150965"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>중첩된 스키마 요소 사이에 암시적 관계 매핑
XSD(XML 스키마 정의 언어) 스키마에는 다른 형식 내부에 중첩된 복합 형식이 포함될 수 있습니다. 이 경우 매핑 프로세스에서는 기본 매핑을 적용하며 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.  
  
- 각 복합 형식(부모 및 자식)에 대해 하나의 테이블을 만듭니다.  
  
- 상위 에 고유한 제약 조건이 없는 경우 *TableName이*상위 테이블의 이름인 TableName _Id 테이블 정의당 하나의 추가 기본 키 *열입니다.*  
  
- 추가 열을 기본 키로 식별하는 상위 테이블의 기본 키 제약 **조건입니다(IsPrimaryKey** 속성을 **True로**설정). 제약 조건은 Constraint\#으로 명명되며, 여기서 \#은 1, 2, 3 등을 나타냅니다. 예를 들어, 첫 번째 제약 조건의 기본 이름은 Constraint1입니다.  
  
- 추가 열을 부모 테이블의 기본 키를 참조하는 외래 키로 식별하는 외래 키 제약 조건을 자식 테이블에 만듭니다. 제약 조건은 *ParentTable이* 부모 테이블의 이름이며 *ChildTable이* 하위 테이블의 이름인 *ParentTable_ChildTable* 명명됩니다.  
  
- 부모와 자식 테이블 간의 데이터 관계를 만듭니다.  
  
 다음 예제에서는 **OrderDetail이** **Order의**자식 요소인 스키마를 보여 주며 있습니다.  
  
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
  
 XML 스키마 매핑 프로세스는 데이터 **집합에서**다음을 만듭니다.  
  
- **주문** 및 **OrderDetail** 테이블입니다.  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- **Order** 테이블의 고유한 제약 조건입니다. **IsPrimaryKey** 속성은 **True로**설정됩니다.  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- **OrderDetail** 테이블의 외래 키 제약 조건입니다.  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- **주문** 및 **OrderDetail** 테이블 간의 관계입니다. **순서** 및 **OrderDetail** 요소가 스키마에 중첩되기 때문에 이 관계에 대한 **중첩** 속성은 **True로** 설정됩니다.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a>참고 항목

- [XSD(XML 스키마)에서 데이터 세트 관계 생성](generating-dataset-relations-from-xml-schema-xsd.md)
- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET 개요](../ado-net-overview.md)
