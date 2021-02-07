---
description: '자세한 정보: 스키마 가져오기 및 내보내기'
title: 스키마 가져오기 및 내보내기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
ms.openlocfilehash: 3381cfee1d431b53a6f579ae50655a6f4fe80a3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733166"
---
# <a name="schema-import-and-export"></a><span data-ttu-id="08160-103">스키마 가져오기 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="08160-103">Schema Import and Export</span></span>

<span data-ttu-id="08160-104">WCF (Windows Communication Foundation)에는 새로운 serialization 엔진인가 포함 되어 있습니다 <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="08160-104">Windows Communication Foundation (WCF) includes a new serialization engine, the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="08160-105">는 `DataContractSerializer` .NET Framework 개체와 XML 사이를 변환 합니다 (양방향).</span><span class="sxs-lookup"><span data-stu-id="08160-105">The `DataContractSerializer` translates between .NET Framework objects and XML (in both directions).</span></span> <span data-ttu-id="08160-106">WCF에는 serializer 자체 외에도 연결 된 스키마 가져오기 및 스키마 내보내기 메커니즘이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-106">In addition to the serializer itself, WCF includes associated schema import and schema export mechanisms.</span></span> <span data-ttu-id="08160-107">*스키마* 는 serializer가 생성 하거나 역직렬 변환기가 액세스할 수 있는 XML의 모양에 대 한 공식적이 고 정확 하며 컴퓨터에서 읽을 수 있는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="08160-107">*Schema* is a formal, precise, and machine-readable description of the shape of XML that the serializer produces or that the deserializer can access.</span></span> <span data-ttu-id="08160-108">WCF에서는 W3C (World Wide Web 컨소시엄) XSD (XML 스키마 정의 언어)를 스키마 표현으로 사용 하며,이는 다양 한 타사 플랫폼과 크게 상호 운용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-108">WCF uses the World Wide Web Consortium (W3C) XML Schema definition language (XSD) as its schema representation, which is widely interoperable with numerous third-party platforms.</span></span>  
  
 <span data-ttu-id="08160-109">스키마 가져오기 구성 요소인는 <xref:System.Runtime.Serialization.XsdDataContractImporter> XSD 스키마 문서를 사용 하 고 serialize 된 형식이 지정 된 스키마에 해당 하는 .NET Framework 클래스 (일반적으로 데이터 계약 클래스)를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="08160-109">The schema import component, <xref:System.Runtime.Serialization.XsdDataContractImporter>, takes an XSD schema document and generates .NET Framework classes (normally data contract classes) such that the serialized forms correspond to the given schema.</span></span>  
  
 <span data-ttu-id="08160-110">예를 들어 다음과 같은 스키마 단편이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-110">For example, the following schema fragment:</span></span>  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 <span data-ttu-id="08160-111">코드를 보다 쉽게 파악할 수 있도록 간소화된 다음과 같은 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="08160-111">generates the following type (simplified slightly for better readability).</span></span>  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 <span data-ttu-id="08160-112">생성 된 형식은 다음과 같은 몇 가지 데이터 계약 모범 사례를 따릅니다 ( [모범 사례: 데이터 계약 버전 관리](../best-practices-data-contract-versioning.md)참조).</span><span class="sxs-lookup"><span data-stu-id="08160-112">Note that the generated type follows several data contract best practices (found in [Best Practices: Data Contract Versioning](../best-practices-data-contract-versioning.md)):</span></span>  
  
