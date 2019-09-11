---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855302"
---
# <a name="exposedmethod"></a><span data-ttu-id="ca67c-101">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="ca67c-101">\<exposedMethod></span></span>
<span data-ttu-id="ca67c-102">COM+ 구성 요소의 인터페이스가 웹 서비스로 노출될 때 노출되는 COM+ 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
<span data-ttu-id="ca67c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ca67c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ca67c-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ca67c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ca67c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="ca67c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="ca67c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="ca67c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="ca67c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<exposedMethods >** ](exposedmethods.md)</span><span class="sxs-lookup"><span data-stu-id="ca67c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)</span></span>\
<span data-ttu-id="ca67c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<exposedMethod >**</span><span class="sxs-lookup"><span data-stu-id="ca67c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca67c-109">구문</span><span class="sxs-lookup"><span data-stu-id="ca67c-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca67c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ca67c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca67c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca67c-112">특성</span><span class="sxs-lookup"><span data-stu-id="ca67c-112">Attributes</span></span>  
  
|<span data-ttu-id="ca67c-113">특성</span><span class="sxs-lookup"><span data-stu-id="ca67c-113">Attribute</span></span>|<span data-ttu-id="ca67c-114">Description</span><span class="sxs-lookup"><span data-stu-id="ca67c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca67c-115">name</span><span class="sxs-lookup"><span data-stu-id="ca67c-115">name</span></span>|<span data-ttu-id="ca67c-116">COM+ 구성 요소의 인터페이스가 웹 서비스로 공개될 때 노출되는 COM+ 메서드를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-116">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca67c-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ca67c-117">Child Elements</span></span>  
 <span data-ttu-id="ca67c-118">없음</span><span class="sxs-lookup"><span data-stu-id="ca67c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca67c-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ca67c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ca67c-120">요소</span><span class="sxs-lookup"><span data-stu-id="ca67c-120">Element</span></span>|<span data-ttu-id="ca67c-121">설명</span><span class="sxs-lookup"><span data-stu-id="ca67c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca67c-122">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="ca67c-122">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="ca67c-123">ExposedMethod > 요소의 컬렉션 [ \<](exposedmethod.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-123">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca67c-124">설명</span><span class="sxs-lookup"><span data-stu-id="ca67c-124">Remarks</span></span>  
 <span data-ttu-id="ca67c-125">COM+ 통합 구성 도구(ComSvcConfig.exe)는 COM 인터페이스의 특정 메서드를 생성된 서비스 계약에 나타나도록 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-125">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="ca67c-126">예를 들어, 다음 명령을 사용하여 생성된 서비스 계약에 `IFinances`.Financial 구성 요소의 `ItemOrders` COM 인터페이스에 있는 명명된 메서드 3개를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-126">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="ca67c-127">Comsvcconfig.exe를 실행 하면 앞에서 설명한 메서드 [ \<를 exposedMethod >](exposedmethod.md) 요소로 나열 하는 다음 서비스 계약이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-127">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="ca67c-128">서비스 초기화 시 런타임에서는 [ \<exposedMethod >](exposedmethod.md) 요소 목록에 포함 된 메서드만 반영 하 고 추가 하 여 서비스 계약을 생성 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-128">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="ca67c-129">서비스 계약에 포함되지 않은 모든 인터페이스 메서드에 대해서는 추적이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca67c-129">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca67c-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca67c-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="ca67c-131">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="ca67c-131">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="ca67c-132">COM+ 애플리케이션과 통합</span><span class="sxs-lookup"><span data-stu-id="ca67c-132">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ca67c-133">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ca67c-133">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
