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
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="35dc1-102">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="35dc1-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="35dc1-103">이 단원에서는 XSD(XML 스키마 정의 언어) 스키마 문서에서 `DataSet`의 관계형 스키마를 빌드하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="35dc1-104">일반적으로 스키마 요소의 각 `complexType` 자식 요소에 대해 `DataSet`에서 테이블이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="35dc1-105">테이블 구조는 복합 형식의 정의에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="35dc1-106">테이블은 스키마의 최상위 요소에 대해 `DataSet`에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="35dc1-107">그러나 `complexType` 요소가 다른 `complexType` 요소 내에 중첩 되어 있는 경우에만 테이블은 최상위 `complexType` 요소에 대해 만들어지므로,이 경우 중첩 된 `complexType` 요소가 `DataTable` 내의 `DataSet`에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="35dc1-108">XSD에 대 한 자세한 내용은 W3C (World Wide Web 컨소시엄) [Xml 스키마 파트 0: 입문 권장 사항](https://www.w3.org/TR/xmlschema-0/), [xml 스키마 파트 1: 구조 권장](https://www.w3.org/TR/xmlschema-1/)사항 및 [Xml 스키마 파트 2: 데이터 형식 권장](https://www.w3.org/TR/xmlschema-2/)사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35dc1-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="35dc1-109">다음 예제에서는 `customers`가 **DataSet** 요소인 `MyDataSet` 요소의 자식 요소인 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="35dc1-110">앞의 예제에서 `customers` 요소는 복합 형식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="35dc1-111">따라서 복합 형식 정의가 구문 분석되고 매핑 프로세스에서는 다음 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="35dc1-112">테이블의 각 열에 대한 데이터 형식은 지정된 해당 요소 또는 특성의 XML 스키마 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35dc1-113">요소 `customers` **정수**등의 간단한 XML 스키마 데이터 형식인 경우 테이블이 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="35dc1-114">테이블은 복합 형식인 최상위 요소에 대해서만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="35dc1-115">다음 XML 스키마에서 **schema** 요소에는 두 개의 요소 자식인 `InStateCustomers` 및 `OutOfStateCustomers`있습니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="35dc1-116">`InStateCustomers` 및 `OutOfStateCustomers` 자식 요소는 모두 복합 형식 요소(`customerType`)입니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="35dc1-117">따라서 매핑 프로세스는 `DataSet`에 다음과 같은 두 개의 동일한 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="35dc1-118">단원 내용</span><span class="sxs-lookup"><span data-stu-id="35dc1-118">In This Section</span></span>  
 [<span data-ttu-id="35dc1-119">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="35dc1-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="35dc1-120">`DataSet`에서 unique 및 foreign key 제약 조건을 만드는 데 사용 되는 XML 스키마 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="35dc1-121">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="35dc1-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="35dc1-122">`DataSet`에서 테이블 열 간의 관계를 만드는 데 사용 되는 XML 스키마 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="35dc1-123">XML 스키마 제약 조건 및 관계</span><span class="sxs-lookup"><span data-stu-id="35dc1-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="35dc1-124">XML 스키마 요소를 사용 하 여 `DataSet`에서 제약 조건을 만들 때 관계를 암시적으로 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="35dc1-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="35dc1-125">Related Sections</span></span>  
 [<span data-ttu-id="35dc1-126">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="35dc1-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="35dc1-127">`DataSet`의 관계형 구조와 데이터를 XML 데이터로 로드 하 고 유지 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35dc1-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35dc1-128">참조</span><span class="sxs-lookup"><span data-stu-id="35dc1-128">See also</span></span>

- [<span data-ttu-id="35dc1-129">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="35dc1-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
