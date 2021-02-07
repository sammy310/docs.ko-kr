---
description: 다음에 대해 자세히 알아보세요. <exposedMethod>
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 7bf271ba03ee16c6a45726e2bcb522bf6f55d441
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664732"
---
# \<exposedMethod>

<span data-ttu-id="77ac6-102">COM+ 구성 요소의 인터페이스가 웹 서비스로 노출될 때 노출되는 COM+ 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="77ac6-103">구문</span><span class="sxs-lookup"><span data-stu-id="77ac6-103">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77ac6-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="77ac6-104">Attributes and Elements</span></span>  

 <span data-ttu-id="77ac6-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77ac6-106">특성</span><span class="sxs-lookup"><span data-stu-id="77ac6-106">Attributes</span></span>  
  
|<span data-ttu-id="77ac6-107">attribute</span><span class="sxs-lookup"><span data-stu-id="77ac6-107">Attribute</span></span>|<span data-ttu-id="77ac6-108">설명</span><span class="sxs-lookup"><span data-stu-id="77ac6-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77ac6-109">name</span><span class="sxs-lookup"><span data-stu-id="77ac6-109">name</span></span>|<span data-ttu-id="77ac6-110">COM+ 구성 요소의 인터페이스가 웹 서비스로 공개될 때 노출되는 COM+ 메서드를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-110">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77ac6-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="77ac6-111">Child Elements</span></span>  

 <span data-ttu-id="77ac6-112">없음</span><span class="sxs-lookup"><span data-stu-id="77ac6-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77ac6-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="77ac6-113">Parent Elements</span></span>  
  
|<span data-ttu-id="77ac6-114">요소</span><span class="sxs-lookup"><span data-stu-id="77ac6-114">Element</span></span>|<span data-ttu-id="77ac6-115">설명</span><span class="sxs-lookup"><span data-stu-id="77ac6-115">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="77ac6-116">[\<exposedMethod>](exposedmethod.md)요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-116">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77ac6-117">설명</span><span class="sxs-lookup"><span data-stu-id="77ac6-117">Remarks</span></span>  

 <span data-ttu-id="77ac6-118">COM+ 통합 구성 도구(ComSvcConfig.exe)는 COM 인터페이스의 특정 메서드를 생성된 서비스 계약에 나타나도록 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-118">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="77ac6-119">예를 들어, 다음 명령을 사용하여 생성된 서비스 계약에 `IFinances`.Financial 구성 요소의 `ItemOrders` COM 인터페이스에 있는 명명된 메서드 3개를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-119">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="77ac6-120">또한 ComSvcConfig.exe를 실행 하면 앞에서 설명한 메서드를 요소로 나열 하는 다음 서비스 계약이 생성 됩니다 [\<exposedMethod>](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="77ac6-120">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="77ac6-121">서비스 초기화 시 런타임에서는 요소 목록에 포함 된 메서드만 반영 하 고 추가 하 여 서비스 계약을 생성 하려고 시도 [\<exposedMethod>](exposedmethod.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-121">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="77ac6-122">서비스 계약에 포함되지 않은 모든 인터페이스 메서드에 대해서는 추적이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="77ac6-122">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ac6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77ac6-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="77ac6-124">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="77ac6-124">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="77ac6-125">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="77ac6-125">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
