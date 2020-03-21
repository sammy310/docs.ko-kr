---
title: 데이터 세트 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150885"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 세트 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
**keyref** 요소를 사용하면 문서 내의 요소 간에 링크를 설정할 수 있습니다. 이 링크는 관계형 데이터베이스의 외래 키 관계와 유사합니다. 스키마가 **keyref** 요소를 지정하면 스키마 매핑 프로세스 중에 요소가 <xref:System.Data.DataSet>의 테이블의 열에 해당하는 외래 키 제약 조건으로 변환됩니다. 기본적으로 **키레프** 요소는 **부모 테이블,** 하위 **테이블, 부모열**및 **ParentColumn**관계에 지정된 **자식열** 속성을 사용하는 관계도 생성합니다.  
  
 다음 표에서는 **keyref** 요소에서 지정할 수 있는 **msdata** 특성을 간략하게 설명합니다.  
  
|특성 이름|Description|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|**ConstraintOnly="true"가** 스키마의 **키레프** 요소에 지정되면 제약 조건이 만들어지지만 관계가 만들어지지 않습니다. 이 특성이 지정되지 않았거나 **False로**설정된 경우 제약 조건과 관계가 **DataSet**에서 만들어집니다.|  
|**msdata:ConstraintName**|**ConstraintName** 특성을 지정하면 해당 값이 제약 조건의 이름으로 사용됩니다. 그렇지 않으면 스키마의 **keyref** 요소의 **이름** 특성은 **DataSet**에서 제약 조건 이름을 제공합니다.|  
|**msdata:UpdateRule**|**UpdateRule** 특성이 스키마의 **keyref** 요소에 지정되면 해당 값은 **DataSet**의 **UpdateRule** 제약 조건 속성에 할당됩니다. 그렇지 않으면 **UpdateRule** 속성이 **계단식으로**설정됩니다.|  
|**msdata:DeleteRule**|**DeleteRule** 특성이 스키마의 **keyref** 요소에 지정되면 해당 값은 **DataSet의** **DeleteRule** 제약 조건 속성에 할당됩니다. 그렇지 않으면 **DeleteRule** 속성이 **계단식으로**설정됩니다.|  
|**msdata:AcceptRejectRule**|**AcceptRejectRule** 특성이 스키마의 **키레프** 요소에 지정되면 해당 값은 **DataSet의** **AcceptRejectRule** 제약 조건 속성에 할당됩니다. 그렇지 않으면 **AcceptRejectRule** 속성이 **없음으로**설정됩니다.|  
  
 다음 예제에는 **OrderNumber** 하위 요소의 **OrderNumber** 자식 요소와 **OrderDetail** 요소의 **OrderNo** 자식 요소 간의 **키** 및 **키 참조** 관계를 지정하는 스키마가 포함되어 있습니다.  
  
 예제에서 **OrderNumber** **OrderDetail** 요소의 자식 요소는 **OrderNo 순서** 요소의 **OrderNo** 키 자식 요소를 참조합니다.  
  
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
  
 XML 스키마 정의 언어(XSD) 스키마 매핑 프로세스는 두 개의 테이블이 있는 다음 **DataSet을** 생성합니다.  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 또한 **DataSet은** 다음 제약 조건을 정의합니다.  
  
- **Order** 테이블의 고유한 제약 조건입니다.  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- **주문** 및 **OrderDetail** 테이블 간의 관계입니다. 두 요소가 스키마에 중첩되지 않으므로 **중첩된** 속성은 **False로** 설정됩니다.  
  
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
  
- **OrderDetail** 테이블의 외래 키 제약 조건입니다.  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a>참고 항목

- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [XSD(XML 스키마)에서 데이터 세트 관계 생성](generating-dataset-relations-from-xml-schema-xsd.md)
- [ADO.NET 개요](../ado-net-overview.md)
