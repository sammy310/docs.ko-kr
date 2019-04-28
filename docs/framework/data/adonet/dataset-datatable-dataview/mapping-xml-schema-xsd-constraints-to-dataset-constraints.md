---
title: 데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: a1690e99aeaeb7ed9c85fd28697ae22d34bb2018
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607901"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="077f3-102">데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="077f3-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="077f3-103">XSD(XML 스키마 정의 언어)를 사용하여 요소와 특성에서 제약 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="077f3-104">관계형 스키마에 XML 스키마를 매핑하는 경우는 <xref:System.Data.DataSet>, XML 스키마 제약 조건을 테이블 및 열 내에서 적절 한 관계형 제약 조건에 매핑되는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="077f3-105">이 단원에서는 다음 XML 스키마 제약 조건의 매핑에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
- <span data-ttu-id="077f3-106">고유성 제약 조건을 사용 하 여 지정 된 **고유** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
- <span data-ttu-id="077f3-107">키 제약 조건을 사용 하 여 지정 된 **키** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-107">The key constraint specified using the **key** element.</span></span>  
  
- <span data-ttu-id="077f3-108">Keyref 제약 조건을 사용 하 여 지정 된 **keyref** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="077f3-109">요소나 특성에서 제약 조건을 사용하여 문서의 모든 인스턴스에서 요소의 값에 특정 제한 사항을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="077f3-110">에 key 제약 조건이 예를 들어,를 **CustomerID** 의 자식 요소를 **고객** 스키마 요소에에서 나타내는 값을 **CustomerID** 자식 요소 여야 합니다 모든 문서 인스턴스에서 고유 null 값이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="077f3-111">또한 문서 내에서 관계를 설정하도록 문서의 요소와 특성 사이에 제약 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="077f3-112">KEY 및 KEYREF 제약 조건은 스키마에서 사용되어 문서 내에서의 제약 조건을 지정함으로써 결과적으로 문서 요소와 특성 간의 관계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="077f3-113">매핑 프로세스 내에서 만든 테이블에 적절 한 제약 조건으로 이러한 스키마 제약 조건을 변환 합니다 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="077f3-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="077f3-114">In This Section</span></span>  
 [<span data-ttu-id="077f3-115">데이터 세트 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="077f3-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="077f3-116">unique 제약 조건을 만드는 데 사용 하는 XML 스키마 요소에 설명 합니다는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="077f3-117">데이터 세트 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="077f3-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="077f3-118">키 제약 조건 (고유 제약 조건 null 값이 허용 되지 않습니다)를 만드는 데 사용 하는 XML 스키마 요소에 설명 된 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="077f3-119">데이터 세트 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="077f3-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="077f3-120">Keyref (외래 키) 제약 조건을 만드는 데 사용 하는 XML 스키마 요소에 설명 합니다는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="077f3-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="077f3-121">Related Sections</span></span>  
 [<span data-ttu-id="077f3-122">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="077f3-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="077f3-123">관계형 구조 또는 스키마를 설명 합니다는 **데이터 집합** XSD 스키마에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="077f3-124">XSD(XML 스키마)에서 데이터 세트 관계 생성</span><span class="sxs-lookup"><span data-stu-id="077f3-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="077f3-125">테이블 열 간의 관계를 만드는 데 사용 하는 XML 스키마 요소에 설명 합니다는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="077f3-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077f3-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="077f3-126">See also</span></span>

- [<span data-ttu-id="077f3-127">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="077f3-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
