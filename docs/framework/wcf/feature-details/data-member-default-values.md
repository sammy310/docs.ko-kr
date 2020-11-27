---
title: 데이터 멤버 기본값
description: .NET Framework 기본값이 있을 경우 serialize 된 데이터에서 데이터 멤버를 생략 하는 방법에 대해 알아봅니다. WCF는 기본값을 직렬화 하지 않고 성능을 향상 시킬 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data members [WCF], default values
- data members [WCF]
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
ms.openlocfilehash: 98b19fdabebeb8a1d43a66a192cb523b82ada618
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261997"
---
# <a name="data-member-default-values"></a><span data-ttu-id="09647-104">데이터 멤버 기본값</span><span class="sxs-lookup"><span data-stu-id="09647-104">Data Member Default Values</span></span>

<span data-ttu-id="09647-105">.NET Framework에서는 형식에 *기본값* 의 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-105">In the .NET Framework, types have a concept of *default values*.</span></span> <span data-ttu-id="09647-106">예를 들어 참조 형식의 기본값은 `null`이고 정수 형식의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="09647-106">For example, for any reference type the default value is `null`, and for an integer type it is zero.</span></span> <span data-ttu-id="09647-107">기본값으로 설정할 경우 serialize된 데이터에서 데이터 멤버를 생략하는 것이 좋을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-107">It is occasionally desirable to omit a data member from serialized data when it is set to its default value.</span></span> <span data-ttu-id="09647-108">멤버에 기본값이 있기 때문에 실제 값을 serialize할 필요가 없으므로 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-108">Because the member has a default value, an actual value need not be serialized; this has a performance advantage.</span></span>  
  
 <span data-ttu-id="09647-109">serialize된 데이터에서 멤버를 생략하려면 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> 특성의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 `false`로 설정합니다. 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="09647-109">To omit a member from serialized data, set the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to `false` (the default is `true`).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09647-110">상호 운용성이나 데이터 크기 축소 등 특별히 필요한 경우에만 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> 속성을 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09647-110">You should set the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property to `false` if there is a specific need to do so, such as for interoperability or data size reduction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09647-111">예제</span><span class="sxs-lookup"><span data-stu-id="09647-111">Example</span></span>  

 <span data-ttu-id="09647-112">다음 코드에는 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>가 `false`로 설정된 여러 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-112">The following code has several members with the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> set to `false`.</span></span>  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 <span data-ttu-id="09647-113">이 클래스의 인스턴스를 serialize하면 다음과 같은 결과가 나타납니다. `employeeName` 및 `employeeID`가 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-113">If an instance of this class is serialized, the result is as follows: `employeeName` and `employeeID` is serialized.</span></span> <span data-ttu-id="09647-114">`employeeName` 값이 null이고 `employeeID` 값이 0이면 명시적으로 serialize된 데이터의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-114">The null value for `employeeName` and the zero value for `employeeID` is explicitly part of the serialized data.</span></span> <span data-ttu-id="09647-115">그러나 `position`, `salary` 및 `bonus` 멤버는 serialize되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-115">However, the `position`, `salary`, and `bonus` members are not serialized.</span></span> <span data-ttu-id="09647-116">마지막으로 57800은 정수에 대한 .NET 기본값인 0과 일치하지 않으므로 `targetSalary` 속성이 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>로 설정되어 있더라도 `false`는 평소와 같이 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-116">Finally, `targetSalary` is serialized as usual, even though the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property is set to `false`, because 57800 does not match the .NET default value for an integer, which is zero.</span></span>  
  
### <a name="xml-representation"></a><span data-ttu-id="09647-117">XML 표현</span><span class="sxs-lookup"><span data-stu-id="09647-117">XML Representation</span></span>  

 <span data-ttu-id="09647-118">이전 예제가 XML로 serialize될 경우의 표현은 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="09647-118">If the previous example is serialized to XML, the representation is similar to the following.</span></span>  
  