- <span data-ttu-id="08160-113">이 형식은 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="08160-113">The type implements the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span> <span data-ttu-id="08160-114">자세한 내용은 [호환 가능한 데이터 계약](forward-compatible-data-contracts.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08160-114">For more information, see [Forward-Compatible Data Contracts](forward-compatible-data-contracts.md).</span></span>  
  
- <span data-ttu-id="08160-115">데이터 멤버는 private 필드를 래핑하는 public 속성으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="08160-115">Data members are implemented as public properties that wrap private fields.</span></span>  
  
- <span data-ttu-id="08160-116">클래스는 부분 클래스로, 생성된 코드를 수정하지 않고 추가 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-116">The class is a partial class, and additions can be made without modifying generated code.</span></span>  
  
 <span data-ttu-id="08160-117"><xref:System.Runtime.Serialization.XsdDataContractExporter>를 사용하면 반대로 작업할 수 있습니다. 즉 `DataContractSerializer`로 serialize할 수 있는 형식을 사용하고 XSD 스키마 문서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-117">The <xref:System.Runtime.Serialization.XsdDataContractExporter> enables you to do the reverse—take types that are serializable with the `DataContractSerializer` and generate an XSD Schema document.</span></span>  
  
## <a name="fidelity-is-not-guaranteed"></a><span data-ttu-id="08160-118">정확도는 보장되지 않음</span><span class="sxs-lookup"><span data-stu-id="08160-118">Fidelity Is Not Guaranteed</span></span>  

 <span data-ttu-id="08160-119">스키마나 형식을 통해 완벽히 정확한 라운드트립을 만든다고 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-119">It is not guaranteed that schema or types make a round trip with total fidelity.</span></span> <span data-ttu-id="08160-120">*라운드트립* 이란 스키마를 가져와서 클래스 집합을 만들고 결과를 내보내 스키마를 다시 만드는 것을 의미 합니다. 동일한 스키마가 반환 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-120">(A *round trip* means to import a schema to create a set of classes, and export the result to create a schema again.) The same schema may not be returned.</span></span> <span data-ttu-id="08160-121">이 프로세스를 반대로 해도 정확도는 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-121">Reversing the process is also not guaranteed to preserve fidelity.</span></span> <span data-ttu-id="08160-122">(형식의 스키마를 생성하기 위해 형식을 내보낸 다음 그 형식을 다시 가져옵니다.)</span><span class="sxs-lookup"><span data-stu-id="08160-122">(Export a type to generate its schema, and then import the type back.</span></span> <span data-ttu-id="08160-123">이때도 동일한 형식은 반환되지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08160-123">It is unlikely the same type is returned.)</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="08160-124">지원 형식</span><span class="sxs-lookup"><span data-stu-id="08160-124">Supported Types</span></span>  

 <span data-ttu-id="08160-125">데이터 계약 모델은 WC3 스키마의 제한된 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="08160-125">The data contract model supports only a limited subset of the WC3 schema.</span></span> <span data-ttu-id="08160-126">이 하위 집합을 따르지 않는 스키마는 가져오기 프로세스 동안 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="08160-126">Any schema that does not conform to this subset will cause an exception during the import process.</span></span> <span data-ttu-id="08160-127">예를 들어 데이터 계약의 데이터 멤버가 XML 특성으로 serialize되도록 지정하는 방법이 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="08160-127">For example, there is no way to specify that a data member of a data contract should be serialized as an XML attribute.</span></span> <span data-ttu-id="08160-128">이 경우, XML 특성을 사용하도록 하는 스키마는 지원되지 않고, 올바른 XML 프로젝션으로 데이터 계약을 생성할 수 없으므로 가져오기 작업 동안 예외가 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="08160-128">Thus, schemas that require the use of XML attributes are not supported and will cause exceptions during import, because it is impossible to generate a data contract with the correct XML projection.</span></span>  
  
 <span data-ttu-id="08160-129">예를 들어 다음과 같은 스키마 단편은 가져오기 기본 설정을 사용하여 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-129">For example, the following schema fragment cannot be imported using the default import settings.</span></span>  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 <span data-ttu-id="08160-130">자세한 내용은 [데이터 계약 스키마 참조](data-contract-schema-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08160-130">For more information, see [Data Contract Schema Reference](data-contract-schema-reference.md).</span></span> <span data-ttu-id="08160-131">스키마가 데이터 계약 규칙을 따르지 않으면 다른 serialization 엔진을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08160-131">If a schema does not conform to the data contract rules, use a different serialization engine.</span></span> <span data-ttu-id="08160-132">예를 들어 <xref:System.Xml.Serialization.XmlSerializer>는 별도의 자체 스키마 가져오기 메커니즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08160-132">For example, the <xref:System.Xml.Serialization.XmlSerializer> uses its own separate schema import mechanism.</span></span> <span data-ttu-id="08160-133">또한 지원되는 스키마 범위가 확장되는 특별한 가져오기 모드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08160-133">Also, there is a special import mode in which the range of supported schema is expanded.</span></span> <span data-ttu-id="08160-134">자세한 내용은 <xref:System.Xml.Serialization.IXmlSerializable> [클래스 생성을 위한 스키마 가져오기](importing-schema-to-generate-classes.md)에서 형식 생성에 대 한 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08160-134">For more information, see the section about generating <xref:System.Xml.Serialization.IXmlSerializable> types in [Importing Schema to Generate Classes](importing-schema-to-generate-classes.md).</span></span>  
  
 <span data-ttu-id="08160-135">는를 사용 하 여 `XsdDataContractExporter` serialize 할 수 있는 모든 .NET Framework 형식을 지원 합니다 `DataContractSerializer` .</span><span class="sxs-lookup"><span data-stu-id="08160-135">The `XsdDataContractExporter` supports any .NET Framework types that can be serialized with the `DataContractSerializer`.</span></span> <span data-ttu-id="08160-136">자세한 내용은 [데이터 계약 Serializer에서 지 원하는 형식](types-supported-by-the-data-contract-serializer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08160-136">For more information, see [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md).</span></span> <span data-ttu-id="08160-137">`XsdDataContractExporter`를 사용하여 스키마를 생성하지 않는 이상, `XsdDataContractImporter`를 통해 생성된 스키마는 일반적으로 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>가 사용할 수 있는 유효한 데이터가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08160-137">Note that schema generated using the `XsdDataContractExporter` is normally valid data that the `XsdDataContractImporter` can use (unless the <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> is used to customize the schema).</span></span>  
  
 <span data-ttu-id="08160-138">를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Runtime.Serialization.XsdDataContractImporter> [클래스 생성을 위한 스키마 가져오기](importing-schema-to-generate-classes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08160-138">For more information about using the <xref:System.Runtime.Serialization.XsdDataContractImporter>, see [Importing Schema to Generate Classes](importing-schema-to-generate-classes.md).</span></span>  
  
 <span data-ttu-id="08160-139">를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Runtime.Serialization.XsdDataContractExporter> [클래스에서 스키마 내보내기](exporting-schemas-from-classes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08160-139">For more information about using the <xref:System.Runtime.Serialization.XsdDataContractExporter>, see [Exporting Schemas from Classes](exporting-schemas-from-classes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08160-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08160-140">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [<span data-ttu-id="08160-141">스키마를 가져와 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="08160-141">Importing Schema to Generate Classes</span></span>](importing-schema-to-generate-classes.md)
- [<span data-ttu-id="08160-142">클래스에서 스키마 내보내기</span><span class="sxs-lookup"><span data-stu-id="08160-142">Exporting Schemas from Classes</span></span>](exporting-schemas-from-classes.md)
