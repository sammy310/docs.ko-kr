---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113635"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="de00b-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="de00b-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="de00b-102">사용자 지정의 바인딩에 대한 Windows 스트림 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="de00b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="de00b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="de00b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="de00b-104">\<bindings></span></span>  
<span data-ttu-id="de00b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="de00b-105">\<customBinding></span></span>  
<span data-ttu-id="de00b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="de00b-106">\<binding></span></span>  
<span data-ttu-id="de00b-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="de00b-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de00b-108">구문</span><span class="sxs-lookup"><span data-stu-id="de00b-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de00b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="de00b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="de00b-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de00b-111">특성</span><span class="sxs-lookup"><span data-stu-id="de00b-111">Attributes</span></span>  
  
|<span data-ttu-id="de00b-112">특성</span><span class="sxs-lookup"><span data-stu-id="de00b-112">Attribute</span></span>|<span data-ttu-id="de00b-113">설명</span><span class="sxs-lookup"><span data-stu-id="de00b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de00b-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="de00b-114">protectionLevel</span></span>|<span data-ttu-id="de00b-115">메시지 보안 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-115">Defines message-level security.</span></span> <span data-ttu-id="de00b-116">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="de00b-117">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="de00b-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="de00b-119">-None. 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-119">-   None: No protection.</span></span><br /><span data-ttu-id="de00b-120">기호: 메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="de00b-121">-   EncryptAndSign: 메시지 서명 및 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="de00b-122">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="de00b-123">이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de00b-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="de00b-124">Child Elements</span></span>  
 <span data-ttu-id="de00b-125">없음</span><span class="sxs-lookup"><span data-stu-id="de00b-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de00b-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="de00b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="de00b-127">요소</span><span class="sxs-lookup"><span data-stu-id="de00b-127">Element</span></span>|<span data-ttu-id="de00b-128">설명</span><span class="sxs-lookup"><span data-stu-id="de00b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de00b-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="de00b-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="de00b-130">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de00b-131">설명</span><span class="sxs-lookup"><span data-stu-id="de00b-131">Remarks</span></span>  
 <span data-ttu-id="de00b-132">TCP 및 명명된 파이프와 같은 스트림 지향 프로토콜을 사용하는 전송은 스트림 기반 전송 업그레이드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="de00b-133">특히 WCF는 보안 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de00b-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="de00b-134">이 전송 보안의 구성은이 구성 요소에 캡슐화 [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), 구성 및 사용자 지정 바인딩에 추가할 수 있는</span><span class="sxs-lookup"><span data-stu-id="de00b-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de00b-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="de00b-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="de00b-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="de00b-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="de00b-137">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="de00b-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="de00b-138">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="de00b-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="de00b-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="de00b-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
