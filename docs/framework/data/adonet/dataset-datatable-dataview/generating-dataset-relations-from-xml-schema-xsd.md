---
title: XSD(XML 스키마)에서 데이터 세트 관계 생성
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151132"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>XSD(XML 스키마)에서 데이터 세트 관계 생성
<xref:System.Data.DataSet>에서는 부모-자식 관계를 만들어 둘 이상의 열을 연결시킵니다. XML 스키마 정의 언어(XSD) 스키마 내에서 **데이터 집합** 관계를 나타내는 방법에는 세 가지가 있습니다.  
  
- 중첩된 복합 형식을 지정합니다.  
  
- **msdata:관계** 추가를 사용합니다.  
  
- **msdata:ConstraintOnly** 추가 가 없는 **xs:keyref를** 지정합니다.  
  
## <a name="nested-complex-types"></a>중첩된 복합 형식  
 스키마에서 중첩된 복합 형식의 정의는 요소의 부모-자식 관계를 나타냅니다. 다음 XML 스키마 조각은 **OrderDetail이** **Order** 요소의 자식 요소임을 보여 주며 있습니다.  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 XML 스키마 매핑 프로세스는 스키마에 중첩된 복합 형식에 해당하는 **DataSet의** 테이블을 만듭니다. 또한 생성된 테이블에 대한 상위**-** 자식 열로 사용되는 추가 열을 만듭니다. 이러한 상위**-** 자식 열은 기본 키/외래 키 제약 조건을 지정하는 것과 같지 않은 관계를 지정합니다.  
  
## <a name="msdatarelationship-annotation"></a>msdata:Relationship 주석  
 **msdata:Relationship** 기능을 사용하면 중첩되지 않은 스키마의 요소 간에 부모-자식 관계를 명시적으로 지정할 수 있습니다. 다음 예제에서는 **관계** 요소의 구조를 보여 주며 있습니다.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 **msdata:Relationship** 추가의 특성은 부모-자식 관계에 관련된 요소뿐만 아니라 관계에 관련된 **부모 키** 및 **자식 키** 요소 및 특성을 식별합니다. 매핑 프로세스는 이 정보를 사용하여 **DataSet에서** 테이블을 생성하고 이러한 테이블 간의 기본 키/외래 키 관계를 만듭니다.  
  
 예를 들어 다음 스키마 조각은 **동일한** 수준(중첩되지 않음)에서 Order 및 **OrderDetail** 요소를 지정합니다. 스키마는 **msdata:Relationship** 추가를 지정하여 이러한 두 요소 간의 부모-자식 관계를 지정합니다. 이 경우 **msdata:Relationship** 설명을 사용하여 명시적 관계를 지정해야 합니다.  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 매핑 프로세스는 **관계** 요소를 사용하여 **OrderNumber** 테이블의 **OrderNumber** 열과 **DataSet의** **OrderDetail** 테이블의 **OrderNo** 열 간의 부모-자식 관계를 만듭니다. 매핑 프로세스에서는 관계만 지정합니다. 즉, 관계형 데이터베이스의 기본 키/외래 키 제약 조건처럼 이러한 열의 값에 대해 제약 조건을 자동으로 지정하지는 않습니다.  
  
### <a name="in-this-section"></a>섹션 내용  
 [중첩된 스키마 요소 사이에 암시적 관계 매핑](map-implicit-relations-between-nested-schema-elements.md)  
 XML 스키마에서 중첩된 요소가 발생할 때 **DataSet에서** 암시적으로 생성되는 제약 조건 및 관계를 설명합니다.  
  
 [중첩된 요소에 지정된 관계 매핑](map-relations-specified-for-nested-elements.md)  
 XML 스키마의 중첩 된 요소에 대 한 **DataSet에서** 관계를 명시적으로 설정 하는 방법을 설명 합니다.  
  
 [중첩 없이 요소 사이에 관계 지정](specify-relations-between-elements-with-no-nesting.md)  
 중첩되지 않은 XML 스키마 요소 간의 **DataSet에서** 관계를 만드는 방법에 대해 설명합니다.  
  
### <a name="related-sections"></a>관련 섹션  
 [XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 XML 스키마 정의 언어(XSD) 스키마에서 만든 **DataSet의** 관계형 구조 또는 스키마에 대해 설명합니다.  
  
 [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 **DataSet에서**고유 및 외래 키 제약 조건을 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목

- [ADO.NET 개요](../ado-net-overview.md)
