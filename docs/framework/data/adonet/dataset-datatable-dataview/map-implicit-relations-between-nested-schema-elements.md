---
title: 중첩된 스키마 요소 사이에 암시적 관계 매핑
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 076e3ec6e5a00fd294fa3c6d7998cfab3a136240
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182076"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>중첩된 스키마 요소 사이에 암시적 관계 매핑
XSD(XML 스키마 정의 언어) 스키마에는 다른 형식 내부에 중첩된 복합 형식이 포함될 수 있습니다. 이 경우 매핑 프로세스에서는 기본 매핑을 적용하며 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.  
  
-   각 복합 형식(부모 및 자식)에 대해 하나의 테이블을 만듭니다.  
  
-   부모에 unique 제약 조건이 없는 있으면 하나 라는 추가 기본 키 열 테이블 정의 *TableName*_Id 위치 *TableName* 부모 테이블의 이름입니다.  
  
-   기본 키로 추가 열을 식별 하 고 부모 테이블에서 기본 키 제약 조건 (설정 하 여 합니다 **IsPrimaryKey** 속성을 **True**). 제약 조건은 Constraint\#으로 명명되며, 여기서 \#은 1, 2, 3 등을 나타냅니다. 예를 들어, 첫 번째 제약 조건의 기본 이름은 Constraint1입니다.  
  
-   추가 열을 부모 테이블의 기본 키를 참조하는 외래 키로 식별하는 외래 키 제약 조건을 자식 테이블에 만듭니다. 제약 조건 이름은 *ParentTable_ChildTable* 여기서 *ParentTable* 은 부모 테이블의 이름 및 *ChildTable* 자식 테이블의 이름입니다.  
  
-   부모와 자식 테이블 간의 데이터 관계를 만듭니다.  
  
 다음 예제에서는 스키마를 보여 줍니다. 여기서 **OrderDetail** 의 자식 요소인 **순서**합니다.  
  
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
  
 XML 스키마 매핑 프로세스의 다음 항목을 만듭니다는 **데이터 집합**:  
  
-   **순서** 와 **OrderDetail** 테이블입니다.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Unique 제약 조건 합니다 **순서** 테이블입니다. 유의 합니다 **IsPrimaryKey** 속성이 **True**합니다.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   foreign key 제약 조건 합니다 **OrderDetail** 테이블입니다.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   간의 관계는 **순서** 하 고 **OrderDetail** 테이블입니다. **중첩** 이 관계에 대 한 속성 **True** 때문에 **순서** 하 고 **OrderDetail** 요소가 스키마에서 중첩 .  
  
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
  
## <a name="see-also"></a>참고자료

- [XSD(XML 스키마)에서 데이터 세트 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
