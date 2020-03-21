---
title: 중첩된 요소에 지정된 관계 매핑
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cd652f51f01dcfa16a8b707f35c658043c20670d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150898"
---
# <a name="map-relations-specified-for-nested-elements"></a>중첩된 요소에 지정된 관계 매핑
스키마에는 **msdata:Relationship** 어구가 포함되어 스키마의 두 요소 간의 매핑을 명시적으로 지정할 수 있습니다. **msdata:Relationship에** 지정된 두 요소는 스키마에 중첩될 수 있지만 할 필요는 없습니다. 매핑 프로세스는 스키마에서 **msdata:Relationship를** 사용하여 두 열 간의 기본 키/외래 키 관계를 생성합니다.  
  
 다음 예제에서는 **OrderDetail** 요소가 **Order의**자식 요소인 XML 스키마를 보여 주며 있습니다. **msdata:Relationship는** 이 부모-자식 관계를 식별하고 결과 **주문** 테이블의 **OrderNumber** 열이 결과 **OrderDetail** 테이블의 **OrderNo** 열과 관련되도록 지정합니다.  
  
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
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"
                                msdata:parent="Order"
                                msdata:child="OrderDetail"
                                msdata:parentkey="OrderNumber"
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 XML 스키마 매핑 프로세스에서는 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.  
  
- **주문** 및 **OrderDetail** 테이블입니다.  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- **주문** 및 **OrderDetail** 테이블 간의 관계입니다. **순서** 및 **OrderDetail** 요소가 스키마에 중첩되기 때문에 이 관계에 대한 **중첩** 속성은 **True로** 설정됩니다.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 매핑 프로세스에서는 어떠한 제약 조건도 만들지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [XSD(XML 스키마)에서 데이터 세트 관계 생성](generating-dataset-relations-from-xml-schema-xsd.md)
- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET 개요](../ado-net-overview.md)
