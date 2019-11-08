---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738599"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="19613-101">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="19613-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="19613-102">SSL 스트림을 사용한 채널 보안을 지원하는 사용자 지정 바인딩 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19613-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="19613-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19613-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19613-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="19613-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="19613-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="19613-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="19613-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="19613-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="19613-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="19613-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="19613-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sslStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="19613-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19613-109">구문</span><span class="sxs-lookup"><span data-stu-id="19613-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19613-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19613-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19613-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19613-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19613-112">특성</span><span class="sxs-lookup"><span data-stu-id="19613-112">Attributes</span></span>  
  
|<span data-ttu-id="19613-113">특성</span><span class="sxs-lookup"><span data-stu-id="19613-113">Attribute</span></span>|<span data-ttu-id="19613-114">설명</span><span class="sxs-lookup"><span data-stu-id="19613-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19613-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="19613-115">requireClientCertificate</span></span>|<span data-ttu-id="19613-116">이 바인딩에 클라이언트 인증서가 필요한지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="19613-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="19613-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="19613-117">The default is `false`.</span></span>|  
|<span data-ttu-id="19613-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="19613-118">sslProtocols</span></span>|<span data-ttu-id="19613-119">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="19613-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="19613-120">기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12입니다.</span><span class="sxs-lookup"><span data-stu-id="19613-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19613-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19613-121">Child Elements</span></span>  
 <span data-ttu-id="19613-122">없음.</span><span class="sxs-lookup"><span data-stu-id="19613-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19613-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19613-123">Parent Elements</span></span>  
  
|<span data-ttu-id="19613-124">요소</span><span class="sxs-lookup"><span data-stu-id="19613-124">Element</span></span>|<span data-ttu-id="19613-125">설명</span><span class="sxs-lookup"><span data-stu-id="19613-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19613-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="19613-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="19613-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19613-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19613-128">참조</span><span class="sxs-lookup"><span data-stu-id="19613-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="19613-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="19613-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="19613-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="19613-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="19613-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="19613-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="19613-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="19613-132">\<customBinding></span></span>](custombinding.md)
