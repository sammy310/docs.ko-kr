---
title: 유추 제한
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 308d2ffdd9e2cb16626861e25613657f341a4ccb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076245"
---
# <a name="inference-limitations"></a><span data-ttu-id="f5180-102">유추 제한</span><span class="sxs-lookup"><span data-stu-id="f5180-102">Inference Limitations</span></span>
<span data-ttu-id="f5180-103">XML에서 <xref:System.Data.DataSet> 스키마를 유추하는 과정을 통해 만들어지는 스키마는 각 문서의 XML 요소에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5180-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="f5180-104">예를 들어, 다음과 같은 XML 문서를 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="f5180-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="f5180-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="f5180-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f5180-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="f5180-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f5180-107">"Document1," 유추 과정에서 생성 된 **데이터 집합** "Element1" 반복 요소 이기 때문에 "DocumentElement" 및 "Element1," 라는 테이블을 명명 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5180-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="f5180-108">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f5180-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f5180-109">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="f5180-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f5180-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="f5180-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="f5180-111">Text1</span><span class="sxs-lookup"><span data-stu-id="f5180-111">Text1</span></span>|  
|<span data-ttu-id="f5180-112">Text2</span><span class="sxs-lookup"><span data-stu-id="f5180-112">Text2</span></span>|  
  
 <span data-ttu-id="f5180-113">그러나 "문서 2"에 대 한 유추 과정에서 생성 된 **데이터 집합** "NewDataSet" 및 "DocumentElement." 라는 테이블</span><span class="sxs-lookup"><span data-stu-id="f5180-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="f5180-114">"Element1"은 특성이나 자식 요소가 없으므로 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5180-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="f5180-115">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="f5180-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="f5180-116">**테이블:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f5180-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="f5180-117">Element1</span><span class="sxs-lookup"><span data-stu-id="f5180-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="f5180-118">Text1</span><span class="sxs-lookup"><span data-stu-id="f5180-118">Text1</span></span>|  
  
 <span data-ttu-id="f5180-119">이러한 두 XML 문서는 동일한 스키마를 생성하려는 의도로 만들어졌겠지만, 각 문서에 포함된 요소에 따라 유추 과정의 결과가 크게 달라졌습니다.</span><span class="sxs-lookup"><span data-stu-id="f5180-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="f5180-120">XML 문서에서 스키마를 생성할 때 발생할 수 있는 불일치를 방지 하려면 스키마를 로드할 때 XML 스키마 정의 언어 (XSD) 또는 Xml-data Reduced (XDR)를 사용 하 여 명시적으로 지정 하는 권장 된 **데이터 집합** 에서 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="f5180-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="f5180-121">명시적으로 지정 하는 방법에 대 한 자세한 내용은 **데이터 집합** XML 스키마를 사용 하 여 스키마를 참조 하십시오 [파생 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5180-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5180-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5180-122">See also</span></span>

- [<span data-ttu-id="f5180-123">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="f5180-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="f5180-124">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="f5180-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="f5180-125">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="f5180-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="f5180-126">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="f5180-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="f5180-127">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="f5180-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f5180-128">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="f5180-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
