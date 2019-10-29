---
title: XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: ef77030b4e847f91fea074b68e223ac622539048
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040095"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)
이 단원에서는 XSD(XML 스키마 정의 언어) 스키마 문서에서 `DataSet`의 관계형 스키마를 빌드하는 방법을 간략하게 설명합니다. 일반적으로 스키마 요소의 각 `complexType` 자식 요소에 대해 `DataSet`에서 테이블이 생성 됩니다. 테이블 구조는 복합 형식의 정의에 의해 결정됩니다. 테이블은 스키마의 최상위 요소에 대해 `DataSet`에 생성 됩니다. 그러나 `complexType` 요소가 다른 `complexType` 요소 내에 중첩 되어 있는 경우에만 테이블은 최상위 `complexType` 요소에 대해 만들어지므로,이 경우 중첩 된 `complexType` 요소가 `DataTable` 내의 `DataSet`에 매핑됩니다.  
  
 XSD에 대 한 자세한 내용은 W3C (World Wide Web 컨소시엄) [Xml 스키마 파트 0: 입문 권장 사항](https://www.w3.org/TR/xmlschema-0/), [xml 스키마 파트 1: 구조 권장](https://www.w3.org/TR/xmlschema-1/)사항 및 [Xml 스키마 파트 2: 데이터 형식 권장](https://www.w3.org/TR/xmlschema-2/)사항을 참조 하세요.  
  
 다음 예제에서는 `customers`가 **DataSet** 요소인 `MyDataSet` 요소의 자식 요소인 XML 스키마를 보여 줍니다.  
  
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
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 테이블의 각 열에 대한 데이터 형식은 지정된 해당 요소 또는 특성의 XML 스키마 형식에서 파생됩니다.  
  
> [!NOTE]
> 요소 `customers` **정수**등의 간단한 XML 스키마 데이터 형식인 경우 테이블이 생성 되지 않습니다. 테이블은 복합 형식인 최상위 요소에 대해서만 만들어집니다.  
  
 다음 XML 스키마에서 **schema** 요소에는 두 개의 요소 자식인 `InStateCustomers` 및 `OutOfStateCustomers`있습니다.  
  
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
  
 `InStateCustomers` 및 `OutOfStateCustomers` 자식 요소는 모두 복합 형식 요소(`customerType`)입니다. 따라서 매핑 프로세스는 `DataSet`에 다음과 같은 두 개의 동일한 테이블을 생성 합니다.  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>단원 내용  
 [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 `DataSet`에서 unique 및 foreign key 제약 조건을 만드는 데 사용 되는 XML 스키마 요소에 대해 설명 합니다.  
  
 [XSD(XML 스키마)에서 데이터 세트 관계 생성](generating-dataset-relations-from-xml-schema-xsd.md)  
 `DataSet`에서 테이블 열 간의 관계를 만드는 데 사용 되는 XML 스키마 요소에 대해 설명 합니다.  
  
 [XML 스키마 제약 조건 및 관계](xml-schema-constraints-and-relationships.md)  
 XML 스키마 요소를 사용 하 여 `DataSet`에서 제약 조건을 만들 때 관계를 암시적으로 만드는 방법을 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)  
 `DataSet`의 관계형 구조와 데이터를 XML 데이터로 로드 하 고 유지 하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참조

- [ADO.NET 개요](../ado-net-overview.md)
