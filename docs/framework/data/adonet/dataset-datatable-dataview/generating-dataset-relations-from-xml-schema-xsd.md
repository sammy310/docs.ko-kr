---
title: XSD(XML 스키마)에서 데이터 집합 관계 생성
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 29c0e9ee96c376c6da392692febccbbae3c6a33f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170224"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>XSD(XML 스키마)에서 데이터 집합 관계 생성
<xref:System.Data.DataSet>에서는 부모-자식 관계를 만들어 둘 이상의 열을 연결시킵니다. 나타내는 세 가지는 **데이터 집합** XML 스키마 정의 언어 (XSD) 스키마 내의 관계:  
  
-   중첩된 복합 형식을 지정합니다.  
  
-   사용 된 **msdata: relationship** 주석입니다.  
  
-   지정는 **xs: keyref** 없이 **사용** 주석입니다.  
  
## <a name="nested-complex-types"></a>중첩된 복합 형식  
 스키마에서 중첩된 복합 형식의 정의는 요소의 부모-자식 관계를 나타냅니다. 다음 XML 스키마 조각에 따르면 **OrderDetail** 의 자식 요소를 **순서** 요소입니다.  
  
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
  
 XML 스키마 매핑 프로세스에 테이블을 만듭니다는 **데이터 집합** 스키마에서 중첩된 된 복합 형식에 해당 하는 합니다. 또한 부모로 사용 되는 추가 열을 만듭니다**-** 생성된 된 테이블에 대 한 자식 열입니다. 이러한 부모 보면**-** 자식 열에서는 없는 기본 키/외래 키 제약 조건을 지정 하는 것과 관계를 지정 합니다.  
  
## <a name="msdatarelationship-annotation"></a>msdata:Relationship 주석  
 합니다 **msdata: relationship** 주석을 사용 하면 명시적으로 중첩 되지 않은 스키마의 요소 간의 부모-자식 관계를 지정할 수 있습니다. 다음 예제에서는의 구조를 표시 합니다 **관계** 요소.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 특성을 **msdata: relationship** 주석으로도 부모-자식 관계에 관련 된 요소를 식별 합니다 **parentkey** 및 **childkey** 요소 및 특성 관계를 맺고 있습니다. 테이블을 생성 하려면이 정보를 사용 하는 매핑 프로세스를 **데이터 집합** 고 이러한 테이블 간에 기본 키/외래 키 관계를 만들 수 있습니다.  
  
 예를 들어 다음 스키마 조각 지정 **순서** 하 고 **OrderDetail** 동일한 수준에서 요소 (중첩 되지 않음). 스키마 지정는 **msdata: relationship** 주석에 이러한 두 요소 간의 부모-자식 관계를 지정 합니다. 이 경우 관계를 명시적으로 지정 해야 합니다 **msdata: relationship** 주석입니다.  
  
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
  
 매핑 프로세스를 사용 하는 **관계** 요소 간의 부모-자식 관계를 만들려면를 **OrderNumber** 열에는 **순서** 테이블과 합니다 **OrderNo** 열에는 **OrderDetail** 테이블에 **데이터 집합**합니다. 매핑 프로세스에서는 관계만 지정합니다. 즉, 관계형 데이터베이스의 기본 키/외래 키 제약 조건처럼 이러한 열의 값에 대해 제약 조건을 자동으로 지정하지는 않습니다.  
  
### <a name="in-this-section"></a>섹션 내용  
 [중첩된 스키마 요소 사이에 암시적 관계 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 제약 조건 및에서 암시적으로 만든 관계에 설명 합니다는 **데이터 집합** XML 스키마에서 중첩 된 요소가 발생 한 경우.  
  
 [중첩된 요소에 지정된 관계 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 관계를 명시적으로 설정 하는 방법에 설명 된 **데이터 집합** XML 스키마의 중첩 된 요소에 대 한 합니다.  
  
 [중첩 없이 요소 사이에 관계 지정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 관계를 만드는 방법을 설명 합니다는 **데이터 집합** 중첩 되지 않은 XML 스키마 요소 사이입니다.  
  
### <a name="related-sections"></a>관련 단원  
 [XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 관계형 구조 또는 스키마를 설명 합니다는 **데이터 집합** XML 스키마 정의 언어 (XSD)에서 만들어집니다.  
  
 [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 고유 및 외래 키 제약 조건을 만드는 데 필요한 XML 스키마 요소에 설명 합니다는 **데이터 집합**합니다.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
