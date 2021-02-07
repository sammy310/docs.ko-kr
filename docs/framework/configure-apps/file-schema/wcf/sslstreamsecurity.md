---
description: 다음에 대해 자세히 알아보세요. <sslStreamSecurity>
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 77e08deb5263e330ead5df21ed1ef2dddbba28ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682698"
---
# \<sslStreamSecurity>

<span data-ttu-id="f9558-102">SSL 스트림을 사용한 채널 보안을 지원하는 사용자 지정 바인딩 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9558-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="f9558-103">구문</span><span class="sxs-lookup"><span data-stu-id="f9558-103">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9558-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f9558-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f9558-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9558-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9558-106">특성</span><span class="sxs-lookup"><span data-stu-id="f9558-106">Attributes</span></span>  
  
|<span data-ttu-id="f9558-107">attribute</span><span class="sxs-lookup"><span data-stu-id="f9558-107">Attribute</span></span>|<span data-ttu-id="f9558-108">설명</span><span class="sxs-lookup"><span data-stu-id="f9558-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9558-109">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="f9558-109">requireClientCertificate</span></span>|<span data-ttu-id="f9558-110">이 바인딩에 클라이언트 인증서가 필요한지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f9558-110">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="f9558-111">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f9558-111">The default is `false`.</span></span>|  
|<span data-ttu-id="f9558-112">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="f9558-112">sslProtocols</span></span>|<span data-ttu-id="f9558-113">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f9558-113">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="f9558-114">기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12입니다.</span><span class="sxs-lookup"><span data-stu-id="f9558-114">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9558-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f9558-115">Child Elements</span></span>  

 <span data-ttu-id="f9558-116">없음</span><span class="sxs-lookup"><span data-stu-id="f9558-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9558-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f9558-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f9558-118">요소</span><span class="sxs-lookup"><span data-stu-id="f9558-118">Element</span></span>|<span data-ttu-id="f9558-119">설명</span><span class="sxs-lookup"><span data-stu-id="f9558-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f9558-120">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9558-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9558-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9558-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="f9558-122">바인딩</span><span class="sxs-lookup"><span data-stu-id="f9558-122">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f9558-123">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="f9558-123">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f9558-124">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="f9558-124">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
