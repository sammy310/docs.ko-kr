---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: cddd9f0c1dda982c1795500723c21546bd58c92b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399093"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="9ebaa-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="9ebaa-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="9ebaa-102">사용자 지정의 바인딩에 대한 Windows 스트림 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="9ebaa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ebaa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ebaa-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9ebaa-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9ebaa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9ebaa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9ebaa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="9ebaa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="9ebaa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="9ebaa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9ebaa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="9ebaa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ebaa-109">구문</span><span class="sxs-lookup"><span data-stu-id="9ebaa-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ebaa-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9ebaa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ebaa-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ebaa-112">특성</span><span class="sxs-lookup"><span data-stu-id="9ebaa-112">Attributes</span></span>  
  
|<span data-ttu-id="9ebaa-113">특성</span><span class="sxs-lookup"><span data-stu-id="9ebaa-113">Attribute</span></span>|<span data-ttu-id="9ebaa-114">Description</span><span class="sxs-lookup"><span data-stu-id="9ebaa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ebaa-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="9ebaa-115">protectionLevel</span></span>|<span data-ttu-id="9ebaa-116">메시지 보안 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-116">Defines message-level security.</span></span> <span data-ttu-id="9ebaa-117">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="9ebaa-118">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="9ebaa-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9ebaa-120">없음을 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-120">-   None: No protection.</span></span><br /><span data-ttu-id="9ebaa-121">로그인 메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="9ebaa-122">-   EncryptAndSign: 메시지는 서명 되 고 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="9ebaa-123">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="9ebaa-124">이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ebaa-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9ebaa-125">Child Elements</span></span>  
 <span data-ttu-id="9ebaa-126">없음</span><span class="sxs-lookup"><span data-stu-id="9ebaa-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ebaa-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9ebaa-127">Parent Elements</span></span>  
  
|<span data-ttu-id="9ebaa-128">요소</span><span class="sxs-lookup"><span data-stu-id="9ebaa-128">Element</span></span>|<span data-ttu-id="9ebaa-129">설명</span><span class="sxs-lookup"><span data-stu-id="9ebaa-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ebaa-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ebaa-130">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="9ebaa-131">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ebaa-132">설명</span><span class="sxs-lookup"><span data-stu-id="9ebaa-132">Remarks</span></span>  
 <span data-ttu-id="9ebaa-133">TCP 및 명명된 파이프와 같은 스트림 지향 프로토콜을 사용하는 전송은 스트림 기반 전송 업그레이드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="9ebaa-134">특히 WCF는 보안 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="9ebaa-135">이 전송 보안의 구성은이 구성 요소 [ \<](sslstreamsecurity.md)뿐만 아니라 사용자 지정 바인딩에 구성 및 추가 될 수 있는 sslstreamsecurity >에 의해 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ebaa-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ebaa-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ebaa-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="9ebaa-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="9ebaa-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9ebaa-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="9ebaa-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9ebaa-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="9ebaa-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9ebaa-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9ebaa-140">\<customBinding></span></span>](custombinding.md)
