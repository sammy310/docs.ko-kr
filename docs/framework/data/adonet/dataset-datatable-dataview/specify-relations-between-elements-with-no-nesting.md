---
title: 중첩 없이 요소 사이에 관계 지정
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 4b7b216e58f36302db29c4b4b5176339521b0f17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607919"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a>중첩 없이 요소 사이에 관계 지정
요소가 중첩되지 않은 경우에는 암시적 관계가 만들어지지 않습니다. 하지만 사용 하 여 중첩 되지 않은 요소 간의 관계를 명시적으로 지정 있습니다 합니다 **msdata: relationship** 주석입니다.  
  
 다음 예제는 XML 스키마를 보여 줍니다.는 **msdata: relationship** 사이 주석이 지정 됩니다는 **순서** 하 고 **OrderDetail** 되지 않는 요소 중첩 합니다. **msdata: relationship** 주석이의 자식 요소로 지정 합니다 **스키마** 요소입니다.  
  
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
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 XML 스키마 정의 언어 (XSD) 스키마 매핑 프로세스에서는 만듭니다는 <xref:System.Data.DataSet> 사용 하 여 **순서** 하 고 **OrderDetail** 테이블과 아래와 같이 이러한 두 테이블 간에 지정 된 관계는 합니다.  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a>참고자료

- [XSD(XML 스키마)에서 데이터 세트 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
