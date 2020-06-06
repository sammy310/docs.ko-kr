---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850034"
---
# \<comContract>
<span data-ttu-id="49878-101">COM+ 통합 서비스 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49878-101">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="49878-102">구문</span><span class="sxs-lookup"><span data-stu-id="49878-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49878-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="49878-103">Attributes and Elements</span></span>  
 <span data-ttu-id="49878-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="49878-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49878-105">특성</span><span class="sxs-lookup"><span data-stu-id="49878-105">Attributes</span></span>  
  
|<span data-ttu-id="49878-106">attribute</span><span class="sxs-lookup"><span data-stu-id="49878-106">Attribute</span></span>|<span data-ttu-id="49878-107">Description</span><span class="sxs-lookup"><span data-stu-id="49878-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49878-108">계약</span><span class="sxs-lookup"><span data-stu-id="49878-108">contract</span></span>|<span data-ttu-id="49878-109">계약 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="49878-109">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="49878-110">name</span><span class="sxs-lookup"><span data-stu-id="49878-110">name</span></span>|<span data-ttu-id="49878-111">계약 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="49878-111">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="49878-112">namespace</span><span class="sxs-lookup"><span data-stu-id="49878-112">namespace</span></span>|<span data-ttu-id="49878-113">계약 네임스페이스를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="49878-113">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="49878-114">requiresSession</span><span class="sxs-lookup"><span data-stu-id="49878-114">requiresSession</span></span>|<span data-ttu-id="49878-115">계약을 세션 바인딩에서만 사용할 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="49878-115">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="49878-116">서비스가 초기화될 때 통합 런타임에서는 사용될 바인딩 형식과 이 설정이 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="49878-116">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="49878-117">계약의 바인딩 중 하나 이상이 충돌할 경우 예외가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="49878-117">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="49878-118">이 속성이 `false`이고 단방향 채널을 사용하며 [out] 매개 변수가 있을 경우에도 예외가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="49878-118">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49878-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="49878-119">Child Elements</span></span>  
  
|<span data-ttu-id="49878-120">요소</span><span class="sxs-lookup"><span data-stu-id="49878-120">Element</span></span>|<span data-ttu-id="49878-121">Description</span><span class="sxs-lookup"><span data-stu-id="49878-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49878-122">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="49878-122">persistableTypes</span></span>|<span data-ttu-id="49878-123">모든 지속 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="49878-123">All the persistable types.</span></span>|  
|<span data-ttu-id="49878-124">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="49878-124">userDefinedTypes</span></span>|<span data-ttu-id="49878-125">서비스 계약에 포함될 UDT(사용자 정의 형식) 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="49878-125">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="49878-126">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="49878-126">exposedMethods</span></span>|<span data-ttu-id="49878-127">COM+ 구성 요소의 인터페이스가 웹 서비스로 공개될 때 노출되는 COM+ 메서드 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="49878-127">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49878-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="49878-128">Parent Elements</span></span>  
  
|<span data-ttu-id="49878-129">요소</span><span class="sxs-lookup"><span data-stu-id="49878-129">Element</span></span>|<span data-ttu-id="49878-130">Description</span><span class="sxs-lookup"><span data-stu-id="49878-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49878-131">comContracts</span><span class="sxs-lookup"><span data-stu-id="49878-131">comContracts</span></span>|<span data-ttu-id="49878-132">`comContract` 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="49878-132">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49878-133">설명</span><span class="sxs-lookup"><span data-stu-id="49878-133">Remarks</span></span>  
 <span data-ttu-id="49878-134">COM + 통합 서비스 계약은 현재 `http://tempuri.org` 네임 스페이스로 제한 되며, 계약 이름은 지원 COM 인터페이스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49878-134">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="49878-135">그러나 구성 파일에서`comContracts` 섹션 및 `comContract` 요소를 사용하여 대안을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49878-135">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="49878-136">예를 들어 다음 구성을 사용하여 포함시킬 네임스페이스, 계약 이름, 사용자 정의 형식 및 서비스 계약의 기타 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49878-136">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="49878-137">지정된 네임스페이스와 계약 이름은 서비스가 초기화될 때 생성된 서비스 설명에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="49878-137">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49878-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49878-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="49878-139">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="49878-139">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="49878-140">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="49878-140">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
