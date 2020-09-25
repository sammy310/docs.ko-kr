---
title: 유추 제한
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 9d8191be137661200e1a6b84d68328c1202880ca
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172777"
---
# <a name="inference-limitations"></a><span data-ttu-id="11b3d-102">유추 제한</span><span class="sxs-lookup"><span data-stu-id="11b3d-102">Inference Limitations</span></span>

<span data-ttu-id="11b3d-103">XML에서 <xref:System.Data.DataSet> 스키마를 유추하는 과정을 통해 만들어지는 스키마는 각 문서의 XML 요소에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11b3d-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="11b3d-104">예를 들어, 다음과 같은 XML 문서를 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="11b3d-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="11b3d-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="11b3d-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="11b3d-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="11b3d-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="11b3d-107">"문서 1"의 경우 "Element1"가 반복 되는 요소 이므로 유추 프로세스에서 "DocumentElement" 라는 **데이터 집합과** "Element1" 라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11b3d-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="11b3d-108">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="11b3d-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="11b3d-109">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="11b3d-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="11b3d-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="11b3d-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="11b3d-111">Text1</span><span class="sxs-lookup"><span data-stu-id="11b3d-111">Text1</span></span>|  
|<span data-ttu-id="11b3d-112">Text2</span><span class="sxs-lookup"><span data-stu-id="11b3d-112">Text2</span></span>|  
  
 <span data-ttu-id="11b3d-113">그러나 "Document2"의 경우 유추 프로세스는 "NewDataSet" 이라는 **데이터 집합과** "documentelement" 라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11b3d-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="11b3d-114">"Element1"은 특성이나 자식 요소가 없으므로 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="11b3d-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="11b3d-115">**데이터 집합:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="11b3d-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="11b3d-116">**테이블:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="11b3d-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="11b3d-117">Element1</span><span class="sxs-lookup"><span data-stu-id="11b3d-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="11b3d-118">Text1</span><span class="sxs-lookup"><span data-stu-id="11b3d-118">Text1</span></span>|  
  
 <span data-ttu-id="11b3d-119">이러한 두 XML 문서는 동일한 스키마를 생성하려는 의도로 만들어졌겠지만, 각 문서에 포함된 요소에 따라 유추 과정의 결과가 크게 달라졌습니다.</span><span class="sxs-lookup"><span data-stu-id="11b3d-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="11b3d-120">Xml 문서에서 스키마를 생성할 때 발생할 수 있는 불일치를 방지 하려면 xml에서 **데이터 집합** 을 로드할 때 XSD (xml 스키마 정의 언어) 또는 XDR (Xml 데이터 축소)를 사용 하 여 스키마를 명시적으로 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="11b3d-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="11b3d-121">XML 스키마를 사용 하 여 **데이터 집합** 스키마를 명시적으로 지정 하는 방법에 대 한 자세한 내용은 [Xml 스키마에서 데이터 집합 관계형 구조 파생 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11b3d-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b3d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11b3d-122">See also</span></span>

- [<span data-ttu-id="11b3d-123">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="11b3d-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="11b3d-124">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="11b3d-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="11b3d-125">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="11b3d-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="11b3d-126">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="11b3d-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="11b3d-127">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="11b3d-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="11b3d-128">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="11b3d-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