```xml  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 <span data-ttu-id="09647-119">`xsi:nil` 특성은 null 값을 명시적으로 나타낼 수 있는 상호 운용 가능한 방법을 제공하는 W3C(World Wide Web Consortium) XML 스키마 인스턴스 네임스페이스의 특수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="09647-119">The `xsi:nil` attribute is a special attribute in the World Wide Web Consortium (W3C) XML Schema instance namespace that provides an interoperable way to explicitly represent a null value.</span></span> <span data-ttu-id="09647-120">XML에는 지위, 급여 및 보너스 데이터 멤버에 대한 정보는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-120">Note that there is no information at all in the XML about position, salary, and bonus data members.</span></span> <span data-ttu-id="09647-121">받는 측에서 이 값을 `null`, 0 및 `null`로 각각 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-121">The receiving end can interpret these as `null`, zero, and `null`, respectively.</span></span> <span data-ttu-id="09647-122">타사 역직렬 변환기에서도 올바른 해석을 한다는 보장이 없으므로 이 패턴은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-122">There is no guarantee that a third-party deserializer can make the correct interpretation, which is why this pattern is not recommended.</span></span> <span data-ttu-id="09647-123"><xref:System.Runtime.Serialization.DataContractSerializer> 클래스는 누락된 값에 대해 올바른 해석을 항상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09647-123">The <xref:System.Runtime.Serialization.DataContractSerializer> class always selects the correct interpretation for missing values.</span></span>  
  
### <a name="interaction-with-isrequired"></a><span data-ttu-id="09647-124">IsRequired와의 상호 작용</span><span class="sxs-lookup"><span data-stu-id="09647-124">Interaction with IsRequired</span></span>  

 <span data-ttu-id="09647-125">[데이터 계약 버전 관리](data-contract-versioning.md)에 설명 된 대로 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성에는 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 속성이 있습니다 (기본값은 `false` ).</span><span class="sxs-lookup"><span data-stu-id="09647-125">As discussed in [Data Contract Versioning](data-contract-versioning.md), the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property (the default is `false`).</span></span> <span data-ttu-id="09647-126">이 속성은 지정된 데이터 멤버가 역직렬화될 때 직렬화된 데이터에 있어야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09647-126">The property indicates whether a given data member must be present in the serialized data when it is being deserialized.</span></span> <span data-ttu-id="09647-127">`IsRequired`가 `true`(값이 있어야 함을 표시)로 설정되고 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>가 `false`(기본값으로 설정된 경우 값이 없어야 함을 표시)로 설정되어 있으면 결과가 모순될 수 있으므로 이 데이터 멤버의 기본값을 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-127">If `IsRequired` is set to `true`, (which indicates that a value must be present) and <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> is set to `false` (indicating that the value must not be present if it is set to its default value), default values for this data member cannot be serialized because the results would be contradictory.</span></span> <span data-ttu-id="09647-128">그런 데이터 멤버를 기본값(일반적으로 `null` 또는 0)으로 설정하고 serialization을 시도하면 <xref:System.Runtime.Serialization.SerializationException>가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-128">If such a data member is set to its default value (usually `null` or zero) and a serialization is attempted, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>  
  
### <a name="schema-representation"></a><span data-ttu-id="09647-129">스키마 표현</span><span class="sxs-lookup"><span data-stu-id="09647-129">Schema Representation</span></span>  

 <span data-ttu-id="09647-130">속성이로 설정 된 경우 데이터 멤버의 XSD (XML 스키마 정의 언어) 스키마 표현의 세부 정보에 대 한 자세한 내용은 `EmitDefaultValue` `false` [데이터 계약 스키마 참조를 참조](data-contract-schema-reference.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="09647-130">The details of the XML Schema definition language (XSD) schema representation of data members when the `EmitDefaultValue` property is set to `false` are discussed in [Data Contract Schema Reference](data-contract-schema-reference.md).</span></span> <span data-ttu-id="09647-131">여기서는 개요만 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="09647-131">However, the following is a brief overview:</span></span>  
  
- <span data-ttu-id="09647-132"><xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>가로 설정 되 면 `false` 스키마에서 WCF (Windows Communication Foundation)에 한정 된 주석으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-132">When the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> is set to `false`, it is represented in the schema as an annotation specific to Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="09647-133">이 정보를 나타내는 상호 운용 가능한 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-133">There is no interoperable way to represent this information.</span></span> <span data-ttu-id="09647-134">특히 스키마의 "default" 특성은 이 용도로 사용되지 않고, `minOccurs` 특성은 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 설정의 영향만 받고, `nillable` 특성은 데이터 멤버 형식의 영향만 받습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-134">In particular, the "default" attribute in the schema is not used for this purpose, the `minOccurs` attribute is affected only by the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> setting, and the `nillable` attribute is affected only by the type of the data member.</span></span>  
  
- <span data-ttu-id="09647-135">사용할 실제 기본값은 스키마에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09647-135">The actual default value to use is not present in the schema.</span></span> <span data-ttu-id="09647-136">따라서 수신하는 엔드포인트에서 누락된 요소를 적절하게 해석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09647-136">It is up to the receiving endpoint to appropriately interpret a missing element.</span></span>  
  
 <span data-ttu-id="09647-137">스키마 가져오기에서 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> `false` 이전에 언급 된 WCF 관련 주석이 검색 될 때마다 속성이 자동으로로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-137">On schema import, the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property is automatically set to `false` whenever the WCF-specific annotation mentioned previously is detected.</span></span> <span data-ttu-id="09647-138">`false` `nillable` `false` ASP.NET 웹 서비스를 사용할 때 일반적으로 발생 하는 특정 상호 운용성 시나리오를 지원 하기 위해 속성이로 설정 된 참조 형식에 대해서도로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09647-138">It is also set to `false` for reference types that have the `nillable` property set to `false` to support specific interoperability scenarios that commonly occur when consuming ASP.NET Web services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09647-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09647-139">See also</span></span>

- <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
