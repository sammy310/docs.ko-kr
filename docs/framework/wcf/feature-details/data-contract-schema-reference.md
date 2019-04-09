---
title: 데이터 계약 스키마 참조
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: a4ddaaea2133a8adf5271628f442644194a7f453
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131939"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="d2c2e-102">데이터 계약 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="d2c2e-102">Data Contract Schema Reference</span></span>
<span data-ttu-id="d2c2e-103">이 항목에서는 XML serialization에 대한 CLR(공용 언어 런타임) 형식을 설명하기 위해 <xref:System.Runtime.Serialization.DataContractSerializer> 에서 사용하는 XSD(XML 스키마) 하위 집합에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>  
  
## <a name="datacontractserializer-mappings"></a><span data-ttu-id="d2c2e-104">DataContractSerializer 매핑</span><span class="sxs-lookup"><span data-stu-id="d2c2e-104">DataContractSerializer Mappings</span></span>  
 <span data-ttu-id="d2c2e-105">합니다 `DataContractSerializer` 메타 데이터 끝점을 사용 하는 Windows Communication Foundation (WCF) 서비스에서 메타 데이터를 내보낼 때 CLR 형식을 XSD에 매핑합니다 또는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="d2c2e-106">자세한 내용은 [데이터 계약 Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-106">For more information, see [Data Contract Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).</span></span>  
  
 <span data-ttu-id="d2c2e-107">또한 WSDL(웹 서비스 기술 언어) 또는 XSD 문서에 액세스하여 서비스 또는 클라이언트에 대한 데이터 계약을 생성하기 위해 Svcutil.exe를 사용하는 경우 `DataContractSerializer` 는 XSD를 CLR 형식에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>  
  
 <span data-ttu-id="d2c2e-108">이 문서에 명시된 요구 사항을 준수하는 XML 스키마 인스턴스만 `DataContractSerializer`를 사용하여 CLR 형식에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>  
  
### <a name="support-levels"></a><span data-ttu-id="d2c2e-109">지원 수준</span><span class="sxs-lookup"><span data-stu-id="d2c2e-109">Support Levels</span></span>  
 <span data-ttu-id="d2c2e-110">`DataContractSerializer` 는 지정된 XML 스키마 기능에 대해 다음과 같은 수준의 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>  
  
-   <span data-ttu-id="d2c2e-111">**지원**.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-111">**Supported**.</span></span> <span data-ttu-id="d2c2e-112">`DataContractSerializer`를 사용하여 이 기능에서 CLR 형식 또는 특성(또는 둘 다)으로 명시적 매핑이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>  
  
-   <span data-ttu-id="d2c2e-113">**무시**.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-113">**Ignored**.</span></span> <span data-ttu-id="d2c2e-114">`DataContractSerializer`가 가져온 스키마에 이 기능을 사용할 수 있지만 코드 생성에 영향을 주지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>  
  
-   <span data-ttu-id="d2c2e-115">**사용할 수 없음**.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-115">**Forbidden**.</span></span> <span data-ttu-id="d2c2e-116">`DataContractSerializer` 는 이 기능을 사용하여 스키마 가져오기 작업을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="d2c2e-117">예를 들어, 이러한 기능을 사용하는 스키마를 통해 WSDL에 액세스하는 경우 Svcutil.exe는 대신 <xref:System.Xml.Serialization.XmlSerializer> 로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="d2c2e-118">이 기능은 기본적으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-118">This is by default.</span></span>  
  
## <a name="general-information"></a><span data-ttu-id="d2c2e-119">일반 정보</span><span class="sxs-lookup"><span data-stu-id="d2c2e-119">General Information</span></span>  
  
-   <span data-ttu-id="d2c2e-120">스키마 네임스페이스에 대해서는 [XML Schema](https://go.microsoft.com/fwlink/?LinkId=95475)에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-120">The schema namespace is described at [XML Schema](https://go.microsoft.com/fwlink/?LinkId=95475).</span></span> <span data-ttu-id="d2c2e-121">이 문서에서는 접두사 "xs"가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-121">The prefix "xs" is used in this document.</span></span>  
  
-   <span data-ttu-id="d2c2e-122">스키마 네임스페이스가 아닌 네임스페이스를 가진 특성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-122">Any attributes with a non-schema namespace are ignored.</span></span>  
  
-   <span data-ttu-id="d2c2e-123">이 문서에서 설명한 주석을 제외한 모든 주석이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-123">Any annotations (except for those described in this document) are ignored.</span></span>  
  
### <a name="xsschema-attributes"></a><span data-ttu-id="d2c2e-124">\<xs: schema >: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-124">\<xs:schema>: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-125">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-125">Attribute</span></span>|<span data-ttu-id="d2c2e-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="d2c2e-126">DataContract</span></span>|  
|---------------|------------------|  
|`attributeFormDefault`|<span data-ttu-id="d2c2e-127">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-127">Ignored.</span></span>|  
|`blockDefault`|<span data-ttu-id="d2c2e-128">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-128">Ignored.</span></span>|  
|`elementFormDefault`|<span data-ttu-id="d2c2e-129">정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-129">Must be qualified.</span></span> <span data-ttu-id="d2c2e-130">`DataContractSerializer`에서 스키마를 지원하려면 모든 요소가 정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="d2c2e-131">설정 하거나이 작업을 수행할 수 있습니다 xs:schema/@elementFormDefault 을 "qualified" 또는 설정 하 여 xs:element/@form 각 개별 요소 선언에 "qualified"로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|  
|`finalDefault`|<span data-ttu-id="d2c2e-132">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-132">Ignored.</span></span>|  
|`Id`|<span data-ttu-id="d2c2e-133">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-133">Ignored.</span></span>|  
|`targetNamespace`|<span data-ttu-id="d2c2e-134">지원되며 데이터 계약 네임스페이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="d2c2e-135">이 특성을 지정하지 않으면 빈 네임스페이스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="d2c2e-136">예약된 된 네임 스페이스를 사용할 수 없습니다. `http://schemas.microsoft.com/2003/10/Serialization/`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|  
|`version`|<span data-ttu-id="d2c2e-137">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-137">Ignored.</span></span>|  
  
### <a name="xsschema-contents"></a><span data-ttu-id="d2c2e-138">\<xs:schema>: contents</span><span class="sxs-lookup"><span data-stu-id="d2c2e-138">\<xs:schema>: contents</span></span>  
  
|<span data-ttu-id="d2c2e-139">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-139">Contents</span></span>|<span data-ttu-id="d2c2e-140">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-140">Schema</span></span>|  
|--------------|------------|  
|`include`|<span data-ttu-id="d2c2e-141">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-141">Supported.</span></span> `DataContractSerializer` <span data-ttu-id="d2c2e-142">x를 지원 합니다: 포함 및 xs: import입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-142">supports xs:include and xs:import.</span></span> <span data-ttu-id="d2c2e-143">그러나 Svcutil.exe는 로컬 파일에서 메타데이터를 로드할 때 다음 `xs:include/@schemaLocation` 및 `xs:import/@location` 참조를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="d2c2e-144">이러한 경우 스키마 파일 목록은 `include` 가 아닌 out-of-band 메커니즘을 통해 전달해야 합니다. `include`된 스키마 문서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`redefine`|<span data-ttu-id="d2c2e-145">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-145">Forbidden.</span></span> <span data-ttu-id="d2c2e-146">보안상의 이유로 `xs:redefine` 는 `DataContractSerializer` 을 사용할 수 없습니다. `x:redefine` 을 사용하려면 `schemaLocation` 을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="d2c2e-147">상황에 따라 DataContract를 사용하는 Svcutil.exe는 `schemaLocation`사용을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|  
|`import`|<span data-ttu-id="d2c2e-148">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-148">Supported.</span></span> `DataContractSerializer` <span data-ttu-id="d2c2e-149">지원 `xs:include` 고 `xs:import`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-149">supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="d2c2e-150">그러나 Svcutil.exe는 로컬 파일에서 메타데이터를 로드할 때 다음 `xs:include/@schemaLocation` 및 `xs:import/@location` 참조를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="d2c2e-151">이러한 경우 스키마 파일 목록은 `include` 가 아닌 out-of-band 메커니즘을 통해 전달해야 합니다. `include`된 스키마 문서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`simpleType`|<span data-ttu-id="d2c2e-152">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-152">Supported.</span></span> <span data-ttu-id="d2c2e-153">`xs:simpleType` 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-153">See the `xs:simpleType` section.</span></span>|  
|`complexType`|<span data-ttu-id="d2c2e-154">지원되며 데이터 계약으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="d2c2e-155">`xs:complexType` 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-155">See the `xs:complexType` section.</span></span>|  
|`group`|<span data-ttu-id="d2c2e-156">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-156">Ignored.</span></span> `DataContractSerializer` <span data-ttu-id="d2c2e-157">사용을 지원 하지 않습니다 `xs:group`하십시오 `xs:attributeGroup`, 및 `xs:attribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-157">does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="d2c2e-158">이러한 선언은 `xs:schema`의 자식으로 무시되며 `complexType` 또는 기타 지원되는 구문 내에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`attributeGroup`|<span data-ttu-id="d2c2e-159">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-159">Ignored.</span></span> `DataContractSerializer` <span data-ttu-id="d2c2e-160">사용을 지원 하지 않습니다 `xs:group`하십시오 `xs:attributeGroup`, 및 `xs:attribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-160">does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="d2c2e-161">이러한 선언은 `xs:schema`의 자식으로 무시되며 `complexType` 또는 기타 지원되는 구문 내에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`element`|<span data-ttu-id="d2c2e-162">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-162">Supported.</span></span> <span data-ttu-id="d2c2e-163">GED(전역 요소 선언)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-163">See Global Element Declaration (GED).</span></span>|  
|`attribute`|<span data-ttu-id="d2c2e-164">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-164">Ignored.</span></span> `DataContractSerializer` <span data-ttu-id="d2c2e-165">사용을 지원 하지 않습니다 `xs:group`하십시오 `xs:attributeGroup`, 및 `xs:attribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-165">does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="d2c2e-166">이러한 선언은 `xs:schema`의 자식으로 무시되며 `complexType` 또는 기타 지원되는 구문 내에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`notation`|<span data-ttu-id="d2c2e-167">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-167">Ignored.</span></span>|  
  
## <a name="complex-types--xscomplextype"></a><span data-ttu-id="d2c2e-168">복합 형식 – \<xs:complexType ></span><span class="sxs-lookup"><span data-stu-id="d2c2e-168">Complex Types – \<xs:complexType></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="d2c2e-169">일반 정보</span><span class="sxs-lookup"><span data-stu-id="d2c2e-169">General Information</span></span>  
 <span data-ttu-id="d2c2e-170">각 복합 형식 \<xs:complexType > 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>  
  
### <a name="xscomplextype-attributes"></a><span data-ttu-id="d2c2e-171">\<xs:complexType >: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-171">\<xs:complexType>: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-172">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-172">Attribute</span></span>|<span data-ttu-id="d2c2e-173">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-173">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="d2c2e-174">false이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="d2c2e-174">Must be false (default).</span></span>|  
|`block`|<span data-ttu-id="d2c2e-175">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-175">Forbidden.</span></span>|  
|`final`|<span data-ttu-id="d2c2e-176">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-176">Ignored.</span></span>|  
|`id`|<span data-ttu-id="d2c2e-177">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-177">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="d2c2e-178">false이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="d2c2e-178">Must be false (default).</span></span>|  
|`name`|<span data-ttu-id="d2c2e-179">지원되며 데이터 계약 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="d2c2e-180">이름에 마침표가 있는 경우 형식을 내부 형식에 매핑하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="d2c2e-181">예를 들어, `A.B` 라는 복합 형식은 `A`라는 데이터 계약 이름을 가진 형식의 내부 형식인 데이터 계약 형식으로 매핑되지만 이러한 데이터 계약 형식이 있는 경우에만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="d2c2e-182">둘 이상의 중첩 수준이 가능합니다. 예를 들어, `A.B.C` 가 내부 형식일 수 있지만 `A` 및 `A.B` 가 모두 있는 경우에만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|  
  
### <a name="xscomplextype-contents"></a><span data-ttu-id="d2c2e-183">\<xs:complexType>: contents</span><span class="sxs-lookup"><span data-stu-id="d2c2e-183">\<xs:complexType>: contents</span></span>  
  
|<span data-ttu-id="d2c2e-184">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-184">Contents</span></span>|<span data-ttu-id="d2c2e-185">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-185">Schema</span></span>|  
|--------------|------------|  
|`simpleContent`|<span data-ttu-id="d2c2e-186">확장을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="d2c2e-187">제한은 `anySimpleType`에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-187">Restriction is allowed only from `anySimpleType`.</span></span>|  
|`complexContent`|<span data-ttu-id="d2c2e-188">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-188">Supported.</span></span> <span data-ttu-id="d2c2e-189">"상속"을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-189">See "Inheritance".</span></span>|  
|`group`|<span data-ttu-id="d2c2e-190">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-190">Forbidden.</span></span>|  
|`all`|<span data-ttu-id="d2c2e-191">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-191">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="d2c2e-192">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d2c2e-192">Forbidden</span></span>|  
|`sequence`|<span data-ttu-id="d2c2e-193">지원되며 데이터 계약의 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-193">Supported, maps to data members of a data contract.</span></span>|  
|`attribute`|<span data-ttu-id="d2c2e-194">한 가지 예외를 포함하여 use="prohibited"인 경우에도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="d2c2e-195">표준 Serialization 스키마 네임스페이스에서 선택적 특성만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="d2c2e-196">이러한 특성은 데이터 계약 프로그래밍 모델의 데이터 멤버에 매핑되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="d2c2e-197">현재 이러한 하나의 특성만 의미가 있으며, 여기에 대해서는 ISerializable 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="d2c2e-198">다른 특성은 모두 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-198">All others are ignored.</span></span>|  
|`attributeGroup`|<span data-ttu-id="d2c2e-199">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-199">Forbidden.</span></span> <span data-ttu-id="d2c2e-200">WCF v1 릴리스에서 `DataContractSerializer` 존재를 무시 `attributeGroup` 내에서 `xs:complexType`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|  
|`anyAttribute`|<span data-ttu-id="d2c2e-201">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-201">Forbidden.</span></span>|  
|<span data-ttu-id="d2c2e-202">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-202">(empty)</span></span>|<span data-ttu-id="d2c2e-203">데이터 멤버 없이 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-203">Maps to a data contract with no data members.</span></span>|  
  
### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="d2c2e-204">\<나타나는 > 복합 유형에: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-204">\<xs:sequence> in a complex type: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-205">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-205">Attribute</span></span>|<span data-ttu-id="d2c2e-206">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-206">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="d2c2e-207">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-207">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="d2c2e-208">1이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="d2c2e-208">Must be 1 (default).</span></span>|  
|`minOccurs`|<span data-ttu-id="d2c2e-209">1이어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="d2c2e-209">Must be 1 (default).</span></span>|  
  
### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="d2c2e-210">\<나타나는 > 복합 유형에: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d2c2e-210">\<xs:sequence> in a complex type: contents</span></span>  
  
|<span data-ttu-id="d2c2e-211">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-211">Contents</span></span>|<span data-ttu-id="d2c2e-212">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-212">Schema</span></span>|  
|--------------|------------|  
|`element`|<span data-ttu-id="d2c2e-213">각 인스턴스는 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-213">Each instance maps to a data member.</span></span>|  
|`group`|<span data-ttu-id="d2c2e-214">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-214">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="d2c2e-215">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-215">Forbidden.</span></span>|  
|`sequence`|<span data-ttu-id="d2c2e-216">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-216">Forbidden.</span></span>|  
|`any`|<span data-ttu-id="d2c2e-217">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-217">Forbidden.</span></span>|  
|<span data-ttu-id="d2c2e-218">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-218">(empty)</span></span>|<span data-ttu-id="d2c2e-219">데이터 멤버 없이 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-219">Maps to a data contract with no data members.</span></span>|  
  
## <a name="elements--xselement"></a><span data-ttu-id="d2c2e-220">요소 – \<xs: element ></span><span class="sxs-lookup"><span data-stu-id="d2c2e-220">Elements – \<xs:element></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="d2c2e-221">일반 정보</span><span class="sxs-lookup"><span data-stu-id="d2c2e-221">General Information</span></span>  
 `<xs:element>` <span data-ttu-id="d2c2e-222">다음 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-222">can occur in the following contexts:</span></span>  
  
-   <span data-ttu-id="d2c2e-223">이 요소는 `<xs:sequence>`내에서 발생할 수 있으며, 일반(비컬렉션) 데이터 계약의 데이터 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="d2c2e-224">이 경우 `maxOccurs` 특성은 1이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="d2c2e-225">(값 0이 허용되지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="d2c2e-225">(A value of 0 is not allowed).</span></span>  
  
-   <span data-ttu-id="d2c2e-226">이 요소는 `<xs:sequence>`내에서 발생할 수 있으며, 컬렉션 데이터 계약의 데이터 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="d2c2e-227">이 경우 `maxOccurs` 특성은 1보다 크거나 "unbounded"여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>  
  
-   <span data-ttu-id="d2c2e-228">이 요소는 `<xs:schema>` 내에서 GED(전역 요소 선언)로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="d2c2e-229">\<xs: element > maxoccurs=1 내는 \<나타나는 > (데이터 멤버)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>  
  
|<span data-ttu-id="d2c2e-230">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-230">Attribute</span></span>|<span data-ttu-id="d2c2e-231">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-231">Schema</span></span>|  
|---------------|------------|  
|`ref`|<span data-ttu-id="d2c2e-232">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-232">Forbidden.</span></span>|  
|`name`|<span data-ttu-id="d2c2e-233">지원되며 데이터 멤버 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-233">Supported, maps to the data member name.</span></span>|  
|`type`|<span data-ttu-id="d2c2e-234">지원되며 데이터 멤버 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="d2c2e-235">자세한 내용은 형식/기본 매핑을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="d2c2e-236">지정되지 않고 요소에 익명 형식이 없는 경우 `xs:anyType` 으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|  
|`block`|<span data-ttu-id="d2c2e-237">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-237">Ignored.</span></span>|  
|`default`|<span data-ttu-id="d2c2e-238">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-238">Forbidden.</span></span>|  
|`fixed`|<span data-ttu-id="d2c2e-239">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-239">Forbidden.</span></span>|  
|`form`|<span data-ttu-id="d2c2e-240">정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-240">Must be qualified.</span></span> <span data-ttu-id="d2c2e-241">이 특성은 `elementFormDefault` 에서 `xs:schema`를 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|  
|`id`|<span data-ttu-id="d2c2e-242">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-242">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="d2c2e-243">1</span><span class="sxs-lookup"><span data-stu-id="d2c2e-243">1</span></span>|  
|`minOccurs`|<span data-ttu-id="d2c2e-244">데이터 멤버의 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 속성에 매핑됩니다.`IsRequired` 가 1인 경우 `minOccurs` 는 true입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|  
|`nillable`|<span data-ttu-id="d2c2e-245">형식 매핑에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-245">Affects type mapping.</span></span> <span data-ttu-id="d2c2e-246">형식/기본 매핑을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-246">See Type/primitive mapping.</span></span>|  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="d2c2e-247">\<xs: element > maxOccurs를 사용 하 여 > 내에서 1을 \<나타나는 > (컬렉션)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>  
  
-   <span data-ttu-id="d2c2e-248"><xref:System.Runtime.Serialization.CollectionDataContractAttribute>에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>  
  
-   <span data-ttu-id="d2c2e-249">컬렉션 형식에서 하나의 xs:element만 xs:sequence 내에 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>  
  
 <span data-ttu-id="d2c2e-250">컬렉션은 다음 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-250">Collections can be of the following types:</span></span>  
  
-   <span data-ttu-id="d2c2e-251">정규 컬렉션(예: 배열)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-251">Regular collections (for example, arrays).</span></span>  
  
-   <span data-ttu-id="d2c2e-252">사전 컬렉션(값을 다른 값에 매핑. 예: <xref:System.Collections.Hashtable>)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>  
  
-   <span data-ttu-id="d2c2e-253">사전과 키/값 쌍 형식의 배열 간 유일한 차이는 생성된 프로그래밍 모델에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="d2c2e-254">지정된 형식이 사전 컬렉션임을 나타내는 데 사용할 수 있는 스키마 주석 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>  
  
 <span data-ttu-id="d2c2e-255">`ref`, `block`, `default`, `fixed`, `form`및 `id` 특성에 대한 규칙이 비컬렉션의 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="d2c2e-256">기타 특성은 다음 표에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-256">Other attributes include those in the following table.</span></span>  
  
|<span data-ttu-id="d2c2e-257">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-257">Attribute</span></span>|<span data-ttu-id="d2c2e-258">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-258">Schema</span></span>|  
|---------------|------------|  
|`name`|<span data-ttu-id="d2c2e-259">지원되며 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> 특성의 `CollectionDataContractAttribute` 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|  
|`type`|<span data-ttu-id="d2c2e-260">지원되며 컬렉션에 저장된 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-260">Supported, maps to the type stored in the collection.</span></span>|  
|`maxOccurs`|<span data-ttu-id="d2c2e-261">1보다 크거나 "unbounded"입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="d2c2e-262">DC 스키마는 "unbounded"를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-262">The DC schema should use "unbounded".</span></span>|  
|`minOccurs`|<span data-ttu-id="d2c2e-263">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-263">Ignored.</span></span>|  
|`nillable`|<span data-ttu-id="d2c2e-264">형식 매핑에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-264">Affects type mapping.</span></span> <span data-ttu-id="d2c2e-265">이 특성은 사전 컬렉션에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-265">This attribute is ignored for dictionary collections.</span></span>|  
  
### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="d2c2e-266">\<xs: element > 내는 \<xs: schema > 전역 요소 선언</span><span class="sxs-lookup"><span data-stu-id="d2c2e-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>  
  
-   <span data-ttu-id="d2c2e-267">스키마의 형식과 동일한 이름 및 네임스페이스가 있거나 익명 형식을 정의하는 GED(전역 요소 선언)가 형식과 연결된 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>  
  
-   <span data-ttu-id="d2c2e-268">스키마 내보내기: 연결된 GED가 생성된 모든 단순 및 복합 형식에 대해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>  
  
-   <span data-ttu-id="d2c2e-269">Deserialization/serialization: 연결된 GED가 형식에 대해 루트 요소로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>  
  
-   <span data-ttu-id="d2c2e-270">스키마 가져오기: 다음 규칙을 따르는 경우(형식을 정의하지 않는 한) 연결된 GED가 필요 없으며 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>  
  
|<span data-ttu-id="d2c2e-271">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-271">Attribute</span></span>|<span data-ttu-id="d2c2e-272">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-272">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="d2c2e-273">연결된 GED에 대해 false이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-273">Must be false for associated GEDs.</span></span>|  
|`block`|<span data-ttu-id="d2c2e-274">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-274">Forbidden in associated GEDs.</span></span>|  
|`default`|<span data-ttu-id="d2c2e-275">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-275">Forbidden in associated GEDs.</span></span>|  
|`final`|<span data-ttu-id="d2c2e-276">연결된 GED에 대해 false이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-276">Must be false for associated GEDs.</span></span>|  
|`fixed`|<span data-ttu-id="d2c2e-277">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-277">Forbidden in associated GEDs.</span></span>|  
|`id`|<span data-ttu-id="d2c2e-278">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-278">Ignored.</span></span>|  
|`name`|<span data-ttu-id="d2c2e-279">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-279">Supported.</span></span> <span data-ttu-id="d2c2e-280">연결된 GED의 정의를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-280">See the definition of associated GEDs.</span></span>|  
|`nillable`|<span data-ttu-id="d2c2e-281">연결된 GED에 대해 true이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-281">Must be true for associated GEDs.</span></span>|  
|`substitutionGroup`|<span data-ttu-id="d2c2e-282">연결된 GED에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-282">Forbidden in associated GEDs.</span></span>|  
|`type`|<span data-ttu-id="d2c2e-283">지원되며 요소에 익명 형식이 포함되어 있는 경우 연결된 GED의 연결된 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|  
  
### <a name="xselement-contents"></a><span data-ttu-id="d2c2e-284">\<xs: element >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d2c2e-284">\<xs:element>: contents</span></span>  
  
|<span data-ttu-id="d2c2e-285">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-285">Contents</span></span>|<span data-ttu-id="d2c2e-286">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-286">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="d2c2e-287">지원됩니다.\*</span><span class="sxs-lookup"><span data-stu-id="d2c2e-287">Supported.\*</span></span>|  
|`complexType`|<span data-ttu-id="d2c2e-288">지원됩니다.\*</span><span class="sxs-lookup"><span data-stu-id="d2c2e-288">Supported.\*</span></span>|  
|`unique`|<span data-ttu-id="d2c2e-289">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-289">Ignored.</span></span>|  
|`key`|<span data-ttu-id="d2c2e-290">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-290">Ignored.</span></span>|  
|`keyref`|<span data-ttu-id="d2c2e-291">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-291">Ignored.</span></span>|  
|<span data-ttu-id="d2c2e-292">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-292">(blank)</span></span>|<span data-ttu-id="d2c2e-293">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-293">Supported.</span></span>|  
  
 <span data-ttu-id="d2c2e-294">\* 사용 하는 경우는 `simpleType` 고 `complexType,` 요소 이름에서 파생 된 생성 된 이름을 사용 하 여 명명 된 데이터 계약이 작성 되 고 익명 데이터 계약이 없는 없다는 점을 제외 하면 익명 형식에 대 한 매핑을 익명이 아닌 형식에서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="d2c2e-295">다음 목록에는 익명 형식에 대한 규칙이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-295">The rules for anonymous types are in the following list:</span></span>  
  
-   <span data-ttu-id="d2c2e-296">WCF 구현 세부 정보: 경우는 `xs:element` 이름에 마침표가 없는, 익명 형식은 외부 데이터 계약 형식의 내부 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="d2c2e-297">이름에 마침표가 있는 경우 결과 데이터 계약 형식은 내부 형식이 아닌 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>  
  
-   <span data-ttu-id="d2c2e-298">내부 형식의 생성된 데이터 계약 이름은 외부 형식의 데이터 계약 이름 다음에 마침표, 요소 이름 및 문자열 "Type"이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>  
  
-   <span data-ttu-id="d2c2e-299">이러한 이름을 가진 데이터 계약이 이미 존재하는 경우 이름에 "1", "2", "3" 등을 추가하여 고유 이름으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>  
  
## <a name="simple-types---xssimpletype"></a><span data-ttu-id="d2c2e-300">단순 형식- \<xs:simpleType ></span><span class="sxs-lookup"><span data-stu-id="d2c2e-300">Simple Types - \<xs:simpleType></span></span>  
  
### <a name="xssimpletype-attributes"></a><span data-ttu-id="d2c2e-301">\<xs:simpleType >: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-301">\<xs:simpleType>: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-302">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-302">Attribute</span></span>|<span data-ttu-id="d2c2e-303">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-303">Schema</span></span>|  
|---------------|------------|  
|`final`|<span data-ttu-id="d2c2e-304">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-304">Ignored.</span></span>|  
|`id`|<span data-ttu-id="d2c2e-305">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-305">Ignored.</span></span>|  
|`name`|<span data-ttu-id="d2c2e-306">지원되며 데이터 계약 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-306">Supported, maps to the data contract name.</span></span>|  
  
### <a name="xssimpletype-contents"></a><span data-ttu-id="d2c2e-307">\<xs:simpleType >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d2c2e-307">\<xs:simpleType>: contents</span></span>  
  
|<span data-ttu-id="d2c2e-308">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-308">Contents</span></span>|<span data-ttu-id="d2c2e-309">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-309">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="d2c2e-310">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-310">Supported.</span></span> <span data-ttu-id="d2c2e-311">열거형 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="d2c2e-312">이 특성은 열거형 패턴과 일치하지 않는 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="d2c2e-313">`xs:simpleType` 제한 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-313">See the `xs:simpleType` restrictions section.</span></span>|  
|`list`|<span data-ttu-id="d2c2e-314">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-314">Supported.</span></span> <span data-ttu-id="d2c2e-315">열거형 데이터 계약에 플래그됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="d2c2e-316">`xs:simpleType` 목록 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-316">See the `xs:simpleType` lists section.</span></span>|  
|`union`|<span data-ttu-id="d2c2e-317">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-317">Forbidden.</span></span>|  
  
### <a name="xsrestriction"></a><span data-ttu-id="d2c2e-318">\<xs:restriction></span><span class="sxs-lookup"><span data-stu-id="d2c2e-318">\<xs:restriction></span></span>  
  
-   <span data-ttu-id="d2c2e-319">복합 형식 제한은 base="`xs:anyType`"에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-319">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>  
  
-   <span data-ttu-id="d2c2e-320">`xs:string` 이외의 제한 패싯이 없는 `xs:enumeration` 의 단순 형식 제한은 열거형 데이터 계약에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-320">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>  
  
-   <span data-ttu-id="d2c2e-321">다른 모든 단순 형식 제한은 형식이 제한하는 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-321">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="d2c2e-322">예를 들어, `xs:int` 제한은 `xs:int` 자체와 마찬가지로 정수로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-322">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="d2c2e-323">기본 형식 매핑에 대 한 자세한 내용은 형식/기본 매핑을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-323">For more information about primitive type mapping, see Type/primitive mapping.</span></span>  
  
### <a name="xsrestriction-attributes"></a><span data-ttu-id="d2c2e-324">\<xs: restriction >: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-324">\<xs:restriction>: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-325">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-325">Attribute</span></span>|<span data-ttu-id="d2c2e-326">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-326">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="d2c2e-327">지원되는 단순 형식 또는 `xs:anyType`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-327">Must be a supported simple type or `xs:anyType`.</span></span>|  
|`id`|<span data-ttu-id="d2c2e-328">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-328">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="d2c2e-329">\<xs: restriction > 다른 모든 사례: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d2c2e-329">\<xs:restriction> for all other cases: contents</span></span>  
  
|<span data-ttu-id="d2c2e-330">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-330">Contents</span></span>|<span data-ttu-id="d2c2e-331">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-331">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="d2c2e-332">있는 경우 지원되는 기본 형식에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-332">If present, must be derived from a supported primitive type.</span></span>|  
|`minExclusive`|<span data-ttu-id="d2c2e-333">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-333">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="d2c2e-334">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-334">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="d2c2e-335">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-335">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="d2c2e-336">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-336">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="d2c2e-337">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-337">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="d2c2e-338">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-338">Ignored.</span></span>|  
|`length`|<span data-ttu-id="d2c2e-339">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-339">Ignored.</span></span>|  
|`minLength`|<span data-ttu-id="d2c2e-340">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-340">Ignored.</span></span>|  
|`maxLength`|<span data-ttu-id="d2c2e-341">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-341">Ignored.</span></span>|  
|`enumeration`|<span data-ttu-id="d2c2e-342">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-342">Ignored.</span></span>|  
|`whiteSpace`|<span data-ttu-id="d2c2e-343">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-343">Ignored.</span></span>|  
|`pattern`|<span data-ttu-id="d2c2e-344">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-344">Ignored.</span></span>|  
|<span data-ttu-id="d2c2e-345">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-345">(blank)</span></span>|<span data-ttu-id="d2c2e-346">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-346">Supported.</span></span>|  
  
## <a name="enumeration"></a><span data-ttu-id="d2c2e-347">열거형</span><span class="sxs-lookup"><span data-stu-id="d2c2e-347">Enumeration</span></span>  
  
### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="d2c2e-348">\<xs: restriction > 열거형에 대 한: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-348">\<xs:restriction> for enumerations: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-349">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-349">Attribute</span></span>|<span data-ttu-id="d2c2e-350">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-350">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="d2c2e-351">있는 경우 `xs:string`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-351">If present, must be `xs:string`.</span></span>|  
|`id`|<span data-ttu-id="d2c2e-352">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-352">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="d2c2e-353">\<xs: restriction > 열거형에 대 한: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d2c2e-353">\<xs:restriction> for enumerations: contents</span></span>  
  
|<span data-ttu-id="d2c2e-354">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-354">Contents</span></span>|<span data-ttu-id="d2c2e-355">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-355">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="d2c2e-356">있는 경우 데이터 계약(이 단원)에서 지원하는 열거형 제한이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-356">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|  
|`minExclusive`|<span data-ttu-id="d2c2e-357">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-357">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="d2c2e-358">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-358">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="d2c2e-359">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-359">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="d2c2e-360">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-360">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="d2c2e-361">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-361">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="d2c2e-362">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-362">Ignored.</span></span>|  
|`length`|<span data-ttu-id="d2c2e-363">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-363">Forbidden.</span></span>|  
|`minLength`|<span data-ttu-id="d2c2e-364">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-364">Forbidden.</span></span>|  
|`maxLength`|<span data-ttu-id="d2c2e-365">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-365">Forbidden.</span></span>|  
|`enumeration`|<span data-ttu-id="d2c2e-366">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-366">Supported.</span></span> <span data-ttu-id="d2c2e-367">열거형 "ID"는 무시되고 "value"는 열거형 데이터 계약의 값 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-367">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|  
|`whiteSpace`|<span data-ttu-id="d2c2e-368">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-368">Forbidden.</span></span>|  
|`pattern`|<span data-ttu-id="d2c2e-369">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-369">Forbidden.</span></span>|  
|<span data-ttu-id="d2c2e-370">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="d2c2e-370">(empty)</span></span>|<span data-ttu-id="d2c2e-371">지원되며 비어 있는 열거형 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-371">Supported, maps to empty enumeration type.</span></span>|  
  
 <span data-ttu-id="d2c2e-372">다음 코드는 C# 열거형 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-372">The following code shows a C# enumeration class.</span></span>  
  
```csharp  
public enum MyEnum  
{  
  first = 3,  
  second = 4,  
  third =5  
}  
```  
  
 <span data-ttu-id="d2c2e-373">이 클래스는 `DataContractSerializer`에 의해 다음 스키마에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-373">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="d2c2e-374">열거형 값이 1부터 시작하는 경우 `xs:annotation` 블록이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-374">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>  
  
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
  
### <a name="xslist"></a><span data-ttu-id="d2c2e-375">\<xs:list></span><span class="sxs-lookup"><span data-stu-id="d2c2e-375">\<xs:list></span></span>  
 `DataContractSerializer` <span data-ttu-id="d2c2e-376">으로 표시 된 맵 열거형 형식 `System.FlagsAttribute` 하 `xs:list` 에서 파생 된 `xs:string`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-376">maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="d2c2e-377">다른 `xs:list` 변형은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-377">No other `xs:list` variations are supported.</span></span>  
  
### <a name="xslist-attributes"></a><span data-ttu-id="d2c2e-378">\<xs: list >: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-378">\<xs:list>: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-379">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-379">Attribute</span></span>|<span data-ttu-id="d2c2e-380">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-380">Schema</span></span>|  
|---------------|------------|  
|`itemType`|<span data-ttu-id="d2c2e-381">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-381">Forbidden.</span></span>|  
|`id`|<span data-ttu-id="d2c2e-382">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-382">Ignored.</span></span>|  
  
### <a name="xslist-contents"></a><span data-ttu-id="d2c2e-383">\<xs:list>: contents</span><span class="sxs-lookup"><span data-stu-id="d2c2e-383">\<xs:list>: contents</span></span>  
  
|<span data-ttu-id="d2c2e-384">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-384">Contents</span></span>|<span data-ttu-id="d2c2e-385">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-385">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="d2c2e-386">`xs:string` 패싯을 사용하는 `xs:enumeration` 에서의 제한이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-386">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|  
  
 <span data-ttu-id="d2c2e-387">열거형 값이 2의 거듭제곱으로 진행되지 않는 경우(플래그의 경우 기본값) 값은 `xs:annotation/xs:appInfo/ser:EnumerationValue` 요소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-387">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>  
  
 <span data-ttu-id="d2c2e-388">예를 들어, 다음 코드는 열거형 형식을 플래그합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-388">For example, the following code flags an enumeration type.</span></span>  
  
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
  
 <span data-ttu-id="d2c2e-389">이 형식이 다음 스키마에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-389">This type maps to the following schema.</span></span>  
  
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
  
## <a name="inheritance"></a><span data-ttu-id="d2c2e-390">상속</span><span class="sxs-lookup"><span data-stu-id="d2c2e-390">Inheritance</span></span>  
  
### <a name="general-rules"></a><span data-ttu-id="d2c2e-391">일반 규칙</span><span class="sxs-lookup"><span data-stu-id="d2c2e-391">General rules</span></span>  
 <span data-ttu-id="d2c2e-392">데이터 계약을 다른 데이터 계약에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-392">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="d2c2e-393">이러한 데이터 계약은 기본 계약에 매핑되고 `<xs:extension>` XML 스키마 구문을 사용하여 확장 형식에 의해 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-393">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>  
  
 <span data-ttu-id="d2c2e-394">데이터 계약을 컬렉션 데이터 계약에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-394">A data contract cannot inherit from a collection data contract.</span></span>  
  
 <span data-ttu-id="d2c2e-395">예를 들어, 다음 코드는 데이터 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-395">For example, the following code is a data contract.</span></span>  
  
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
  
 <span data-ttu-id="d2c2e-396">이 데이터 계약은 다음 XML 스키마 형식 선언에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-396">This data contract maps to the following XML Schema type declaration.</span></span>  
  
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
  
### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="d2c2e-397">\<xs:complexContent >: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-397">\<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-398">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-398">Attribute</span></span>|<span data-ttu-id="d2c2e-399">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-399">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="d2c2e-400">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-400">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="d2c2e-401">false이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-401">Must be false.</span></span>|  
  
### <a name="xscomplexcontent-contents"></a><span data-ttu-id="d2c2e-402">\<xs:complexContent >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d2c2e-402">\<xs:complexContent>: contents</span></span>  
  
|<span data-ttu-id="d2c2e-403">목차</span><span class="sxs-lookup"><span data-stu-id="d2c2e-403">Contents</span></span>|<span data-ttu-id="d2c2e-404">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-404">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="d2c2e-405">base="`xs:anyType`"인 경우를 제외하고 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-405">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="d2c2e-406">후자는 `xs:restriction` 의 콘텐츠를 `xs:complexContent`컨테이너 바로 아래에 배치하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-406">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|  
|`extension`|<span data-ttu-id="d2c2e-407">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-407">Supported.</span></span> <span data-ttu-id="d2c2e-408">데이터 계약 상속에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-408">Maps to data contract inheritance.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="d2c2e-409">\<xs: extension >에서 \<xs:complexContent >: 특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-409">\<xs:extension> in \<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="d2c2e-410">특성</span><span class="sxs-lookup"><span data-stu-id="d2c2e-410">Attribute</span></span>|<span data-ttu-id="d2c2e-411">스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-411">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="d2c2e-412">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-412">Ignored.</span></span>|  
|`base`|<span data-ttu-id="d2c2e-413">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-413">Supported.</span></span> <span data-ttu-id="d2c2e-414">이 형식이 상속되는 기본 데이터 계약 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-414">Maps to the base data contract type that this type inherits from.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="d2c2e-415">\<xs: extension >에서 \<xs:complexContent >: 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d2c2e-415">\<xs:extension> in \<xs:complexContent>: contents</span></span>  
 <span data-ttu-id="d2c2e-416">규칙은 `<xs:complexType>` 콘텐츠에서와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-416">The rules are the same as for `<xs:complexType>` contents.</span></span>  
  
 <span data-ttu-id="d2c2e-417">`<xs:sequence>` 를 제공하는 경우 멤버 요소가 파생된 데이터 계약에 있는 추가 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-417">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>  
  
 <span data-ttu-id="d2c2e-418">파생된 형식에 기본 형식의 요소와 동일한 이름을 가진 요소가 포함된 경우 중복 요소 선언이 고유하게 생성된 이름을 가진 데이터 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-418">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="d2c2e-419">고유한 이름을 찾을 때까지 양의 정수가 데이터 멤버 이름("member1", "member2" 등)에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-419">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="d2c2e-420">반대의 경우는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-420">Conversely:</span></span>  
  
-   <span data-ttu-id="d2c2e-421">파생된 데이터 계약에 기본 데이터 계약의 데이터 멤버와 동일한 이름을 가진 데이터 멤버가 있는 경우 `DataContractSerializer` 는 이 해당 요소를 파생된 형식으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-421">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>  
  
-   <span data-ttu-id="d2c2e-422">파생된 데이터 계약에 기본 데이터 계약의 데이터 멤버와 동일한 이름을 가졌지만 형식은 다른 데이터 멤버가 포함된 경우 `DataContractSerializer` 는 기본 형식 및 파생된 형식 선언 모두에서 `xs:anyType` 형식의 요소와 함께 스키마를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-422">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="d2c2e-423">원래 형식 이름은 `xs:annotations/xs:appInfo/ser:ActualType/@Name`에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-423">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>  
  
 <span data-ttu-id="d2c2e-424">이 두 변형을 통해 스키마는 모호한 콘텐츠 모델을 가질 수 있으며 각 데이터 멤버의 순서에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-424">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>  
  
## <a name="typeprimitive-mapping"></a><span data-ttu-id="d2c2e-425">형식/기본 매핑</span><span class="sxs-lookup"><span data-stu-id="d2c2e-425">Type/primitive mapping</span></span>  
 <span data-ttu-id="d2c2e-426">`DataContractSerializer` 는 XML 스키마 기본 형식에 대해 다음 매핑을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-426">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>  
  
|<span data-ttu-id="d2c2e-427">XSD 형식</span><span class="sxs-lookup"><span data-stu-id="d2c2e-427">XSD type</span></span>|<span data-ttu-id="d2c2e-428">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="d2c2e-428">.NET type</span></span>|  
|--------------|---------------|  
|`anyType`|<xref:System.Object><span data-ttu-id="d2c2e-429">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-429">.</span></span>|  
|`anySimpleType`|<xref:System.String><span data-ttu-id="d2c2e-430">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-430">.</span></span>|  
|`duration`|<xref:System.TimeSpan><span data-ttu-id="d2c2e-431">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-431">.</span></span>|  
|`dateTime`|<xref:System.DateTime><span data-ttu-id="d2c2e-432">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-432">.</span></span>|  
|`dateTimeOffset`|<xref:System.DateTime> <span data-ttu-id="d2c2e-433">및 <xref:System.TimeSpan> 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-433">and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="d2c2e-434">아래 DateTimeOffset Serialization을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-434">See DateTimeOffset Serialization below.</span></span>|  
|`time`|<xref:System.String><span data-ttu-id="d2c2e-435">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-435">.</span></span>|  
|`date`|<xref:System.String><span data-ttu-id="d2c2e-436">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-436">.</span></span>|  
|`gYearMonth`|<xref:System.String><span data-ttu-id="d2c2e-437">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-437">.</span></span>|  
|`gYear`|<xref:System.String><span data-ttu-id="d2c2e-438">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-438">.</span></span>|  
|`gMonthDay`|<xref:System.String><span data-ttu-id="d2c2e-439">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-439">.</span></span>|  
|`gDay`|<xref:System.String><span data-ttu-id="d2c2e-440">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-440">.</span></span>|  
|`gMonth`|<xref:System.String><span data-ttu-id="d2c2e-441">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-441">.</span></span>|  
|`boolean`|<xref:System.Boolean>|  
|`base64Binary`|<xref:System.Byte> <span data-ttu-id="d2c2e-442">배열이 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="d2c2e-442">array.</span></span>|  
|`hexBinary`|<xref:System.String><span data-ttu-id="d2c2e-443">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-443">.</span></span>|  
|`float`|<xref:System.Single><span data-ttu-id="d2c2e-444">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-444">.</span></span>|  
|`double`|<xref:System.Double><span data-ttu-id="d2c2e-445">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-445">.</span></span>|  
|`anyURI`|<xref:System.Uri><span data-ttu-id="d2c2e-446">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-446">.</span></span>|  
|`QName`|<xref:System.Xml.XmlQualifiedName><span data-ttu-id="d2c2e-447">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-447">.</span></span>|  
|`string`|<xref:System.String><span data-ttu-id="d2c2e-448">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-448">.</span></span>|  
|`normalizedString`|<xref:System.String><span data-ttu-id="d2c2e-449">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-449">.</span></span>|  
|`token`|<xref:System.String><span data-ttu-id="d2c2e-450">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-450">.</span></span>|  
|`language`|<xref:System.String><span data-ttu-id="d2c2e-451">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-451">.</span></span>|  
|`Name`|<xref:System.String><span data-ttu-id="d2c2e-452">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-452">.</span></span>|  
|`NCName`|<xref:System.String><span data-ttu-id="d2c2e-453">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-453">.</span></span>|  
|`ID`|<xref:System.String><span data-ttu-id="d2c2e-454">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-454">.</span></span>|  
|`IDREF`|<xref:System.String><span data-ttu-id="d2c2e-455">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-455">.</span></span>|  
|`IDREFS`|<xref:System.String><span data-ttu-id="d2c2e-456">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-456">.</span></span>|  
|`ENTITY`|<xref:System.String><span data-ttu-id="d2c2e-457">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-457">.</span></span>|  
|`ENTITIES`|<xref:System.String><span data-ttu-id="d2c2e-458">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-458">.</span></span>|  
|`NMTOKEN`|<xref:System.String><span data-ttu-id="d2c2e-459">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-459">.</span></span>|  
|`NMTOKENS`|<xref:System.String><span data-ttu-id="d2c2e-460">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-460">.</span></span>|  
|`decimal`|<xref:System.Decimal><span data-ttu-id="d2c2e-461">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-461">.</span></span>|  
|`integer`|<xref:System.Int64><span data-ttu-id="d2c2e-462">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-462">.</span></span>|  
|`nonPositiveInteger`|<xref:System.Int64><span data-ttu-id="d2c2e-463">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-463">.</span></span>|  
|`negativeInteger`|<xref:System.Int64><span data-ttu-id="d2c2e-464">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-464">.</span></span>|  
|`long`|<xref:System.Int64><span data-ttu-id="d2c2e-465">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-465">.</span></span>|  
|`int`|<xref:System.Int32><span data-ttu-id="d2c2e-466">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-466">.</span></span>|  
|`short`|<xref:System.Int16><span data-ttu-id="d2c2e-467">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-467">.</span></span>|  
|`Byte`|<xref:System.SByte><span data-ttu-id="d2c2e-468">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-468">.</span></span>|  
|`nonNegativeInteger`|<xref:System.Int64><span data-ttu-id="d2c2e-469">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-469">.</span></span>|  
|`unsignedLong`|<xref:System.UInt64><span data-ttu-id="d2c2e-470">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-470">.</span></span>|  
|`unsignedInt`|<xref:System.UInt32><span data-ttu-id="d2c2e-471">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-471">.</span></span>|  
|`unsignedShort`|<xref:System.UInt16><span data-ttu-id="d2c2e-472">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-472">.</span></span>|  
|`unsignedByte`|<xref:System.Byte><span data-ttu-id="d2c2e-473">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-473">.</span></span>|  
|`positiveInteger`|<xref:System.Int64><span data-ttu-id="d2c2e-474">.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-474">.</span></span>|  
  
## <a name="iserializable-types-mapping"></a><span data-ttu-id="d2c2e-475">ISerializable 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="d2c2e-475">ISerializable types mapping</span></span>  
 <span data-ttu-id="d2c2e-476">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 은 <xref:System.Runtime.Serialization.ISerializable> 버전 1.0에서 지속성이나 데이터 전송을 위해 개체를 serialize하는 일반 메커니즘으로 새로 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-476">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="d2c2e-477">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 을 구현하고 애플리케이션 간에 전달할 수 있는 다양한 `ISerializable` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-477">There are many [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that implement `ISerializable` and that can be passed between applications.</span></span> <xref:System.Runtime.Serialization.DataContractSerializer> <span data-ttu-id="d2c2e-478">기본적으로 지 `ISerializable` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-478">naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="d2c2e-479">`DataContractSerializer` 는 형식의 QName(정규화된 이름)에 의해서만 달라지는 효율적인 속성 컬렉션인 `ISerializable` 구현 스키마 형식을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-479">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="d2c2e-480">예를 들어, 합니다 `DataContractSerializer` 매핑합니다 <xref:System.Exception> 된 다음 XSD 형식에 `http://schemas.datacontract.org/2004/07/System` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-480">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>  
  
```xml  
<xs:complexType name="Exception">  
 <xs:sequence>  
  <xs:any minOccurs="0" maxOccurs="unbounded"   
      namespace="##local" processContents="skip"/>  
 </xs:sequence>  
 <xs:attribute ref="ser:FactoryType"/>  
</xs:complexType>  
```  
  
 <span data-ttu-id="d2c2e-481">데이터 계약 Serialization 스키마에서 선언한 선택적 특성 `ser:FactoryType` 은 형식을 deserialize할 수 있는 팩터리 클래스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-481">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="d2c2e-482">팩터리 클래스는 사용 중인 `DataContractSerializer` 인스턴스의 알려진 형식 컬렉션의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-482">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="d2c2e-483">알려진된 형식에 대 한 자세한 내용은 참조 하세요. [데이터 계약 알려진 형식을](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-483">For more information about known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="datacontract-serialization-schema"></a><span data-ttu-id="d2c2e-484">DataContract Serialization 스키마</span><span class="sxs-lookup"><span data-stu-id="d2c2e-484">DataContract Serialization Schema</span></span>  
 <span data-ttu-id="d2c2e-485">`DataContractSerializer` 에서 내보낸 여러 스키마는 다음과 같은 특별한 데이터 계약 Serialization 네임스페이스의 형식, 요소 및 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-485">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>  
  
 `http://schemas.microsoft.com/2003/10/Serialization`
  
 <span data-ttu-id="d2c2e-486">다음은 전체 데이터 계약 Serialization 스키마 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-486">The following is a complete Data Contract Serialization schema declaration.</span></span>  
  
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
  
 <span data-ttu-id="d2c2e-487">다음 항목에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-487">The following should be noted:</span></span>  
  
-   `ser:char` <span data-ttu-id="d2c2e-488">형식의 유니코드 문자를 표현 하기 위해 도입 되었습니다 <xref:System.Char>합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-488">is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>  
  
-   <span data-ttu-id="d2c2e-489">`valuespace` 의 `xs:duration` 는 <xref:System.TimeSpan>에 매핑될 수 있도록 정렬된 집합으로 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-489">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>  
  
-   `FactoryType` <span data-ttu-id="d2c2e-490">파생 된 형식에서 내보낸 스키마는 <xref:System.Runtime.Serialization.ISerializable>합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-490">is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="d2c2e-491">DataContract가 아닌 스키마 가져오기</span><span class="sxs-lookup"><span data-stu-id="d2c2e-491">Importing non-DataContract schemas</span></span>  
 `DataContractSerializer` <span data-ttu-id="d2c2e-492">에 `ImportXmlTypes` 옵션을 준수 하지 않는 스키마를 가져올 수 있도록 합니다 `DataContractSerializer` XSD 프로필 (참조를 <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> 속성).</span><span class="sxs-lookup"><span data-stu-id="d2c2e-492">has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="d2c2e-493">이 옵션을 `true` 로 설정하면 맞지 않는 스키마 형식을 허용하고, 이러한 형식을 다음 구현에 매핑하고, <xref:System.Xml.Serialization.IXmlSerializable> 이 <xref:System.Xml.XmlNode> 의 배열을 래핑할 수 있습니다(클래스 이름만 다름).</span><span class="sxs-lookup"><span data-stu-id="d2c2e-493">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>  
  
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
  
## <a name="datetimeoffset-serialization"></a><span data-ttu-id="d2c2e-494">DateTimeOffset Serialization</span><span class="sxs-lookup"><span data-stu-id="d2c2e-494">DateTimeOffset Serialization</span></span>  
 <span data-ttu-id="d2c2e-495"><xref:System.DateTimeOffset> 은 기본 형식으로 취급되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-495">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="d2c2e-496">대신 두 부분으로 구성된 복합 요소로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-496">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="d2c2e-497">첫 번째 부분은 날짜/시간을 표시하고 두 번째 부분은 날짜/시간의 오프셋을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-497">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="d2c2e-498">다음 코드에서는 serialize된 DateTimeOffset 값의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-498">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="d2c2e-499">스키마는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c2e-499">The schema is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2c2e-500">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2c2e-500">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="d2c2e-501">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="d2c2e-501">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
