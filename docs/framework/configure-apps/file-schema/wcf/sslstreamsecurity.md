---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 5ed87adfb3963513602844fc69afce8f7994fa8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932432"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="5ea48-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="5ea48-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="5ea48-102">SSL 스트림을 사용한 채널 보안을 지원하는 사용자 지정 바인딩 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ea48-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="5ea48-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5ea48-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5ea48-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5ea48-104">\<bindings></span></span>  
<span data-ttu-id="5ea48-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5ea48-105">\<customBinding></span></span>  
<span data-ttu-id="5ea48-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="5ea48-106">\<binding></span></span>  
<span data-ttu-id="5ea48-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="5ea48-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ea48-108">구문</span><span class="sxs-lookup"><span data-stu-id="5ea48-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ea48-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5ea48-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5ea48-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea48-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ea48-111">특성</span><span class="sxs-lookup"><span data-stu-id="5ea48-111">Attributes</span></span>  
  
|<span data-ttu-id="5ea48-112">특성</span><span class="sxs-lookup"><span data-stu-id="5ea48-112">Attribute</span></span>|<span data-ttu-id="5ea48-113">설명</span><span class="sxs-lookup"><span data-stu-id="5ea48-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ea48-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="5ea48-114">requireClientCertificate</span></span>|<span data-ttu-id="5ea48-115">이 바인딩에 클라이언트 인증서가 필요한지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5ea48-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="5ea48-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5ea48-116">The default is `false`.</span></span>|  
|<span data-ttu-id="5ea48-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="5ea48-117">sslProtocols</span></span>|<span data-ttu-id="5ea48-118">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5ea48-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="5ea48-119">기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12입니다.</span><span class="sxs-lookup"><span data-stu-id="5ea48-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ea48-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5ea48-120">Child Elements</span></span>  
 <span data-ttu-id="5ea48-121">없음</span><span class="sxs-lookup"><span data-stu-id="5ea48-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ea48-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5ea48-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5ea48-123">요소</span><span class="sxs-lookup"><span data-stu-id="5ea48-123">Element</span></span>|<span data-ttu-id="5ea48-124">설명</span><span class="sxs-lookup"><span data-stu-id="5ea48-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ea48-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="5ea48-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="5ea48-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea48-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ea48-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ea48-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="5ea48-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="5ea48-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5ea48-129">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="5ea48-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5ea48-130">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5ea48-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5ea48-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5ea48-131">\<customBinding></span></span>](custombinding.md)
