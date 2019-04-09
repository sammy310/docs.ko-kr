---
title: XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 549579fca0179994191987097c12b6085ee91756
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119693"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)
이 단원에서는 XSD(XML 스키마 정의 언어) 스키마 문서에서 `DataSet`의 관계형 스키마를 빌드하는 방법을 간략하게 설명합니다. 일반적으로 각각에 대해 `complexType` 스키마 요소의 자식 요소 테이블에서 생성 되는 `DataSet`합니다. 테이블 구조는 복합 형식의 정의에 의해 결정됩니다. 만들어진 테이블은 `DataSet` 스키마의 최상위 요소에 대 한 합니다. 그러나 테이블에만 만들어집니다 최상위 수준에 대 한 `complexType` 요소 때를 `complexType` 요소는 다른 내부에 중첩 `complexType` 는 요소인 경우 중첩 된 `complexType` 요소에 매핑되는 `DataTable` 내는 `DataSet`합니다.  
  
 XSD에 대 한 자세한 내용은 World Wide Web Consortium (W3C)을 참조 하세요. [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), 및 [XML Schema Part 2: 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/)합니다.  
  
 다음 예제에서는 XML 스키마를 보여 줍니다. 여기서 `customers` 의 자식 요소를 `MyDataSet` 요소의 **데이터 집합** 요소입니다.  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 앞의 예제에서 `customers` 요소는 복합 형식 요소입니다. 따라서 복합 형식 정의가 구문 분석되고 매핑 프로세스에서는 다음 테이블을 만듭니다.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 테이블의 각 열에 대한 데이터 형식은 지정된 해당 요소 또는 특성의 XML 스키마 형식에서 파생됩니다.  
  
> [!NOTE]
>  경우 요소 `customers` 와 같은 간단한 XML 스키마 데이터 형식입니다 **정수**, 테이블이 생성 됩니다. 테이블은 복합 형식인 최상위 요소에 대해서만 만들어집니다.  
  
 다음 XML 스키마에는 **스키마** 요소에 두 명의 요소 자식이 `InStateCustomers` 및 `OutOfStateCustomers`합니다.  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 `InStateCustomers` 및 `OutOfStateCustomers` 자식 요소는 모두 복합 형식 요소(`customerType`)입니다. 따라서 매핑 프로세스의 다음 두 개의 동일한 테이블을 생성 합니다 `DataSet`합니다.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>섹션 내용  
 [데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 고유 및 외래 키 제약 조건을 만드는 데 필요한 XML 스키마 요소에 설명 된 `DataSet`합니다.  
  
 [XSD(XML 스키마)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 테이블 열 간의 관계를 만드는 데 XML 스키마 요소에 설명 된 `DataSet`합니다.  
  
 [XML 스키마 제약 조건 및 관계](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 관계가 만들어지는 방법을 암시적으로 XML 스키마 요소에 대 한 제약 조건을 만드는 데 사용 하는 경우에 대해 설명 된 `DataSet`합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 로드 하 고 관계형 구조와 데이터를 유지 하는 방법을 설명는 `DataSet` XML 데이터로 합니다.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
