---
title: 데이터 집합 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: dcb295aef6d93222e682ef7f720c83963036e795
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229747"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 집합 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
합니다 **keyref** 요소는 문서 내의 요소 간의 연결을 설정할 수 있습니다. 이 링크는 관계형 데이터베이스의 외래 키 관계와 유사합니다. 스키마를 지정 하는 경우는 **keyref** 요소가 요소는 해당 외래 키 제약 조건 테이블의 열에 스키마 매핑 프로세스 중 변환 되는 <xref:System.Data.DataSet>합니다. 기본적으로 **keyref** 도 요소와의 관계를 생성 합니다 **ParentTable**를 **ChildTable**, **ParentColumn**, 및  **ChildColumn** 관계에서 지정 된 속성입니다.  
  
 다음 표에 간략하게 설명 합니다 **msdata** 특성에 지정할 수 있습니다 합니다 **keyref** 요소입니다.  
  
|특성 이름|설명|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|하는 경우 **ConstraintOnly = "true"** 에 지정 합니다 **keyref** 스키마의 요소에는 제약 조건 만들어지지만 관계는 만들어지지 않습니다. 이 특성을 지정 하지 않으면 (또는로 설정 되어 **False**), 제약 조건 및 관계에 생성 됩니다 합니다 **데이터 집합**합니다.|  
|**msdata:ConstraintName**|경우는 **ConstraintName** 특성을 지정 하면 해당 값이 제약 조건의 이름으로 사용 됩니다. 이 고, 그렇지는 **이름** 특성을 **keyref** 스키마의 요소에는 제약 조건 이름을 제공 합니다 **데이터 집합**합니다.|  
|**msdata:UpdateRule**|경우는 **UpdateRule** 특성을 지정 합니다 **keyref** 스키마의 요소를 해당 값에 할당 됩니다는 **UpdateRule** 제약 조건 속성에는  **데이터 집합**합니다. 그렇지 않은 경우는 **UpdateRule** 속성이 **Cascade**합니다.|  
|**msdata:DeleteRule**|경우는 **DeleteRule** 특성을 지정 합니다 **keyref** 스키마의 요소를 해당 값에 할당 됩니다는 **DeleteRule** 제약 조건 속성에는  **데이터 집합**합니다. 그렇지 않은 경우는 **DeleteRule** 속성이 **Cascade**합니다.|  
|**msdata:AcceptRejectRule**|경우는 **AcceptRejectRule** 특성을 지정 합니다 **keyref** 스키마의 요소를 해당 값에 할당 됩니다는 **AcceptRejectRule** 제약 조건 속성에는  **데이터 집합**합니다. 그렇지 않은 경우는 **AcceptRejectRule** 속성이 **None**합니다.|  
  
 지정 하는 스키마를 포함 하는 다음 예제는 **키** 및 **keyref** 간의 관계를 **OrderNumber** 의 자식 요소는 **순서**  요소와 **OrderNo** 자식 요소는 **OrderDetail** 요소입니다.  
  
 예에서는 **OrderNumber** 의 자식 요소를 **OrderDetail** 요소를 가리킵니다를 **OrderNo** 키 자식 요소는 **순서**요소입니다.  
  
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
  
 XML 스키마 정의 언어 (XSD) 스키마 매핑 프로세스 결과 다음과 **데이터 집합** 두 테이블을 사용 하 여:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 또한 합니다 **데이터 집합** 다음 제약 조건을 정의 합니다.  
  
-   Unique 제약 조건 합니다 **순서** 테이블입니다.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   간의 관계는 **순서** 하 고 **OrderDetail** 테이블입니다. **중첩** 속성이 **False** 두 요소가 스키마에서 중첩 되지 때문입니다.  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   foreign key 제약 조건 합니다 **OrderDetail** 테이블입니다.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>참고자료

- [데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [XSD(XML 스키마)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
