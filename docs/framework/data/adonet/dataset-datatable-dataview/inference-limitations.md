---
title: 유추 제한
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 4e0f63776162b60c9333ba47be58ea78a9b6805d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204837"
---
# <a name="inference-limitations"></a><span data-ttu-id="a2d9a-102">유추 제한</span><span class="sxs-lookup"><span data-stu-id="a2d9a-102">Inference Limitations</span></span>
<span data-ttu-id="a2d9a-103">XML에서 <xref:System.Data.DataSet> 스키마를 유추하는 과정을 통해 만들어지는 스키마는 각 문서의 XML 요소에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="a2d9a-104">예를 들어, 다음과 같은 XML 문서를 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="a2d9a-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="a2d9a-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a2d9a-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="a2d9a-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a2d9a-107">"문서 1"의 경우 "Element1"가 반복 되는 요소 이므로 유추 프로세스에서 "DocumentElement" 라는 **데이터 집합과** "Element1" 라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="a2d9a-108">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a2d9a-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a2d9a-109">**테이블** Element1</span><span class="sxs-lookup"><span data-stu-id="a2d9a-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a2d9a-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a2d9a-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="a2d9a-111">Text1</span><span class="sxs-lookup"><span data-stu-id="a2d9a-111">Text1</span></span>|  
|<span data-ttu-id="a2d9a-112">Text2</span><span class="sxs-lookup"><span data-stu-id="a2d9a-112">Text2</span></span>|  
  
 <span data-ttu-id="a2d9a-113">그러나 "Document2"의 경우 유추 프로세스는 "NewDataSet" 이라는 **데이터 집합과** "documentelement" 라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="a2d9a-114">"Element1"은 특성이나 자식 요소가 없으므로 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="a2d9a-115">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="a2d9a-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="a2d9a-116">**테이블** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a2d9a-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="a2d9a-117">Element1</span><span class="sxs-lookup"><span data-stu-id="a2d9a-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="a2d9a-118">Text1</span><span class="sxs-lookup"><span data-stu-id="a2d9a-118">Text1</span></span>|  
  
 <span data-ttu-id="a2d9a-119">이러한 두 XML 문서는 동일한 스키마를 생성하려는 의도로 만들어졌겠지만, 각 문서에 포함된 요소에 따라 유추 과정의 결과가 크게 달라졌습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="a2d9a-120">Xml 문서에서 스키마를 생성할 때 발생할 수 있는 불일치를 방지 하려면 xml에서 **데이터 집합** 을 로드할 때 XSD (xml 스키마 정의 언어) 또는 XDR (Xml 데이터 축소)를 사용 하 여 스키마를 명시적으로 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="a2d9a-121">XML 스키마를 사용 하 여 **데이터 집합** 스키마를 명시적으로 지정 하는 방법에 대 한 자세한 내용은 [Xml 스키마에서 데이터 집합 관계형 구조 파생 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2d9a-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d9a-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="a2d9a-122">See also</span></span>

- [<span data-ttu-id="a2d9a-123">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="a2d9a-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a2d9a-124">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="a2d9a-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a2d9a-125">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="a2d9a-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a2d9a-126">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="a2d9a-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a2d9a-127">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="a2d9a-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a2d9a-128">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="a2d9a-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
