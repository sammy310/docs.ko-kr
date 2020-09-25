---
title: 중첩된 요소에 지정된 관계 매핑
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: f758e1ef2c3786a102dc6bb5f6dd217b20dc5b55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198550"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="f3701-102">중첩된 요소에 지정된 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="f3701-102">Map Relations Specified for Nested Elements</span></span>

<span data-ttu-id="f3701-103">스키마는 **msdata: Relationship** 주석을 포함 하 여 스키마의 두 요소 간 매핑을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="f3701-104">**Msdata: Relationship** 에 지정 된 두 요소는 스키마에 중첩 될 수 있지만 반드시 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="f3701-105">매핑 프로세스에서는 스키마의 **msdata: relationship** 을 사용 하 여 두 열 간의 기본 키/외래 키 관계를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="f3701-106">다음 예에서는 **Orderdetail** 요소가 **Order**의 자식 요소인 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="f3701-107">**Msdata: Relationship** 은이 부모-자식 관계를 식별 하 고 결과 **Order** 테이블의 **Ordernumber** 열이 결과 **ordernumber** 테이블의 **ordernumber** 열과 관련 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="f3701-108">XML 스키마 매핑 프로세스에서는 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="f3701-109">**Order** 및 **orderdetail** 테이블</span><span class="sxs-lookup"><span data-stu-id="f3701-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="f3701-110">**Order** 및 **orderdetail** 테이블 간의 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="f3701-111">**Order** 및 **orderdetail** 요소가 스키마에 중첩 되어 있으므로이 관계의 **Nested** 속성은 **True** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="f3701-112">매핑 프로세스에서는 어떠한 제약 조건도 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3701-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3701-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3701-113">See also</span></span>

- [<span data-ttu-id="f3701-114">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="f3701-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="f3701-115">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="f3701-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="f3701-116">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f3701-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
