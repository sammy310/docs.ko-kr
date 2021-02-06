---
description: '자세히 알아보기: XML에서 데이터 집합 관계형 구조 유추'
title: XML에서 데이터 세트 관계형 구조 유추
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: d89b6a42e7e1bc3d7514f180329e9c1d877a67ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652226"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a><span data-ttu-id="0a4f3-103">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="0a4f3-103">Inferring DataSet Relational Structure from XML</span></span>

<span data-ttu-id="0a4f3-104"><xref:System.Data.DataSet>의 관계형 구조 또는 스키마는 테이블, 열, 제약 조건 및 관계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-104">The relational structure, or schema, of a <xref:System.Data.DataSet> is made up of tables, columns, constraints, and relations.</span></span> <span data-ttu-id="0a4f3-105">XML에서 <xref:System.Data.DataSet>을 로드할 때 로드되는 XML에서 스키마를 명시적으로 또는 유추를 통해 미리 정의하거나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-105">When loading a <xref:System.Data.DataSet> from XML, the schema can be predefined, or it can be created, either explicitly or through inference, from the XML being loaded.</span></span> <span data-ttu-id="0a4f3-106">XML에서 스키마 및 콘텐츠를 로드 하는 방법에 대 한 자세한 내용은 xml <xref:System.Data.DataSet> [에서 데이터 집합 로드](loading-a-dataset-from-xml.md) 및 [Xml에서 데이터 집합 스키마 정보 로드](loading-dataset-schema-information-from-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-106">For more information about loading the schema and contents of a <xref:System.Data.DataSet> from XML, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md) and [Loading DataSet Schema Information from XML](loading-dataset-schema-information-from-xml.md).</span></span>  
  
 <span data-ttu-id="0a4f3-107">XML에서의 스키마를 <xref:System.Data.DataSet> 만드는 경우 기본 방법은 Xml [스키마 (xsd)에서 데이터 집합 관계형 구조 파생](deriving-dataset-relational-structure-from-xml-schema-xsd.md)의 설명에 따라 Xsd (xml 스키마 정의 언어)를 사용 하 여 스키마를 명시적으로 지정 하는 것이 고, 그렇지 않으면 XDR (XML-Data 축소)입니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-107">If the schema of a <xref:System.Data.DataSet> is being created from XML, the preferred method is to explicitly specify the schema using either the XML Schema definition language (XSD) (as described in [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)) or the XML-Data Reduced (XDR).</span></span> <span data-ttu-id="0a4f3-108">XML에서 XML 스키마나 XDR 스키마를 사용할 수 없으면 <xref:System.Data.DataSet>의 스키마는 XML 요소 및 특성의 구조로부터 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-108">If no XML Schema or XDR schema is available in the XML, the schema of the <xref:System.Data.DataSet> can be inferred from the structure of the XML elements and attributes.</span></span>  
  
 <span data-ttu-id="0a4f3-109">이 단원에서는 XML 요소와 특성 및 이들의 구조, 그리고 결과로서 유추된 <xref:System.Data.DataSet> 스키마를 보여 줌으로써 <xref:System.Data.DataSet> 스키마 유추 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-109">This section describes the rules for <xref:System.Data.DataSet> schema inference by showing XML elements and attributes and their structure, and the resulting inferred <xref:System.Data.DataSet> schema.</span></span>  
  
 <span data-ttu-id="0a4f3-110">XML 문서에 나타난 모든 특성을 유추 과정에 포함시켜야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-110">Not all attributes present in an XML document should be included in the inference process.</span></span> <span data-ttu-id="0a4f3-111">네임스페이스로 한정된 특성에서는 XML 문서에는 중요하지만 <xref:System.Data.DataSet> 스키마에는 중요하지 않은 메타데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-111">Namespace-qualified attributes can include metadata that is important for the XML document but not for the <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="0a4f3-112"><xref:System.Data.DataSet.InferXmlSchema%2A>를 사용하면 유추 과정에서 네임스페이스를 무시하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-112">Using <xref:System.Data.DataSet.InferXmlSchema%2A>, you can specify namespaces to be ignored during the inference process.</span></span> <span data-ttu-id="0a4f3-113">자세한 내용은 [XML에서 데이터 집합 스키마 정보 로드](loading-dataset-schema-information-from-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-113">For more information, see [Loading DataSet Schema Information from XML](loading-dataset-schema-information-from-xml.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a4f3-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0a4f3-114">In This Section</span></span>  

 [<span data-ttu-id="0a4f3-115">데이터 세트 스키마 유추 프로세스 요약</span><span class="sxs-lookup"><span data-stu-id="0a4f3-115">Summary of the DataSet Schema Inference Process</span></span>](summary-of-the-dataset-schema-inference-process.md)  
 <span data-ttu-id="0a4f3-116">XML로부터 <xref:System.Data.DataSet>의 스키마를 유추하는 규칙에 대한 고급 요약 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-116">Provides a high-level summary of the rules for inferring the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="0a4f3-117">테이블 유추</span><span class="sxs-lookup"><span data-stu-id="0a4f3-117">Inferring Tables</span></span>](inferring-tables.md)  
 <span data-ttu-id="0a4f3-118"><xref:System.Data.DataSet>에서 테이블로 유추되는 XML 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-118">Describes the XML elements that are inferred as tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="0a4f3-119">열 유추</span><span class="sxs-lookup"><span data-stu-id="0a4f3-119">Inferring Columns</span></span>](inferring-columns.md)  
 <span data-ttu-id="0a4f3-120">테이블 열로 유추되는 XML 요소 및 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-120">Describes the XML elements and attributes that are inferred as table columns.</span></span>  
  
 [<span data-ttu-id="0a4f3-121">관계 유추</span><span class="sxs-lookup"><span data-stu-id="0a4f3-121">Inferring Relationships</span></span>](inferring-relationships.md)  
 <span data-ttu-id="0a4f3-122">중첩된 유추 테이블에 사용하도록 만들어지는 <xref:System.Data.DataRelation> 및 <xref:System.Data.ForeignKeyConstraint> 개체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-122">Describes the <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects created for nested, inferred tables.</span></span>  
  
 [<span data-ttu-id="0a4f3-123">요소 텍스트 유추</span><span class="sxs-lookup"><span data-stu-id="0a4f3-123">Inferring Element Text</span></span>](inferring-element-text.md)  
 <span data-ttu-id="0a4f3-124">XML 요소의 텍스트에 사용하기 위해 만드는 열과 XML 요소 내의 텍스트가 무시되는 경우에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-124">Describes the columns that are created for text in XML elements, and explains when text in XML elements is ignored.</span></span>  
  
 [<span data-ttu-id="0a4f3-125">유추 제한</span><span class="sxs-lookup"><span data-stu-id="0a4f3-125">Inference Limitations</span></span>](inference-limitations.md)  
 <span data-ttu-id="0a4f3-126">스키마 유추의 제한 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-126">Discusses the limitations of schema inference.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a4f3-127">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="0a4f3-127">Related Sections</span></span>  

 [<span data-ttu-id="0a4f3-128">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="0a4f3-128">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="0a4f3-129"><xref:System.Data.DataSet> 개체가 XML 데이터와 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-129">Describes how the <xref:System.Data.DataSet> object interacts with XML data.</span></span>  
  
 [<span data-ttu-id="0a4f3-130">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="0a4f3-130">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="0a4f3-131">XSD(XML 스키마 정의 언어) 스키마에서 만들어지는 <xref:System.Data.DataSet>의 관계 구조 또는 스키마에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-131">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="0a4f3-132">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="0a4f3-132">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="0a4f3-133">ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 애플리케이션 데이터를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4f3-133">Describes the ADO.NET architecture and components and how to use them to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4f3-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a4f3-134">See also</span></span>

- [<span data-ttu-id="0a4f3-135">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="0a4f3-135">ADO.NET Overview</span></span>](../ado-net-overview.md)
