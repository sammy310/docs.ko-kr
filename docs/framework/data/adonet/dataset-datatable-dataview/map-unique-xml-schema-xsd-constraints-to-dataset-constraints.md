---
title: 데이터 세트 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150846"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 세트 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑
XML 스키마 정의 언어(XSD) 스키마에서 **고유** 요소는 요소 또는 특성에 대한 고유 성 제약 조건을 지정합니다. XML 스키마를 관계형 스키마로 변환하는 과정에서, XML 스키마의 요소나 특성에 지정된 UNIQUE 제약 조건은 생성된 해당 <xref:System.Data.DataTable>에 있는 <xref:System.Data.DataSet>의 UNIQUE 제약 조건에 매핑됩니다.  
  
 다음 표에서는 **고유한** 요소에서 지정할 수 있는 **msdata** 특성을 간략하게 설명합니다.  
  
|특성 이름|Description|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다. 그렇지 않으면 **name** 특성은 제약 조건 이름의 값을 제공합니다.|  
|**msdata:PrimaryKey**|고유 `PrimaryKey="true"` 요소에 있는 **unique** 경우 **IsPrimaryKey** 속성을 **true로**설정한 고유한 제약 조건이 만들어집니다.|  
  
 다음 예제에서는 **고유** 요소를 사용하여 고유 제약 조건을 지정하는 XML 스키마를 보여 주습니다.  
  
```xml  
<xs:schema id="SampleDataSet"
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 스키마의 **고유한** 요소는 문서 인스턴스의 모든 **Customer** 요소에 대해 **CustomerID** 자식 요소의 값이 고유해야 함을 지정합니다. **DataSet을**빌드할 때 매핑 프로세스는 이 스키마를 읽고 다음 테이블을 생성합니다.  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 매핑 프로세스는 다음 **DataSet**에 표시된 대로 **CustomerID** 열에 고유한 제약 조건을 만듭니다. 여기에서는 편의를 위해 관련 속성만 보여 줍니다.  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 생성된 **DataSet에서** **IsPrimaryKey** 속성은 고유한 제약 조건에 대해 **False로** 설정됩니다. 열의 **고유** 속성은 **CustomerID** 열 값이 고유해야 함을 나타냅니다(열의 **AllowDBNull** 속성에 의해 지정된 대로 null 참조일 수 있음).  
  
 스키마를 수정하고 선택적 **msdata:PrimaryKey** 특성 값을 **True로**설정하면 고유한 제약 조건이 테이블에 만들어집니다. **AllowDBNull** 열 속성은 **false로**설정되고 제약 조건의 **IsPrimaryKey** 속성은 **True로**설정되므로 **CustomerID** 열을 기본 키 열로 만듭니다.  
  
 XML 스키마의 요소나 특성의 조합에 UNIQUE 제약 조건을 지정할 수 있습니다. 다음 예제에서는 스키마에 다른 **xs:field** 요소를 추가하여 모든 인스턴스의 **모든 고객에** 대해 **CustomerID** 및 **CompanyName** 값의 조합이 고유해야 함을 지정하는 방법을 보여 줍니다.  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 결과 **DataSet에서**생성되는 제약 조건입니다.  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>참고 항목

- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [XSD(XML 스키마)에서 데이터 세트 관계 생성](generating-dataset-relations-from-xml-schema-xsd.md)
- [ADO.NET 개요](../ado-net-overview.md)
