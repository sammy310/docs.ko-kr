---
description: 다음에 대해 자세히 알아보세요. <windowsStreamSecurity>
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: c623dc23ca67d0341b66a2a4d97de564be77dcc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682399"
---
# \<windowsStreamSecurity>

<span data-ttu-id="5329b-102">사용자 지정의 바인딩에 대한 Windows 스트림 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="5329b-103">구문</span><span class="sxs-lookup"><span data-stu-id="5329b-103">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5329b-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5329b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5329b-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5329b-106">특성</span><span class="sxs-lookup"><span data-stu-id="5329b-106">Attributes</span></span>  
  
|<span data-ttu-id="5329b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="5329b-107">Attribute</span></span>|<span data-ttu-id="5329b-108">설명</span><span class="sxs-lookup"><span data-stu-id="5329b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5329b-109">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="5329b-109">protectionLevel</span></span>|<span data-ttu-id="5329b-110">메시지 보안 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-110">Defines message-level security.</span></span> <span data-ttu-id="5329b-111">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-111">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="5329b-112">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-112">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="5329b-113">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5329b-114">-없음: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-114">-   None: No protection.</span></span><br /><span data-ttu-id="5329b-115">-서명: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-115">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="5329b-116">-EncryptAndSign: 메시지는 서명 되 고 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-116">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="5329b-117">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-117">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="5329b-118">이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-118">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5329b-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5329b-119">Child Elements</span></span>  

 <span data-ttu-id="5329b-120">없음</span><span class="sxs-lookup"><span data-stu-id="5329b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5329b-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5329b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5329b-122">요소</span><span class="sxs-lookup"><span data-stu-id="5329b-122">Element</span></span>|<span data-ttu-id="5329b-123">설명</span><span class="sxs-lookup"><span data-stu-id="5329b-123">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="5329b-124">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5329b-125">설명</span><span class="sxs-lookup"><span data-stu-id="5329b-125">Remarks</span></span>  

 <span data-ttu-id="5329b-126">TCP 및 명명된 파이프와 같은 스트림 지향 프로토콜을 사용하는 전송은 스트림 기반 전송 업그레이드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-126">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="5329b-127">특히 WCF는 보안 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-127">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="5329b-128">이 전송 보안의 구성은이 구성 요소 뿐만 아니라 [\<sslStreamSecurity>](sslstreamsecurity.md) 사용자 지정 바인딩에 구성 및 추가 될 수 있는에 의해 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5329b-128">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5329b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5329b-129">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="5329b-130">바인딩</span><span class="sxs-lookup"><span data-stu-id="5329b-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5329b-131">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="5329b-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5329b-132">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5329b-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
