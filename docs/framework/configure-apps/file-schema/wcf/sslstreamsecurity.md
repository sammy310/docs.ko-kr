---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204447"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="7d71a-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="7d71a-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="7d71a-102">SSL 스트림을 사용한 채널 보안을 지원하는 사용자 지정 바인딩 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d71a-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="7d71a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7d71a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="7d71a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7d71a-104">\<bindings></span></span>  
<span data-ttu-id="7d71a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7d71a-105">\<customBinding></span></span>  
<span data-ttu-id="7d71a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="7d71a-106">\<binding></span></span>  
<span data-ttu-id="7d71a-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="7d71a-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d71a-108">구문</span><span class="sxs-lookup"><span data-stu-id="7d71a-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d71a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7d71a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7d71a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d71a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d71a-111">특성</span><span class="sxs-lookup"><span data-stu-id="7d71a-111">Attributes</span></span>  
  
|<span data-ttu-id="7d71a-112">특성</span><span class="sxs-lookup"><span data-stu-id="7d71a-112">Attribute</span></span>|<span data-ttu-id="7d71a-113">설명</span><span class="sxs-lookup"><span data-stu-id="7d71a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d71a-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="7d71a-114">requireClientCertificate</span></span>|<span data-ttu-id="7d71a-115">이 바인딩에 클라이언트 인증서가 필요한지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d71a-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="7d71a-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="7d71a-116">The default is `false`.</span></span>|  
|<span data-ttu-id="7d71a-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="7d71a-117">sslProtocols</span></span>|<span data-ttu-id="7d71a-118">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d71a-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="7d71a-119">기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d71a-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d71a-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7d71a-120">Child Elements</span></span>  
 <span data-ttu-id="7d71a-121">없음</span><span class="sxs-lookup"><span data-stu-id="7d71a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d71a-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7d71a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7d71a-123">요소</span><span class="sxs-lookup"><span data-stu-id="7d71a-123">Element</span></span>|<span data-ttu-id="7d71a-124">설명</span><span class="sxs-lookup"><span data-stu-id="7d71a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d71a-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="7d71a-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7d71a-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d71a-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d71a-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d71a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="7d71a-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="7d71a-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7d71a-129">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="7d71a-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7d71a-130">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="7d71a-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7d71a-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7d71a-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
