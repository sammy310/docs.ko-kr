---
title: 데이터 집합 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 46a980f06198c6f06bb13824c65cfb5309eec154
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034231"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 집합 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑
스키마 요소에 키 제약 조건을 지정 하거나 수를 사용 하 여 특성을 **키** 요소입니다. KEY 제약 조건이 지정된 요소 또는 특성은 모든 스키마 인스턴스에서 고유한 값을 가져야 하며 null 값을 가져서는 안 됩니다.  
  
 KEY 제약 조건이 정의된 열이 null 값을 가질 수 없다는 것을 제외하면, key 제약 조건은 UNIQUE 제약 조건과 유사합니다.  
  
 다음 표에 간략하게 설명 합니다 **msdata** 에서 지정할 수 있는 특성을 **키** 요소.  
  
|특성 이름|설명|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다. 그렇지 않은 경우는 **이름을** 특성에서 제약 조건 이름의 값을 제공 합니다.|  
|**msdata:PrimaryKey**|하는 경우 `PrimaryKey="true"` 가 있는 경우는 **IsPrimaryKey** 제약 조건 속성이로 설정 되어 **true**, 하므로 기본 키입니다. 합니다 **AllowDBNull** 열 속성이로 설정 된 **false**이므로 기본 키는 null 값을 가질 수 없습니다.|  
  
 key 제약 조건이 지정 되어 있는 스키마를 변환할 때, 매핑 프로세스는 있는 테이블에 unique 제약 조건을 만듭니다는 **AllowDBNull** 로 설정 하는 열 속성 **false** 의 각 열에 대 한 합니다 제약 조건입니다. 합니다 **IsPrimaryKey** unique 제약 조건의 속성도 설정 됩니다 **false** 지정 하지 않으면 `msdata:PrimaryKey="true"` 에 **키** 요소입니다. 이것은 `PrimaryKey="true"`인 스키마의 UNIQUE 제약 조건에도 마찬가지로 적용됩니다.  
  
 다음 스키마 예제에서는 **키** 요소에 키 제약 조건을 지정 합니다 **CustomerID** 요소입니다.  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 **키** 요소를 지정 하는 값을 **CustomerID** 의 자식 요소를 **고객** 요소 고유 값이 있어야 하 고 null 값을 가질 수 없습니다. XSD(XML 스키마 정의 언어) 스키마를 변환할 때 매핑 프로세스에서는 다음 테이블을 만듭니다.  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 XML 스키마 매핑 만들어지기를 **UniqueConstraint** 에 **CustomerID** 열에 다음과 같이 <xref:System.Data.DataSet>합니다. 여기에서는 편의를 위해 관련 속성만 보여 줍니다.  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 에 **데이터 집합** 생성 된를 **IsPrimaryKey** 의 속성을 **UniqueConstraint** 로 설정 되어 **true** 때문에 스키마 지정 `msdata:PrimaryKey="true"` 에 **키** 요소입니다.  
  
 값을 **ConstraintName** 의 속성을 **UniqueConstraint** 에 **데이터 집합** 의 값인는 **msdata:ConstraintName** 에 지정 된 특성을 **키** 스키마의 요소입니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [XSD(XML 스키마)에서 데이터 세트 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
