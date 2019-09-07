---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 9b7092878c604142c29dcd8d27e3c458d203f9fa
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399526"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="b8921-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="b8921-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="b8921-102">SSL 스트림을 사용한 채널 보안을 지원하는 사용자 지정 바인딩 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8921-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="b8921-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8921-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b8921-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b8921-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b8921-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b8921-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b8921-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b8921-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b8921-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="b8921-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b8921-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sslStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="b8921-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8921-109">구문</span><span class="sxs-lookup"><span data-stu-id="b8921-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8921-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b8921-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b8921-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8921-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8921-112">특성</span><span class="sxs-lookup"><span data-stu-id="b8921-112">Attributes</span></span>  
  
|<span data-ttu-id="b8921-113">특성</span><span class="sxs-lookup"><span data-stu-id="b8921-113">Attribute</span></span>|<span data-ttu-id="b8921-114">Description</span><span class="sxs-lookup"><span data-stu-id="b8921-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8921-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="b8921-115">requireClientCertificate</span></span>|<span data-ttu-id="b8921-116">이 바인딩에 클라이언트 인증서가 필요한지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b8921-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="b8921-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b8921-117">The default is `false`.</span></span>|  
|<span data-ttu-id="b8921-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="b8921-118">sslProtocols</span></span>|<span data-ttu-id="b8921-119">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b8921-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="b8921-120">기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12입니다.</span><span class="sxs-lookup"><span data-stu-id="b8921-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8921-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b8921-121">Child Elements</span></span>  
 <span data-ttu-id="b8921-122">없음</span><span class="sxs-lookup"><span data-stu-id="b8921-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8921-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b8921-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b8921-124">요소</span><span class="sxs-lookup"><span data-stu-id="b8921-124">Element</span></span>|<span data-ttu-id="b8921-125">설명</span><span class="sxs-lookup"><span data-stu-id="b8921-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8921-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="b8921-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b8921-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8921-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8921-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="b8921-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="b8921-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="b8921-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b8921-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="b8921-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b8921-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b8921-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b8921-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b8921-132">\<customBinding></span></span>](custombinding.md)
