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
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="46db0-102">중첩된 요소에 지정된 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="46db0-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="46db0-103">스키마에는 **msdata:Relationship** 어구가 포함되어 스키마의 두 요소 간의 매핑을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="46db0-104">**msdata:Relationship에** 지정된 두 요소는 스키마에 중첩될 수 있지만 할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="46db0-105">매핑 프로세스는 스키마에서 **msdata:Relationship를** 사용하여 두 열 간의 기본 키/외래 키 관계를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="46db0-106">다음 예제에서는 **OrderDetail** 요소가 **Order의**자식 요소인 XML 스키마를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="46db0-107">**msdata:Relationship는** 이 부모-자식 관계를 식별하고 결과 **주문** 테이블의 **OrderNumber** 열이 결과 **OrderDetail** 테이블의 **OrderNo** 열과 관련되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="46db0-108">XML 스키마 매핑 프로세스에서는 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="46db0-109">**주문** 및 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="46db0-110">**주문** 및 **OrderDetail** 테이블 간의 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="46db0-111">**순서** 및 **OrderDetail** 요소가 스키마에 중첩되기 때문에 이 관계에 대한 **중첩** 속성은 **True로** 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="46db0-112">매핑 프로세스에서는 어떠한 제약 조건도 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46db0-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46db0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46db0-113">See also</span></span>

- [<span data-ttu-id="46db0-114">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="46db0-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="46db0-115">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="46db0-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="46db0-116">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="46db0-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
