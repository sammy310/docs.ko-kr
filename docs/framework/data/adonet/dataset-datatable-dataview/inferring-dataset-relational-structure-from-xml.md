---
title: XML에서 데이터 세트 관계형 구조 유추
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: fca50491120346dea3e09c82324225f2114380fc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177581"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a><span data-ttu-id="c23f1-102">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="c23f1-102">Inferring DataSet Relational Structure from XML</span></span>

<span data-ttu-id="c23f1-103"><xref:System.Data.DataSet>의 관계형 구조 또는 스키마는 테이블, 열, 제약 조건 및 관계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-103">The relational structure, or schema, of a <xref:System.Data.DataSet> is made up of tables, columns, constraints, and relations.</span></span> <span data-ttu-id="c23f1-104">XML에서 <xref:System.Data.DataSet>을 로드할 때 로드되는 XML에서 스키마를 명시적으로 또는 유추를 통해 미리 정의하거나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-104">When loading a <xref:System.Data.DataSet> from XML, the schema can be predefined, or it can be created, either explicitly or through inference, from the XML being loaded.</span></span> <span data-ttu-id="c23f1-105">XML에서 스키마 및 콘텐츠를 로드 하는 방법에 대 한 자세한 내용은 xml <xref:System.Data.DataSet> [에서 데이터 집합 로드](loading-a-dataset-from-xml.md) 및 [Xml에서 데이터 집합 스키마 정보 로드](loading-dataset-schema-information-from-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c23f1-105">For more information about loading the schema and contents of a <xref:System.Data.DataSet> from XML, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md) and [Loading DataSet Schema Information from XML](loading-dataset-schema-information-from-xml.md).</span></span>  
  
 <span data-ttu-id="c23f1-106">XML에서의 스키마를 <xref:System.Data.DataSet> 만드는 경우 기본 방법은 Xml [스키마 (xsd)에서 데이터 집합 관계형 구조 파생](deriving-dataset-relational-structure-from-xml-schema-xsd.md)의 설명에 따라 Xsd (xml 스키마 정의 언어)를 사용 하 여 스키마를 명시적으로 지정 하는 것이 고 XDR (xml 데이터 축소)입니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-106">If the schema of a <xref:System.Data.DataSet> is being created from XML, the preferred method is to explicitly specify the schema using either the XML Schema definition language (XSD) (as described in [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)) or the XML-Data Reduced (XDR).</span></span> <span data-ttu-id="c23f1-107">XML에서 XML 스키마나 XDR 스키마를 사용할 수 없으면 <xref:System.Data.DataSet>의 스키마는 XML 요소 및 특성의 구조로부터 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-107">If no XML Schema or XDR schema is available in the XML, the schema of the <xref:System.Data.DataSet> can be inferred from the structure of the XML elements and attributes.</span></span>  
  
 <span data-ttu-id="c23f1-108">이 단원에서는 XML 요소와 특성 및 이들의 구조, 그리고 결과로서 유추된 <xref:System.Data.DataSet> 스키마를 보여 줌으로써 <xref:System.Data.DataSet> 스키마 유추 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-108">This section describes the rules for <xref:System.Data.DataSet> schema inference by showing XML elements and attributes and their structure, and the resulting inferred <xref:System.Data.DataSet> schema.</span></span>  
  
 <span data-ttu-id="c23f1-109">XML 문서에 나타난 모든 특성을 유추 과정에 포함시켜야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-109">Not all attributes present in an XML document should be included in the inference process.</span></span> <span data-ttu-id="c23f1-110">네임스페이스로 한정된 특성에서는 XML 문서에는 중요하지만 <xref:System.Data.DataSet> 스키마에는 중요하지 않은 메타데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-110">Namespace-qualified attributes can include metadata that is important for the XML document but not for the <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="c23f1-111"><xref:System.Data.DataSet.InferXmlSchema%2A>를 사용하면 유추 과정에서 네임스페이스를 무시하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-111">Using <xref:System.Data.DataSet.InferXmlSchema%2A>, you can specify namespaces to be ignored during the inference process.</span></span> <span data-ttu-id="c23f1-112">자세한 내용은 [XML에서 데이터 집합 스키마 정보 로드](loading-dataset-schema-information-from-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c23f1-112">For more information, see [Loading DataSet Schema Information from XML](loading-dataset-schema-information-from-xml.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c23f1-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c23f1-113">In This Section</span></span>  

 [<span data-ttu-id="c23f1-114">데이터 세트 스키마 유추 프로세스 요약</span><span class="sxs-lookup"><span data-stu-id="c23f1-114">Summary of the DataSet Schema Inference Process</span></span>](summary-of-the-dataset-schema-inference-process.md)  
 <span data-ttu-id="c23f1-115">XML로부터 <xref:System.Data.DataSet>의 스키마를 유추하는 규칙에 대한 고급 요약 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-115">Provides a high-level summary of the rules for inferring the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="c23f1-116">테이블 유추</span><span class="sxs-lookup"><span data-stu-id="c23f1-116">Inferring Tables</span></span>](inferring-tables.md)  
 <span data-ttu-id="c23f1-117"><xref:System.Data.DataSet>에서 테이블로 유추되는 XML 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-117">Describes the XML elements that are inferred as tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="c23f1-118">열 유추</span><span class="sxs-lookup"><span data-stu-id="c23f1-118">Inferring Columns</span></span>](inferring-columns.md)  
 <span data-ttu-id="c23f1-119">테이블 열로 유추되는 XML 요소 및 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-119">Describes the XML elements and attributes that are inferred as table columns.</span></span>  
  
 [<span data-ttu-id="c23f1-120">관계 유추</span><span class="sxs-lookup"><span data-stu-id="c23f1-120">Inferring Relationships</span></span>](inferring-relationships.md)  
 <span data-ttu-id="c23f1-121">중첩된 유추 테이블에 사용하도록 만들어지는 <xref:System.Data.DataRelation> 및 <xref:System.Data.ForeignKeyConstraint> 개체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-121">Describes the <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects created for nested, inferred tables.</span></span>  
  
 [<span data-ttu-id="c23f1-122">요소 텍스트 유추</span><span class="sxs-lookup"><span data-stu-id="c23f1-122">Inferring Element Text</span></span>](inferring-element-text.md)  
 <span data-ttu-id="c23f1-123">XML 요소의 텍스트에 사용하기 위해 만드는 열과 XML 요소 내의 텍스트가 무시되는 경우에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-123">Describes the columns that are created for text in XML elements, and explains when text in XML elements is ignored.</span></span>  
  
 [<span data-ttu-id="c23f1-124">유추 제한</span><span class="sxs-lookup"><span data-stu-id="c23f1-124">Inference Limitations</span></span>](inference-limitations.md)  
 <span data-ttu-id="c23f1-125">스키마 유추의 제한 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-125">Discusses the limitations of schema inference.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c23f1-126">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="c23f1-126">Related Sections</span></span>  

 [<span data-ttu-id="c23f1-127">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="c23f1-127">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="c23f1-128"><xref:System.Data.DataSet> 개체가 XML 데이터와 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-128">Describes how the <xref:System.Data.DataSet> object interacts with XML data.</span></span>  
  
 [<span data-ttu-id="c23f1-129">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="c23f1-129">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="c23f1-130">XSD(XML 스키마 정의 언어) 스키마에서 만들어지는 <xref:System.Data.DataSet>의 관계 구조 또는 스키마에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-130">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="c23f1-131">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c23f1-131">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="c23f1-132">ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 애플리케이션 데이터를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c23f1-132">Describes the ADO.NET architecture and components and how to use them to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23f1-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c23f1-133">See also</span></span>

- [<span data-ttu-id="c23f1-134">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c23f1-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
