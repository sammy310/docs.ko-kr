---
title: 중첩 없이 요소 사이에 관계 지정
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: bee427c6cdf76792773ea827c8772b276ff29c31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150820"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="c3d07-102">중첩 없이 요소 사이에 관계 지정</span><span class="sxs-lookup"><span data-stu-id="c3d07-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="c3d07-103">요소가 중첩되지 않은 경우에는 암시적 관계가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d07-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="c3d07-104">그러나 **msdata:Relationship** 추가를 사용하여 중첩되지 않은 요소 간의 관계를 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d07-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="c3d07-105">다음 예제에서는 **msdata:관계** 부호가 **중첩되지** 않은 Order 및 **OrderDetail** 요소 사이에 지정된 XML 스키마를 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="c3d07-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="c3d07-106">**msdata:관계** 추가는 **스키마** 요소의 자식 요소로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3d07-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="c3d07-107">XML 스키마 정의 언어(XSD) 스키마 매핑 <xref:System.Data.DataSet> 프로세스는 **아래와** 같이 Order 및 **OrderDetail** 테이블과 이 두 테이블 사이에 지정된 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3d07-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3d07-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3d07-108">See also</span></span>

- [<span data-ttu-id="c3d07-109">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="c3d07-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="c3d07-110">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="c3d07-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="c3d07-111">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c3d07-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
