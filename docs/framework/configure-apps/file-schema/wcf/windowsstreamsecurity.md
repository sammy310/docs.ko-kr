---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735890"
---
# \<windowsStreamSecurity>
<span data-ttu-id="7a701-101">사용자 지정의 바인딩에 대한 Windows 스트림 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-101">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="7a701-102">구문</span><span class="sxs-lookup"><span data-stu-id="7a701-102">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a701-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7a701-103">Attributes and Elements</span></span>  
 <span data-ttu-id="7a701-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a701-105">특성</span><span class="sxs-lookup"><span data-stu-id="7a701-105">Attributes</span></span>  
  
|<span data-ttu-id="7a701-106">attribute</span><span class="sxs-lookup"><span data-stu-id="7a701-106">Attribute</span></span>|<span data-ttu-id="7a701-107">Description</span><span class="sxs-lookup"><span data-stu-id="7a701-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a701-108">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="7a701-108">protectionLevel</span></span>|<span data-ttu-id="7a701-109">메시지 보안 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-109">Defines message-level security.</span></span> <span data-ttu-id="7a701-110">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-110">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="7a701-111">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-111">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="7a701-112">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7a701-113">-없음: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-113">-   None: No protection.</span></span><br /><span data-ttu-id="7a701-114">-서명: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-114">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="7a701-115">-EncryptAndSign: 메시지는 서명 되 고 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-115">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="7a701-116">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-116">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="7a701-117">이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-117">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a701-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7a701-118">Child Elements</span></span>  
 <span data-ttu-id="7a701-119">None</span><span class="sxs-lookup"><span data-stu-id="7a701-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a701-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7a701-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a701-121">요소</span><span class="sxs-lookup"><span data-stu-id="7a701-121">Element</span></span>|<span data-ttu-id="7a701-122">Description</span><span class="sxs-lookup"><span data-stu-id="7a701-122">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="7a701-123">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a701-124">설명</span><span class="sxs-lookup"><span data-stu-id="7a701-124">Remarks</span></span>  
 <span data-ttu-id="7a701-125">TCP 및 명명된 파이프와 같은 스트림 지향 프로토콜을 사용하는 전송은 스트림 기반 전송 업그레이드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-125">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="7a701-126">특히 WCF는 보안 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-126">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="7a701-127">이 전송 보안의 구성은이 구성 요소 뿐만 아니라 [\<sslStreamSecurity>](sslstreamsecurity.md) 사용자 지정 바인딩에 구성 및 추가 될 수 있는에 의해 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a701-127">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a701-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a701-128">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="7a701-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="7a701-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7a701-130">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="7a701-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7a701-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="7a701-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
