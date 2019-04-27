---
title: 데이터 계약 스키마 참조
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: a4ddaaea2133a8adf5271628f442644194a7f453
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857183"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="6e6ce-102">데이터 계약 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="6e6ce-102">Data Contract Schema Reference</span></span>
<span data-ttu-id="6e6ce-103">이 항목에서는 XML serialization에 대한 CLR(공용 언어 런타임) 형식을 설명하기 위해 <xref:System.Runtime.Serialization.DataContractSerializer> 에서 사용하는 XSD(XML 스키마) 하위 집합에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>  
  
## <a name="datacontractserializer-mappings"></a><span data-ttu-id="6e6ce-104">DataContractSerializer 매핑</span><span class="sxs-lookup"><span data-stu-id="6e6ce-104">DataContractSerializer Mappings</span></span>  
 <span data-ttu-id="6e6ce-105">합니다 `DataContractSerializer` 메타 데이터 끝점을 사용 하는 Windows Communication Foundation (WCF) 서비스에서 메타 데이터를 내보낼 때 CLR 형식을 XSD에 매핑합니다 또는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="6e6ce-106">자세한 내용은 [데이터 계약 Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-106">For more information, see [Data Contract Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).</span></span>  
  
 <span data-ttu-id="6e6ce-107">또한 WSDL(웹 서비스 기술 언어) 또는 XSD 문서에 액세스하여 서비스 또는 클라이언트에 대한 데이터 계약을 생성하기 위해 Svcutil.exe를 사용하는 경우 `DataContractSerializer` 는 XSD를 CLR 형식에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>  
  
 <span data-ttu-id="6e6ce-108">이 문서에 명시된 요구 사항을 준수하는 XML 스키마 인스턴스만 `DataContractSerializer`를 사용하여 CLR 형식에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>  
  
### <a name="support-levels"></a><span data-ttu-id="6e6ce-109">지원 수준</span><span class="sxs-lookup"><span data-stu-id="6e6ce-109">Support Levels</span></span>  
 <span data-ttu-id="6e6ce-110">`DataContractSerializer` 는 지정된 XML 스키마 기능에 대해 다음과 같은 수준의 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>  
  
-   <span data-ttu-id="6e6ce-111">**지원**.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-111">**Supported**.</span></span> <span data-ttu-id="6e6ce-112">`DataContractSerializer`를 사용하여 이 기능에서 CLR 형식 또는 특성(또는 둘 다)으로 명시적 매핑이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>  
  
-   <span data-ttu-id="6e6ce-113">**무시**.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-113">**Ignored**.</span></span> <span data-ttu-id="6e6ce-114">`DataContractSerializer`가 가져온 스키마에 이 기능을 사용할 수 있지만 코드 생성에 영향을 주지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>  
  
-   <span data-ttu-id="6e6ce-115">**사용할 수 없음**.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-115">**Forbidden**.</span></span> <span data-ttu-id="6e6ce-116">`DataContractSerializer` 는 이 기능을 사용하여 스키마 가져오기 작업을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="6e6ce-117">예를 들어, 이러한 기능을 사용하는 스키마를 통해 WSDL에 액세스하는 경우 Svcutil.exe는 대신 <xref:System.Xml.Serialization.XmlSerializer> 로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="6e6ce-118">이 기능은 기본적으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-118">This is by default.</span></span>  
  
## <a name="general-information"></a><span data-ttu-id="6e6ce-119">일반 정보</span><span class="sxs-lookup"><span data-stu-id="6e6ce-119">General Information</span></span>  
  
-   <span data-ttu-id="6e6ce-120">스키마 네임스페이스에 대해서는 [XML Schema](https://go.microsoft.com/fwlink/?LinkId=95475)에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-120">The schema namespace is described at [XML Schema](https://go.microsoft.com/fwlink/?LinkId=95475).</span></span> <span data-ttu-id="6e6ce-121">이 문서에서는 접두사 "xs"가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-121">The prefix "xs" is used in this document.</span></span>  
  
-   <span data-ttu-id="6e6ce-122">스키마 네임스페이스가 아닌 네임스페이스를 가진 특성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-122">Any attributes with a non-schema namespace are ignored.</span></span>  
  
-   <span data-ttu-id="6e6ce-123">이 문서에서 설명한 주석을 제외한 모든 주석이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-123">Any annotations (except for those described in this document) are ignored.</span></span>  
  
### <a name="xsschema-attributes"></a><span data-ttu-id="6e6ce-124">\<xs: schema >: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-124">\<xs:schema>: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-125">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-125">Attribute</span></span>|<span data-ttu-id="6e6ce-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="6e6ce-126">DataContract</span></span>|  
|---------------|------------------|  
|`attributeFormDefault`|<span data-ttu-id="6e6ce-127">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-127">Ignored.</span></span>|  
|`blockDefault`|<span data-ttu-id="6e6ce-128">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-128">Ignored.</span></span>|  
|`elementFormDefault`|<span data-ttu-id="6e6ce-129">정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-129">Must be qualified.</span></span> <span data-ttu-id="6e6ce-130">`DataContractSerializer`에서 스키마를 지원하려면 모든 요소가 정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="6e6ce-131">설정 하거나이 작업을 수행할 수 있습니다 xs:schema/@elementFormDefault 을 "qualified" 또는 설정 하 여 xs:element/@form 각 개별 요소 선언에 "qualified"로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|  
|`finalDefault`|<span data-ttu-id="6e6ce-132">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-132">Ignored.</span></span>|  
|`Id`|<span data-ttu-id="6e6ce-133">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-133">Ignored.</span></span>|  
|`targetNamespace`|<span data-ttu-id="6e6ce-134">지원되며 데이터 계약 네임스페이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="6e6ce-135">이 특성을 지정하지 않으면 빈 네임스페이스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="6e6ce-136">예약된 된 네임 스페이스를 사용할 수 없습니다. `http://schemas.microsoft.com/2003/10/Serialization/`합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|  
|`version`|<span data-ttu-id="6e6ce-137">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-137">Ignored.</span></span>|  
  
### <a name="xsschema-contents"></a><span data-ttu-id="6e6ce-138">\<xs:schema>: contents</span><span class="sxs-lookup"><span data-stu-id="6e6ce-138">\<xs:schema>: contents</span></span>  
  
|<span data-ttu-id="6e6ce-139">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-139">Contents</span></span>|<span data-ttu-id="6e6ce-140">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-140">Schema</span></span>|  
|--------------|------------|  
|`include`|<span data-ttu-id="6e6ce-141">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-141">Supported.</span></span> <span data-ttu-id="6e6ce-142">`DataContractSerializer` 는 xs:include 및 xs:import를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-142">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="6e6ce-143">그러나 Svcutil.exe는 로컬 파일에서 메타데이터를 로드할 때 다음 `xs:include/@schemaLocation` 및 `xs:import/@location` 참조를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="6e6ce-144">이러한 경우 스키마 파일 목록은 `include` 가 아닌 out-of-band 메커니즘을 통해 전달해야 합니다. `include`된 스키마 문서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`redefine`|<span data-ttu-id="6e6ce-145">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-145">Forbidden.</span></span> <span data-ttu-id="6e6ce-146">보안상의 이유로 `xs:redefine` 는 `DataContractSerializer` 을 사용할 수 없습니다. `x:redefine` 을 사용하려면 `schemaLocation` 을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="6e6ce-147">상황에 따라 DataContract를 사용하는 Svcutil.exe는 `schemaLocation`사용을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|  
|`import`|<span data-ttu-id="6e6ce-148">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-148">Supported.</span></span> <span data-ttu-id="6e6ce-149">`DataContractSerializer` 는 `xs:include` 및 `xs:import`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-149">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="6e6ce-150">그러나 Svcutil.exe는 로컬 파일에서 메타데이터를 로드할 때 다음 `xs:include/@schemaLocation` 및 `xs:import/@location` 참조를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="6e6ce-151">이러한 경우 스키마 파일 목록은 `include` 가 아닌 out-of-band 메커니즘을 통해 전달해야 합니다. `include`된 스키마 문서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`simpleType`|<span data-ttu-id="6e6ce-152">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-152">Supported.</span></span> <span data-ttu-id="6e6ce-153">`xs:simpleType` 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-153">See the `xs:simpleType` section.</span></span>|  
|`complexType`|<span data-ttu-id="6e6ce-154">지원되며 데이터 계약으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="6e6ce-155">`xs:complexType` 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-155">See the `xs:complexType` section.</span></span>|  
|`group`|<span data-ttu-id="6e6ce-156">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-156">Ignored.</span></span> <span data-ttu-id="6e6ce-157">`DataContractSerializer` 는 `xs:group`, `xs:attributeGroup`및 `xs:attribute`사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-157">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="6e6ce-158">이러한 선언은 `xs:schema`의 자식으로 무시되며 `complexType` 또는 기타 지원되는 구문 내에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`attributeGroup`|<span data-ttu-id="6e6ce-159">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-159">Ignored.</span></span> <span data-ttu-id="6e6ce-160">`DataContractSerializer` 는 `xs:group`, `xs:attributeGroup`및 `xs:attribute`사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-160">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="6e6ce-161">이러한 선언은 `xs:schema`의 자식으로 무시되며 `complexType` 또는 기타 지원되는 구문 내에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`element`|<span data-ttu-id="6e6ce-162">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-162">Supported.</span></span> <span data-ttu-id="6e6ce-163">GED(전역 요소 선언)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-163">See Global Element Declaration (GED).</span></span>|  
|`attribute`|<span data-ttu-id="6e6ce-164">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-164">Ignored.</span></span> <span data-ttu-id="6e6ce-165">`DataContractSerializer` 는 `xs:group`, `xs:attributeGroup`및 `xs:attribute`사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-165">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="6e6ce-166">이러한 선언은 `xs:schema`의 자식으로 무시되며 `complexType` 또는 기타 지원되는 구문 내에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`notation`|<span data-ttu-id="6e6ce-167">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-167">Ignored.</span></span>|  
  
## <a name="complex-types--xscomplextype"></a><span data-ttu-id="6e6ce-168">복합 형식 – \<xs:complexType ></span><span class="sxs-lookup"><span data-stu-id="6e6ce-168">Complex Types – \<xs:complexType></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="6e6ce-169">일반 정보</span><span class="sxs-lookup"><span data-stu-id="6e6ce-169">General Information</span></span>  
 <span data-ttu-id="6e6ce-170">각 복합 형식 \<xs:complexType > 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>  
  
### <a name="xscomplextype-attributes"></a><span data-ttu-id="6e6ce-171">\<xs:complexType >: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-171">\<xs:complexType>: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-172">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-172">Attribute</span></span>|<span data-ttu-id="6e6ce-173">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-173">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="6e6ce-174">false이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6e6ce-174">Must be false (default).</span></span>|  
|`block`|<span data-ttu-id="6e6ce-175">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-175">Forbidden.</span></span>|  
|`final`|<span data-ttu-id="6e6ce-176">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-176">Ignored.</span></span>|  
|`id`|<span data-ttu-id="6e6ce-177">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-177">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="6e6ce-178">false이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6e6ce-178">Must be false (default).</span></span>|  
|`name`|<span data-ttu-id="6e6ce-179">지원되며 데이터 계약 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="6e6ce-180">이름에 마침표가 있는 경우 형식을 내부 형식에 매핑하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="6e6ce-181">예를 들어, `A.B` 라는 복합 형식은 `A`라는 데이터 계약 이름을 가진 형식의 내부 형식인 데이터 계약 형식으로 매핑되지만 이러한 데이터 계약 형식이 있는 경우에만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="6e6ce-182">둘 이상의 중첩 수준이 가능합니다. 예를 들어, `A.B.C` 가 내부 형식일 수 있지만 `A` 및 `A.B` 가 모두 있는 경우에만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|  
  
### <a name="xscomplextype-contents"></a><span data-ttu-id="6e6ce-183">\<xs:complexType>: contents</span><span class="sxs-lookup"><span data-stu-id="6e6ce-183">\<xs:complexType>: contents</span></span>  
  
|<span data-ttu-id="6e6ce-184">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-184">Contents</span></span>|<span data-ttu-id="6e6ce-185">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-185">Schema</span></span>|  
|--------------|------------|  
|`simpleContent`|<span data-ttu-id="6e6ce-186">확장을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="6e6ce-187">제한은 `anySimpleType`에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-187">Restriction is allowed only from `anySimpleType`.</span></span>|  
|`complexContent`|<span data-ttu-id="6e6ce-188">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-188">Supported.</span></span> <span data-ttu-id="6e6ce-189">"상속"을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-189">See "Inheritance".</span></span>|  
|`group`|<span data-ttu-id="6e6ce-190">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-190">Forbidden.</span></span>|  
|`all`|<span data-ttu-id="6e6ce-191">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-191">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="6e6ce-192">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6e6ce-192">Forbidden</span></span>|  
|`sequence`|<span data-ttu-id="6e6ce-193">지원되며 데이터 계약의 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-193">Supported, maps to data members of a data contract.</span></span>|  
|`attribute`|<span data-ttu-id="6e6ce-194">한 가지 예외를 포함하여 use="prohibited"인 경우에도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="6e6ce-195">표준 Serialization 스키마 네임스페이스에서 선택적 특성만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="6e6ce-196">이러한 특성은 데이터 계약 프로그래밍 모델의 데이터 멤버에 매핑되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="6e6ce-197">현재 이러한 하나의 특성만 의미가 있으며, 여기에 대해서는 ISerializable 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="6e6ce-198">다른 특성은 모두 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-198">All others are ignored.</span></span>|  
|`attributeGroup`|<span data-ttu-id="6e6ce-199">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-199">Forbidden.</span></span> <span data-ttu-id="6e6ce-200">WCF v1 릴리스에서 `DataContractSerializer` 존재를 무시 `attributeGroup` 내에서 `xs:complexType`합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|  
|`anyAttribute`|<span data-ttu-id="6e6ce-201">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-201">Forbidden.</span></span>|  
|<span data-ttu-id="6e6ce-202">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-202">(empty)</span></span>|<span data-ttu-id="6e6ce-203">데이터 멤버 없이 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-203">Maps to a data contract with no data members.</span></span>|  
  
### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="6e6ce-204">\<나타나는 > 복합 유형에: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-204">\<xs:sequence> in a complex type: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-205">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-205">Attribute</span></span>|<span data-ttu-id="6e6ce-206">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-206">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="6e6ce-207">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-207">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="6e6ce-208">1이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6e6ce-208">Must be 1 (default).</span></span>|  
|`minOccurs`|<span data-ttu-id="6e6ce-209">1이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="6e6ce-209">Must be 1 (default).</span></span>|  
  
### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="6e6ce-210">\<나타나는 > 복합 유형에: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6e6ce-210">\<xs:sequence> in a complex type: contents</span></span>  
  
|<span data-ttu-id="6e6ce-211">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-211">Contents</span></span>|<span data-ttu-id="6e6ce-212">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-212">Schema</span></span>|  
|--------------|------------|  
|`element`|<span data-ttu-id="6e6ce-213">각 인스턴스는 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-213">Each instance maps to a data member.</span></span>|  
|`group`|<span data-ttu-id="6e6ce-214">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-214">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="6e6ce-215">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-215">Forbidden.</span></span>|  
|`sequence`|<span data-ttu-id="6e6ce-216">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-216">Forbidden.</span></span>|  
|`any`|<span data-ttu-id="6e6ce-217">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-217">Forbidden.</span></span>|  
|<span data-ttu-id="6e6ce-218">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-218">(empty)</span></span>|<span data-ttu-id="6e6ce-219">데이터 멤버 없이 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-219">Maps to a data contract with no data members.</span></span>|  
  
## <a name="elements--xselement"></a><span data-ttu-id="6e6ce-220">요소 – \<xs: element ></span><span class="sxs-lookup"><span data-stu-id="6e6ce-220">Elements – \<xs:element></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="6e6ce-221">일반 정보</span><span class="sxs-lookup"><span data-stu-id="6e6ce-221">General Information</span></span>  
 <span data-ttu-id="6e6ce-222">`<xs:element>` 는 다음과 같은 컨텍스트에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-222">`<xs:element>` can occur in the following contexts:</span></span>  
  
-   <span data-ttu-id="6e6ce-223">이 요소는 `<xs:sequence>`내에서 발생할 수 있으며, 일반(비컬렉션) 데이터 계약의 데이터 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="6e6ce-224">이 경우 `maxOccurs` 특성은 1이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="6e6ce-225">(값 0이 허용되지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="6e6ce-225">(A value of 0 is not allowed).</span></span>  
  
-   <span data-ttu-id="6e6ce-226">이 요소는 `<xs:sequence>`내에서 발생할 수 있으며, 컬렉션 데이터 계약의 데이터 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="6e6ce-227">이 경우 `maxOccurs` 특성은 1보다 크거나 "unbounded"여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>  
  
-   <span data-ttu-id="6e6ce-228">이 요소는 `<xs:schema>` 내에서 GED(전역 요소 선언)로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="6e6ce-229">\<xs: element > maxoccurs=1 내는 \<나타나는 > (데이터 멤버)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>  
  
|<span data-ttu-id="6e6ce-230">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-230">Attribute</span></span>|<span data-ttu-id="6e6ce-231">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-231">Schema</span></span>|  
|---------------|------------|  
|`ref`|<span data-ttu-id="6e6ce-232">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-232">Forbidden.</span></span>|  
|`name`|<span data-ttu-id="6e6ce-233">지원되며 데이터 멤버 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-233">Supported, maps to the data member name.</span></span>|  
|`type`|<span data-ttu-id="6e6ce-234">지원되며 데이터 멤버 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="6e6ce-235">자세한 내용은 형식/기본 매핑을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="6e6ce-236">지정되지 않고 요소에 익명 형식이 없는 경우 `xs:anyType` 으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|  
|`block`|<span data-ttu-id="6e6ce-237">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-237">Ignored.</span></span>|  
|`default`|<span data-ttu-id="6e6ce-238">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-238">Forbidden.</span></span>|  
|`fixed`|<span data-ttu-id="6e6ce-239">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-239">Forbidden.</span></span>|  
|`form`|<span data-ttu-id="6e6ce-240">정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-240">Must be qualified.</span></span> <span data-ttu-id="6e6ce-241">이 특성은 `elementFormDefault` 에서 `xs:schema`를 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|  
|`id`|<span data-ttu-id="6e6ce-242">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-242">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="6e6ce-243">1</span><span class="sxs-lookup"><span data-stu-id="6e6ce-243">1</span></span>|  
|`minOccurs`|<span data-ttu-id="6e6ce-244">데이터 멤버의 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 속성에 매핑됩니다.`IsRequired` 가 1인 경우 `minOccurs` 는 true입니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|  
|`nillable`|<span data-ttu-id="6e6ce-245">형식 매핑에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-245">Affects type mapping.</span></span> <span data-ttu-id="6e6ce-246">형식/기본 매핑을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-246">See Type/primitive mapping.</span></span>|  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="6e6ce-247">\<xs: element > maxOccurs를 사용 하 여 > 내에서 1을 \<나타나는 > (컬렉션)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>  
  
-   <span data-ttu-id="6e6ce-248"><xref:System.Runtime.Serialization.CollectionDataContractAttribute>에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>  
  
-   <span data-ttu-id="6e6ce-249">컬렉션 형식에서 하나의 xs:element만 xs:sequence 내에 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>  
  
 <span data-ttu-id="6e6ce-250">컬렉션은 다음 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-250">Collections can be of the following types:</span></span>  
  
-   <span data-ttu-id="6e6ce-251">정규 컬렉션(예: 배열)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-251">Regular collections (for example, arrays).</span></span>  
  
-   <span data-ttu-id="6e6ce-252">사전 컬렉션(값을 다른 값에 매핑. 예: <xref:System.Collections.Hashtable>)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>  
  
-   <span data-ttu-id="6e6ce-253">사전과 키/값 쌍 형식의 배열 간 유일한 차이는 생성된 프로그래밍 모델에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="6e6ce-254">지정된 형식이 사전 컬렉션임을 나타내는 데 사용할 수 있는 스키마 주석 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>  
  
 <span data-ttu-id="6e6ce-255">`ref`, `block`, `default`, `fixed`, `form`및 `id` 특성에 대한 규칙이 비컬렉션의 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="6e6ce-256">기타 특성은 다음 표에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-256">Other attributes include those in the following table.</span></span>  
  
|<span data-ttu-id="6e6ce-257">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-257">Attribute</span></span>|<span data-ttu-id="6e6ce-258">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-258">Schema</span></span>|  
|---------------|------------|  
|`name`|<span data-ttu-id="6e6ce-259">지원되며 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> 특성의 `CollectionDataContractAttribute` 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|  
|`type`|<span data-ttu-id="6e6ce-260">지원되며 컬렉션에 저장된 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-260">Supported, maps to the type stored in the collection.</span></span>|  
|`maxOccurs`|<span data-ttu-id="6e6ce-261">1보다 크거나 "unbounded"입니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="6e6ce-262">DC 스키마는 "unbounded"를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-262">The DC schema should use "unbounded".</span></span>|  
|`minOccurs`|<span data-ttu-id="6e6ce-263">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-263">Ignored.</span></span>|  
|`nillable`|<span data-ttu-id="6e6ce-264">형식 매핑에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-264">Affects type mapping.</span></span> <span data-ttu-id="6e6ce-265">이 특성은 사전 컬렉션에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-265">This attribute is ignored for dictionary collections.</span></span>|  
  
### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="6e6ce-266">\<xs: element > 내는 \<xs: schema > 전역 요소 선언</span><span class="sxs-lookup"><span data-stu-id="6e6ce-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>  
  
-   <span data-ttu-id="6e6ce-267">스키마의 형식과 동일한 이름 및 네임스페이스가 있거나 익명 형식을 정의하는 GED(전역 요소 선언)가 형식과 연결된 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>  
  
-   <span data-ttu-id="6e6ce-268">스키마 내보내기: 연결된 GED가 생성된 모든 단순 및 복합 형식에 대해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>  
  
-   <span data-ttu-id="6e6ce-269">Deserialization/serialization: 연결된 GED가 형식에 대해 루트 요소로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>  
  
-   <span data-ttu-id="6e6ce-270">스키마 가져오기: 다음 규칙을 따르는 경우(형식을 정의하지 않는 한) 연결된 GED가 필요 없으며 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>  
  
|<span data-ttu-id="6e6ce-271">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-271">Attribute</span></span>|<span data-ttu-id="6e6ce-272">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-272">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="6e6ce-273">연결된 GED에 대해 false이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-273">Must be false for associated GEDs.</span></span>|  
|`block`|<span data-ttu-id="6e6ce-274">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-274">Forbidden in associated GEDs.</span></span>|  
|`default`|<span data-ttu-id="6e6ce-275">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-275">Forbidden in associated GEDs.</span></span>|  
|`final`|<span data-ttu-id="6e6ce-276">연결된 GED에 대해 false이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-276">Must be false for associated GEDs.</span></span>|  
|`fixed`|<span data-ttu-id="6e6ce-277">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-277">Forbidden in associated GEDs.</span></span>|  
|`id`|<span data-ttu-id="6e6ce-278">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-278">Ignored.</span></span>|  
|`name`|<span data-ttu-id="6e6ce-279">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-279">Supported.</span></span> <span data-ttu-id="6e6ce-280">연결된 GED의 정의를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-280">See the definition of associated GEDs.</span></span>|  
|`nillable`|<span data-ttu-id="6e6ce-281">연결된 GED에 대해 true이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-281">Must be true for associated GEDs.</span></span>|  
|`substitutionGroup`|<span data-ttu-id="6e6ce-282">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-282">Forbidden in associated GEDs.</span></span>|  
|`type`|<span data-ttu-id="6e6ce-283">지원되며 요소에 익명 형식이 포함되어 있는 경우 연결된 GED의 연결된 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|  
  
### <a name="xselement-contents"></a><span data-ttu-id="6e6ce-284">\<xs: element >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6e6ce-284">\<xs:element>: contents</span></span>  
  
|<span data-ttu-id="6e6ce-285">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-285">Contents</span></span>|<span data-ttu-id="6e6ce-286">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-286">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6e6ce-287">지원됩니다.\*</span><span class="sxs-lookup"><span data-stu-id="6e6ce-287">Supported.\*</span></span>|  
|`complexType`|<span data-ttu-id="6e6ce-288">지원됩니다.\*</span><span class="sxs-lookup"><span data-stu-id="6e6ce-288">Supported.\*</span></span>|  
|`unique`|<span data-ttu-id="6e6ce-289">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-289">Ignored.</span></span>|  
|`key`|<span data-ttu-id="6e6ce-290">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-290">Ignored.</span></span>|  
|`keyref`|<span data-ttu-id="6e6ce-291">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-291">Ignored.</span></span>|  
|<span data-ttu-id="6e6ce-292">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-292">(blank)</span></span>|<span data-ttu-id="6e6ce-293">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-293">Supported.</span></span>|  
  
 <span data-ttu-id="6e6ce-294">\* 사용 하는 경우는 `simpleType` 고 `complexType,` 요소 이름에서 파생 된 생성 된 이름을 사용 하 여 명명 된 데이터 계약이 작성 되 고 익명 데이터 계약이 없는 없다는 점을 제외 하면 익명 형식에 대 한 매핑을 익명이 아닌 형식에서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="6e6ce-295">다음 목록에는 익명 형식에 대한 규칙이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-295">The rules for anonymous types are in the following list:</span></span>  
  
-   <span data-ttu-id="6e6ce-296">WCF 구현 세부 정보: 경우는 `xs:element` 이름에 마침표가 없는, 익명 형식은 외부 데이터 계약 형식의 내부 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="6e6ce-297">이름에 마침표가 있는 경우 결과 데이터 계약 형식은 내부 형식이 아닌 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>  
  
-   <span data-ttu-id="6e6ce-298">내부 형식의 생성된 데이터 계약 이름은 외부 형식의 데이터 계약 이름 다음에 마침표, 요소 이름 및 문자열 "Type"이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>  
  
-   <span data-ttu-id="6e6ce-299">이러한 이름을 가진 데이터 계약이 이미 존재하는 경우 이름에 "1", "2", "3" 등을 추가하여 고유 이름으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>  
  
## <a name="simple-types---xssimpletype"></a><span data-ttu-id="6e6ce-300">단순 형식- \<xs:simpleType ></span><span class="sxs-lookup"><span data-stu-id="6e6ce-300">Simple Types - \<xs:simpleType></span></span>  
  
### <a name="xssimpletype-attributes"></a><span data-ttu-id="6e6ce-301">\<xs:simpleType >: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-301">\<xs:simpleType>: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-302">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-302">Attribute</span></span>|<span data-ttu-id="6e6ce-303">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-303">Schema</span></span>|  
|---------------|------------|  
|`final`|<span data-ttu-id="6e6ce-304">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-304">Ignored.</span></span>|  
|`id`|<span data-ttu-id="6e6ce-305">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-305">Ignored.</span></span>|  
|`name`|<span data-ttu-id="6e6ce-306">지원되며 데이터 계약 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-306">Supported, maps to the data contract name.</span></span>|  
  
### <a name="xssimpletype-contents"></a><span data-ttu-id="6e6ce-307">\<xs:simpleType >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6e6ce-307">\<xs:simpleType>: contents</span></span>  
  
|<span data-ttu-id="6e6ce-308">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-308">Contents</span></span>|<span data-ttu-id="6e6ce-309">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-309">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="6e6ce-310">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-310">Supported.</span></span> <span data-ttu-id="6e6ce-311">열거형 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="6e6ce-312">이 특성은 열거형 패턴과 일치하지 않는 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="6e6ce-313">`xs:simpleType` 제한 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-313">See the `xs:simpleType` restrictions section.</span></span>|  
|`list`|<span data-ttu-id="6e6ce-314">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-314">Supported.</span></span> <span data-ttu-id="6e6ce-315">열거형 데이터 계약에 플래그됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="6e6ce-316">`xs:simpleType` 목록 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-316">See the `xs:simpleType` lists section.</span></span>|  
|`union`|<span data-ttu-id="6e6ce-317">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-317">Forbidden.</span></span>|  
  
### <a name="xsrestriction"></a><span data-ttu-id="6e6ce-318">\<xs:restriction></span><span class="sxs-lookup"><span data-stu-id="6e6ce-318">\<xs:restriction></span></span>  
  
-   <span data-ttu-id="6e6ce-319">복합 형식 제한은 base="`xs:anyType`"에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-319">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>  
  
-   <span data-ttu-id="6e6ce-320">`xs:string` 이외의 제한 패싯이 없는 `xs:enumeration` 의 단순 형식 제한은 열거형 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-320">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>  
  
-   <span data-ttu-id="6e6ce-321">다른 모든 단순 형식 제한은 형식이 제한하는 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-321">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="6e6ce-322">예를 들어, `xs:int` 제한은 `xs:int` 자체와 마찬가지로 정수로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-322">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="6e6ce-323">기본 형식 매핑에 대 한 자세한 내용은 형식/기본 매핑을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-323">For more information about primitive type mapping, see Type/primitive mapping.</span></span>  
  
### <a name="xsrestriction-attributes"></a><span data-ttu-id="6e6ce-324">\<xs: restriction >: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-324">\<xs:restriction>: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-325">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-325">Attribute</span></span>|<span data-ttu-id="6e6ce-326">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-326">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="6e6ce-327">지원되는 단순 형식 또는 `xs:anyType`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-327">Must be a supported simple type or `xs:anyType`.</span></span>|  
|`id`|<span data-ttu-id="6e6ce-328">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-328">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="6e6ce-329">\<xs: restriction > 다른 모든 사례: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6e6ce-329">\<xs:restriction> for all other cases: contents</span></span>  
  
|<span data-ttu-id="6e6ce-330">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-330">Contents</span></span>|<span data-ttu-id="6e6ce-331">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-331">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6e6ce-332">있는 경우 지원되는 기본 형식에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-332">If present, must be derived from a supported primitive type.</span></span>|  
|`minExclusive`|<span data-ttu-id="6e6ce-333">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-333">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="6e6ce-334">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-334">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="6e6ce-335">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-335">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="6e6ce-336">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-336">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="6e6ce-337">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-337">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="6e6ce-338">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-338">Ignored.</span></span>|  
|`length`|<span data-ttu-id="6e6ce-339">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-339">Ignored.</span></span>|  
|`minLength`|<span data-ttu-id="6e6ce-340">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-340">Ignored.</span></span>|  
|`maxLength`|<span data-ttu-id="6e6ce-341">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-341">Ignored.</span></span>|  
|`enumeration`|<span data-ttu-id="6e6ce-342">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-342">Ignored.</span></span>|  
|`whiteSpace`|<span data-ttu-id="6e6ce-343">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-343">Ignored.</span></span>|  
|`pattern`|<span data-ttu-id="6e6ce-344">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-344">Ignored.</span></span>|  
|<span data-ttu-id="6e6ce-345">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-345">(blank)</span></span>|<span data-ttu-id="6e6ce-346">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-346">Supported.</span></span>|  
  
## <a name="enumeration"></a><span data-ttu-id="6e6ce-347">열거형</span><span class="sxs-lookup"><span data-stu-id="6e6ce-347">Enumeration</span></span>  
  
### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="6e6ce-348">\<xs: restriction > 열거형에 대 한: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-348">\<xs:restriction> for enumerations: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-349">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-349">Attribute</span></span>|<span data-ttu-id="6e6ce-350">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-350">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="6e6ce-351">있는 경우 `xs:string`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-351">If present, must be `xs:string`.</span></span>|  
|`id`|<span data-ttu-id="6e6ce-352">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-352">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="6e6ce-353">\<xs: restriction > 열거형에 대 한: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6e6ce-353">\<xs:restriction> for enumerations: contents</span></span>  
  
|<span data-ttu-id="6e6ce-354">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-354">Contents</span></span>|<span data-ttu-id="6e6ce-355">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-355">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6e6ce-356">있는 경우 데이터 계약(이 단원)에서 지원하는 열거형 제한이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-356">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|  
|`minExclusive`|<span data-ttu-id="6e6ce-357">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-357">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="6e6ce-358">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-358">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="6e6ce-359">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-359">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="6e6ce-360">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-360">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="6e6ce-361">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-361">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="6e6ce-362">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-362">Ignored.</span></span>|  
|`length`|<span data-ttu-id="6e6ce-363">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-363">Forbidden.</span></span>|  
|`minLength`|<span data-ttu-id="6e6ce-364">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-364">Forbidden.</span></span>|  
|`maxLength`|<span data-ttu-id="6e6ce-365">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-365">Forbidden.</span></span>|  
|`enumeration`|<span data-ttu-id="6e6ce-366">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-366">Supported.</span></span> <span data-ttu-id="6e6ce-367">열거형 "ID"는 무시되고 "value"는 열거형 데이터 계약의 값 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-367">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|  
|`whiteSpace`|<span data-ttu-id="6e6ce-368">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-368">Forbidden.</span></span>|  
|`pattern`|<span data-ttu-id="6e6ce-369">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-369">Forbidden.</span></span>|  
|<span data-ttu-id="6e6ce-370">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="6e6ce-370">(empty)</span></span>|<span data-ttu-id="6e6ce-371">지원되며 비어 있는 열거형 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-371">Supported, maps to empty enumeration type.</span></span>|  
  
 <span data-ttu-id="6e6ce-372">다음 코드는 C# 열거형 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-372">The following code shows a C# enumeration class.</span></span>  
  
```csharp  
public enum MyEnum  
{  
  first = 3,  
  second = 4,  
  third =5  
}  
```  
  
 <span data-ttu-id="6e6ce-373">이 클래스는 `DataContractSerializer`에 의해 다음 스키마에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-373">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="6e6ce-374">열거형 값이 1부터 시작하는 경우 `xs:annotation` 블록이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-374">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>  
  
```xml  
<xs:simpleType name="MyEnum">  
<xs:restriction base="xs:string">  
 <xs:enumeration value="first">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     3  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
 <xs:enumeration value="second">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     4  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
</xs:restriction>  
</xs:simpleType>  
```  
  
### <a name="xslist"></a><span data-ttu-id="6e6ce-375">\<xs:list></span><span class="sxs-lookup"><span data-stu-id="6e6ce-375">\<xs:list></span></span>  
 <span data-ttu-id="6e6ce-376">`DataContractSerializer` 는 `System.FlagsAttribute` 로 표시된 열거형 형식을 `xs:list` 에서 파생된 `xs:string`에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-376">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="6e6ce-377">다른 `xs:list` 변형은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-377">No other `xs:list` variations are supported.</span></span>  
  
### <a name="xslist-attributes"></a><span data-ttu-id="6e6ce-378">\<xs: list >: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-378">\<xs:list>: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-379">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-379">Attribute</span></span>|<span data-ttu-id="6e6ce-380">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-380">Schema</span></span>|  
|---------------|------------|  
|`itemType`|<span data-ttu-id="6e6ce-381">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-381">Forbidden.</span></span>|  
|`id`|<span data-ttu-id="6e6ce-382">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-382">Ignored.</span></span>|  
  
### <a name="xslist-contents"></a><span data-ttu-id="6e6ce-383">\<xs:list>: contents</span><span class="sxs-lookup"><span data-stu-id="6e6ce-383">\<xs:list>: contents</span></span>  
  
|<span data-ttu-id="6e6ce-384">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-384">Contents</span></span>|<span data-ttu-id="6e6ce-385">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-385">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6e6ce-386">`xs:string` 패싯을 사용하는 `xs:enumeration` 에서의 제한이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-386">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|  
  
 <span data-ttu-id="6e6ce-387">열거형 값이 2의 거듭제곱으로 진행되지 않는 경우(플래그의 경우 기본값) 값은 `xs:annotation/xs:appInfo/ser:EnumerationValue` 요소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-387">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>  
  
 <span data-ttu-id="6e6ce-388">예를 들어, 다음 코드는 열거형 형식을 플래그합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-388">For example, the following code flags an enumeration type.</span></span>  
  
```csharp  
[Flags]  
public enum AuthFlags  
{    
  AuthAnonymous = 1,  
  AuthBasic = 2,  
  AuthNTLM = 4,  
  AuthMD5 = 16,  
  AuthWindowsLiveID = 64,  
}  
```  
  
 <span data-ttu-id="6e6ce-389">이 형식이 다음 스키마에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-389">This type maps to the following schema.</span></span>  
  
```xml  
<xs:simpleType name="AuthFlags">  
    <xs:list>  
      <xs:simpleType>  
        <xs:restriction base="xs:string">  
          <xs:enumeration value="AuthAnonymous" />  
          <xs:enumeration value="AuthBasic" />  
          <xs:enumeration value="AuthNTLM" />  
          <xs:enumeration value="AuthMD5">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">16</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
          <xs:enumeration value="AuthWindowsLiveID">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">64</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:list>  
  </xs:simpleType>  
```  
  
## <a name="inheritance"></a><span data-ttu-id="6e6ce-390">상속</span><span class="sxs-lookup"><span data-stu-id="6e6ce-390">Inheritance</span></span>  
  
### <a name="general-rules"></a><span data-ttu-id="6e6ce-391">일반 규칙</span><span class="sxs-lookup"><span data-stu-id="6e6ce-391">General rules</span></span>  
 <span data-ttu-id="6e6ce-392">데이터 계약을 다른 데이터 계약에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-392">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="6e6ce-393">이러한 데이터 계약은 기본 계약에 매핑되고 `<xs:extension>` XML 스키마 구문을 사용하여 확장 형식에 의해 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-393">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>  
  
 <span data-ttu-id="6e6ce-394">데이터 계약을 컬렉션 데이터 계약에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-394">A data contract cannot inherit from a collection data contract.</span></span>  
  
 <span data-ttu-id="6e6ce-395">예를 들어, 다음 코드는 데이터 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-395">For example, the following code is a data contract.</span></span>  
  
```csharp  
[DataContract]  
public class Person  
{  
  [DataMember]  
  public string Name;  
}  
[DataContract]  
public class Employee : Person   
{      
  [DataMember]  
  public int ID;  
}  
```  
  
 <span data-ttu-id="6e6ce-396">이 데이터 계약은 다음 XML 스키마 형식 선언에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-396">This data contract maps to the following XML Schema type declaration.</span></span>  
  
```xml  
<xs:complexType name="Employee">  
 <xs:complexContent mixed="false">  
  <xs:extension base="tns:Person">  
   <xs:sequence>  
    <xs:element minOccurs="0" name="ID" type="xs:int"/>  
   </xs:sequence>  
  </xs:extension>  
 </xs:complexContent>  
</xs:complexType>  
<xs:complexType name="Person">  
 <xs:sequence>  
  <xs:element minOccurs="0" name="Name"   
    nillable="true" type="xs:string"/>  
 </xs:sequence>  
</xs:complexType>  
```  
  
### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="6e6ce-397">\<xs:complexContent >: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-397">\<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-398">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-398">Attribute</span></span>|<span data-ttu-id="6e6ce-399">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-399">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="6e6ce-400">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-400">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="6e6ce-401">false이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-401">Must be false.</span></span>|  
  
### <a name="xscomplexcontent-contents"></a><span data-ttu-id="6e6ce-402">\<xs:complexContent >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6e6ce-402">\<xs:complexContent>: contents</span></span>  
  
|<span data-ttu-id="6e6ce-403">목차</span><span class="sxs-lookup"><span data-stu-id="6e6ce-403">Contents</span></span>|<span data-ttu-id="6e6ce-404">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-404">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="6e6ce-405">base="`xs:anyType`"인 경우를 제외하고 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-405">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="6e6ce-406">후자는 `xs:restriction` 의 콘텐츠를 `xs:complexContent`컨테이너 바로 아래에 배치하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-406">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|  
|`extension`|<span data-ttu-id="6e6ce-407">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-407">Supported.</span></span> <span data-ttu-id="6e6ce-408">데이터 계약 상속에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-408">Maps to data contract inheritance.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="6e6ce-409">\<xs: extension >에서 \<xs:complexContent >: 특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-409">\<xs:extension> in \<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="6e6ce-410">특성</span><span class="sxs-lookup"><span data-stu-id="6e6ce-410">Attribute</span></span>|<span data-ttu-id="6e6ce-411">스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-411">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="6e6ce-412">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-412">Ignored.</span></span>|  
|`base`|<span data-ttu-id="6e6ce-413">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-413">Supported.</span></span> <span data-ttu-id="6e6ce-414">이 형식이 상속되는 기본 데이터 계약 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-414">Maps to the base data contract type that this type inherits from.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="6e6ce-415">\<xs: extension >에서 \<xs:complexContent >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6e6ce-415">\<xs:extension> in \<xs:complexContent>: contents</span></span>  
 <span data-ttu-id="6e6ce-416">규칙은 `<xs:complexType>` 콘텐츠에서와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-416">The rules are the same as for `<xs:complexType>` contents.</span></span>  
  
 <span data-ttu-id="6e6ce-417">`<xs:sequence>` 를 제공하는 경우 멤버 요소가 파생된 데이터 계약에 있는 추가 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-417">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>  
  
 <span data-ttu-id="6e6ce-418">파생된 형식에 기본 형식의 요소와 동일한 이름을 가진 요소가 포함된 경우 중복 요소 선언이 고유하게 생성된 이름을 가진 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-418">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="6e6ce-419">고유한 이름을 찾을 때까지 양의 정수가 데이터 멤버 이름("member1", "member2" 등)에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-419">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="6e6ce-420">반대의 경우는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-420">Conversely:</span></span>  
  
-   <span data-ttu-id="6e6ce-421">파생된 데이터 계약에 기본 데이터 계약의 데이터 멤버와 동일한 이름을 가진 데이터 멤버가 있는 경우 `DataContractSerializer` 는 이 해당 요소를 파생된 형식으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-421">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>  
  
-   <span data-ttu-id="6e6ce-422">파생된 데이터 계약에 기본 데이터 계약의 데이터 멤버와 동일한 이름을 가졌지만 형식은 다른 데이터 멤버가 포함된 경우 `DataContractSerializer` 는 기본 형식 및 파생된 형식 선언 모두에서 `xs:anyType` 형식의 요소와 함께 스키마를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-422">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="6e6ce-423">원래 형식 이름은 `xs:annotations/xs:appInfo/ser:ActualType/@Name`에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-423">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>  
  
 <span data-ttu-id="6e6ce-424">이 두 변형을 통해 스키마는 모호한 콘텐츠 모델을 가질 수 있으며 각 데이터 멤버의 순서에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-424">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>  
  
## <a name="typeprimitive-mapping"></a><span data-ttu-id="6e6ce-425">형식/기본 매핑</span><span class="sxs-lookup"><span data-stu-id="6e6ce-425">Type/primitive mapping</span></span>  
 <span data-ttu-id="6e6ce-426">`DataContractSerializer` 는 XML 스키마 기본 형식에 대해 다음 매핑을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-426">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>  
  
|<span data-ttu-id="6e6ce-427">XSD 형식</span><span class="sxs-lookup"><span data-stu-id="6e6ce-427">XSD type</span></span>|<span data-ttu-id="6e6ce-428">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="6e6ce-428">.NET type</span></span>|  
|--------------|---------------|  
|`anyType`|<span data-ttu-id="6e6ce-429"><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-429"><xref:System.Object>.</span></span>|  
|`anySimpleType`|<span data-ttu-id="6e6ce-430"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-430"><xref:System.String>.</span></span>|  
|`duration`|<span data-ttu-id="6e6ce-431"><xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-431"><xref:System.TimeSpan>.</span></span>|  
|`dateTime`|<span data-ttu-id="6e6ce-432"><xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-432"><xref:System.DateTime>.</span></span>|  
|`dateTimeOffset`|<span data-ttu-id="6e6ce-433">오프셋의 경우<xref:System.DateTime> 및 <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="6e6ce-433"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="6e6ce-434">아래 DateTimeOffset Serialization을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-434">See DateTimeOffset Serialization below.</span></span>|  
|`time`|<span data-ttu-id="6e6ce-435"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-435"><xref:System.String>.</span></span>|  
|`date`|<span data-ttu-id="6e6ce-436"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-436"><xref:System.String>.</span></span>|  
|`gYearMonth`|<span data-ttu-id="6e6ce-437"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-437"><xref:System.String>.</span></span>|  
|`gYear`|<span data-ttu-id="6e6ce-438"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-438"><xref:System.String>.</span></span>|  
|`gMonthDay`|<span data-ttu-id="6e6ce-439"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-439"><xref:System.String>.</span></span>|  
|`gDay`|<span data-ttu-id="6e6ce-440"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-440"><xref:System.String>.</span></span>|  
|`gMonth`|<span data-ttu-id="6e6ce-441"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-441"><xref:System.String>.</span></span>|  
|`boolean`|<xref:System.Boolean>|  
|`base64Binary`|<span data-ttu-id="6e6ce-442"><xref:System.Byte> 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-442"><xref:System.Byte> array.</span></span>|  
|`hexBinary`|<span data-ttu-id="6e6ce-443"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-443"><xref:System.String>.</span></span>|  
|`float`|<span data-ttu-id="6e6ce-444"><xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-444"><xref:System.Single>.</span></span>|  
|`double`|<span data-ttu-id="6e6ce-445"><xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-445"><xref:System.Double>.</span></span>|  
|`anyURI`|<span data-ttu-id="6e6ce-446"><xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-446"><xref:System.Uri>.</span></span>|  
|`QName`|<span data-ttu-id="6e6ce-447"><xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-447"><xref:System.Xml.XmlQualifiedName>.</span></span>|  
|`string`|<span data-ttu-id="6e6ce-448"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-448"><xref:System.String>.</span></span>|  
|`normalizedString`|<span data-ttu-id="6e6ce-449"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-449"><xref:System.String>.</span></span>|  
|`token`|<span data-ttu-id="6e6ce-450"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-450"><xref:System.String>.</span></span>|  
|`language`|<span data-ttu-id="6e6ce-451"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-451"><xref:System.String>.</span></span>|  
|`Name`|<span data-ttu-id="6e6ce-452"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-452"><xref:System.String>.</span></span>|  
|`NCName`|<span data-ttu-id="6e6ce-453"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-453"><xref:System.String>.</span></span>|  
|`ID`|<span data-ttu-id="6e6ce-454"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-454"><xref:System.String>.</span></span>|  
|`IDREF`|<span data-ttu-id="6e6ce-455"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-455"><xref:System.String>.</span></span>|  
|`IDREFS`|<span data-ttu-id="6e6ce-456"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-456"><xref:System.String>.</span></span>|  
|`ENTITY`|<span data-ttu-id="6e6ce-457"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-457"><xref:System.String>.</span></span>|  
|`ENTITIES`|<span data-ttu-id="6e6ce-458"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-458"><xref:System.String>.</span></span>|  
|`NMTOKEN`|<span data-ttu-id="6e6ce-459"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-459"><xref:System.String>.</span></span>|  
|`NMTOKENS`|<span data-ttu-id="6e6ce-460"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-460"><xref:System.String>.</span></span>|  
|`decimal`|<span data-ttu-id="6e6ce-461"><xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-461"><xref:System.Decimal>.</span></span>|  
|`integer`|<span data-ttu-id="6e6ce-462"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-462"><xref:System.Int64>.</span></span>|  
|`nonPositiveInteger`|<span data-ttu-id="6e6ce-463"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-463"><xref:System.Int64>.</span></span>|  
|`negativeInteger`|<span data-ttu-id="6e6ce-464"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-464"><xref:System.Int64>.</span></span>|  
|`long`|<span data-ttu-id="6e6ce-465"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-465"><xref:System.Int64>.</span></span>|  
|`int`|<span data-ttu-id="6e6ce-466"><xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-466"><xref:System.Int32>.</span></span>|  
|`short`|<span data-ttu-id="6e6ce-467"><xref:System.Int16>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-467"><xref:System.Int16>.</span></span>|  
|`Byte`|<span data-ttu-id="6e6ce-468"><xref:System.SByte>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-468"><xref:System.SByte>.</span></span>|  
|`nonNegativeInteger`|<span data-ttu-id="6e6ce-469"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-469"><xref:System.Int64>.</span></span>|  
|`unsignedLong`|<span data-ttu-id="6e6ce-470"><xref:System.UInt64>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-470"><xref:System.UInt64>.</span></span>|  
|`unsignedInt`|<span data-ttu-id="6e6ce-471"><xref:System.UInt32>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-471"><xref:System.UInt32>.</span></span>|  
|`unsignedShort`|<span data-ttu-id="6e6ce-472"><xref:System.UInt16>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-472"><xref:System.UInt16>.</span></span>|  
|`unsignedByte`|<span data-ttu-id="6e6ce-473"><xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-473"><xref:System.Byte>.</span></span>|  
|`positiveInteger`|<span data-ttu-id="6e6ce-474"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-474"><xref:System.Int64>.</span></span>|  
  
## <a name="iserializable-types-mapping"></a><span data-ttu-id="6e6ce-475">ISerializable 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="6e6ce-475">ISerializable types mapping</span></span>  
 <span data-ttu-id="6e6ce-476">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 은 <xref:System.Runtime.Serialization.ISerializable> 버전 1.0에서 지속성이나 데이터 전송을 위해 개체를 serialize하는 일반 메커니즘으로 새로 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-476">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="6e6ce-477">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 을 구현하고 애플리케이션 간에 전달할 수 있는 다양한 `ISerializable` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-477">There are many [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="6e6ce-478"><xref:System.Runtime.Serialization.DataContractSerializer> 는 기본적으로 `ISerializable` 클래스에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-478"><xref:System.Runtime.Serialization.DataContractSerializer> naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="6e6ce-479">`DataContractSerializer` 는 형식의 QName(정규화된 이름)에 의해서만 달라지는 효율적인 속성 컬렉션인 `ISerializable` 구현 스키마 형식을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-479">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="6e6ce-480">예를 들어, 합니다 `DataContractSerializer` 매핑합니다 <xref:System.Exception> 된 다음 XSD 형식에 `http://schemas.datacontract.org/2004/07/System` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-480">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>  
  
```xml  
<xs:complexType name="Exception">  
 <xs:sequence>  
  <xs:any minOccurs="0" maxOccurs="unbounded"   
      namespace="##local" processContents="skip"/>  
 </xs:sequence>  
 <xs:attribute ref="ser:FactoryType"/>  
</xs:complexType>  
```  
  
 <span data-ttu-id="6e6ce-481">데이터 계약 Serialization 스키마에서 선언한 선택적 특성 `ser:FactoryType` 은 형식을 deserialize할 수 있는 팩터리 클래스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-481">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="6e6ce-482">팩터리 클래스는 사용 중인 `DataContractSerializer` 인스턴스의 알려진 형식 컬렉션의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-482">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="6e6ce-483">알려진된 형식에 대 한 자세한 내용은 참조 하세요. [데이터 계약 알려진 형식을](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-483">For more information about known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="datacontract-serialization-schema"></a><span data-ttu-id="6e6ce-484">DataContract Serialization 스키마</span><span class="sxs-lookup"><span data-stu-id="6e6ce-484">DataContract Serialization Schema</span></span>  
 <span data-ttu-id="6e6ce-485">`DataContractSerializer` 에서 내보낸 여러 스키마는 다음과 같은 특별한 데이터 계약 Serialization 네임스페이스의 형식, 요소 및 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-485">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>  
  
 `http://schemas.microsoft.com/2003/10/Serialization`
  
 <span data-ttu-id="6e6ce-486">다음은 전체 데이터 계약 Serialization 스키마 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-486">The following is a complete Data Contract Serialization schema declaration.</span></span>  
  
```xml  
<xs:schema attributeFormDefault="qualified"          
   elementFormDefault="qualified"        
   targetNamespace =   
    "http://schemas.microsoft.com/2003/10/Serialization/"   
   xmlns:xs="http://www.w3.org/2001/XMLSchema"        
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">  
  
 <!-- Top-level elements for primitive types. -->  
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>  
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>  
 <xs:element name="base64Binary"  
       nillable="true" type="xs:base64Binary"/>  
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>  
 <xs:element name="byte" nillable="true" type="xs:byte"/>  
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>  
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>  
 <xs:element name="double" nillable="true" type="xs:double"/>  
 <xs:element name="float" nillable="true" type="xs:float"/>  
 <xs:element name="int" nillable="true" type="xs:int"/>  
 <xs:element name="long" nillable="true" type="xs:long"/>  
 <xs:element name="QName" nillable="true" type="xs:QName"/>  
 <xs:element name="short" nillable="true" type="xs:short"/>  
 <xs:element name="string" nillable="true" type="xs:string"/>  
 <xs:element name="unsignedByte"  
       nillable="true" type="xs:unsignedByte"/>  
 <xs:element name="unsignedInt"  
       nillable="true" type="xs:unsignedInt"/>  
 <xs:element name="unsignedLong"  
       nillable="true" type="xs:unsignedLong"/>  
 <xs:element name="unsignedShort"  
       nillable="true" type="xs:unsignedShort"/>  
  
 <!-- Primitive types introduced for certain .NET simple types. -->  
 <xs:element name="char" nillable="true" type="tns:char"/>  
 <xs:simpleType name="char">  
  <xs:restriction base="xs:int"/>  
 </xs:simpleType>  
  
 <!-- xs:duration is restricted to an ordered value space,  
    to map to System.TimeSpan -->  
 <xs:element name="duration" nillable="true" type="tns:duration"/>  
 <xs:simpleType name="duration">  
  <xs:restriction base="xs:duration">  
   <xs:pattern   
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>  
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>  
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <xs:element name="guid" nillable="true" type="tns:guid"/>  
 <xs:simpleType name="guid">  
  <xs:restriction base="xs:string">  
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <!-- This is used for schemas exported from ISerializable type. -->  
 <xs:attribute name="FactoryType" type="xs:QName"/>  
</xs:schema>  
```  
  
 <span data-ttu-id="6e6ce-487">다음 항목에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-487">The following should be noted:</span></span>  
  
-   <span data-ttu-id="6e6ce-488">`ser:char` 은 <xref:System.Char>형식의 유니코드 문자를 표시하기 위해 도입됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-488">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>  
  
-   <span data-ttu-id="6e6ce-489">`valuespace` 의 `xs:duration` 는 <xref:System.TimeSpan>에 매핑될 수 있도록 정렬된 집합으로 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-489">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>  
  
-   <span data-ttu-id="6e6ce-490">`FactoryType` 은 <xref:System.Runtime.Serialization.ISerializable>에서 파생된 형식에서 내보낸 스키마에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-490">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="6e6ce-491">DataContract가 아닌 스키마 가져오기</span><span class="sxs-lookup"><span data-stu-id="6e6ce-491">Importing non-DataContract schemas</span></span>  
 <span data-ttu-id="6e6ce-492">`DataContractSerializer` 에는 `ImportXmlTypes` XSD 프로필을 준수하지 않는 스키마를 가져올 수 있는 `DataContractSerializer` 옵션이 포함되어 있습니다. <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> 속성을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-492">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="6e6ce-493">이 옵션을 `true` 로 설정하면 맞지 않는 스키마 형식을 허용하고, 이러한 형식을 다음 구현에 매핑하고, <xref:System.Xml.Serialization.IXmlSerializable> 이 <xref:System.Xml.XmlNode> 의 배열을 래핑할 수 있습니다(클래스 이름만 다름).</span><span class="sxs-lookup"><span data-stu-id="6e6ce-493">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>  
  
```csharp  
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]  
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]  
public partial class Person : object, IXmlSerializable  
{    
  private XmlNode[] nodesField;    
  private static XmlQualifiedName typeName =   
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");    
  public XmlNode[] Nodes  
  {  
    get {return this.nodesField;}  
    set {this.nodesField = value;}  
  }    
  public void ReadXml(XmlReader reader)  
  {  
    this.nodesField = XmlSerializableServices.ReadNodes(reader);  
  }    
  public void WriteXml(XmlWriter writer)  
  {  
    XmlSerializableServices.WriteNodes(writer, this.Nodes);  
  }    
  public System.Xml.Schema.XmlSchema GetSchema()  
  {  
    return null;  
  }    
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)  
  {  
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);  
    return typeName;  
  }  
}  
```  
  
## <a name="datetimeoffset-serialization"></a><span data-ttu-id="6e6ce-494">DateTimeOffset Serialization</span><span class="sxs-lookup"><span data-stu-id="6e6ce-494">DateTimeOffset Serialization</span></span>  
 <span data-ttu-id="6e6ce-495"><xref:System.DateTimeOffset> 은 기본 형식으로 취급되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-495">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="6e6ce-496">대신 두 부분으로 구성된 복합 요소로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-496">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="6e6ce-497">첫 번째 부분은 날짜/시간을 표시하고 두 번째 부분은 날짜/시간의 오프셋을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-497">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="6e6ce-498">다음 코드에서는 serialize된 DateTimeOffset 값의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-498">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>  
  
```xml  
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">  
  <DateTime i:type="b:dateTime" xmlns=""   
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00    
  </DateTime>   
  <OffsetMinutes i:type="b:short" xmlns=""   
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480  
   </OffsetMinutes>   
</OffSet>  
```  
  
 <span data-ttu-id="6e6ce-499">스키마는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e6ce-499">The schema is as follows.</span></span>  
  
```xml  
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">  
   <xs:complexType name="DateTimeOffset">  
      <xs:sequence minOccurs="1" maxOccurs="1">  
         <xs:element name="DateTime" type="xs:dateTime"  
         minOccurs="1" maxOccurs="1" />  
         <xs:element name="OffsetMinutes" type="xs:short"  
         minOccurs="1" maxOccurs="1" />  
      </xs:sequence>  
   </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e6ce-500">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e6ce-500">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="6e6ce-501">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="6e6ce-501">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
