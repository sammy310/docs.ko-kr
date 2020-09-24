---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: aa6bc7f5a94afc8a190d3d9d2d71ea8b38d8c25b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153575"
---
# \<sslStreamSecurity>

<span data-ttu-id="6e4f2-101">SSL 스트림을 사용한 채널 보안을 지원하는 사용자 지정 바인딩 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e4f2-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="6e4f2-102">구문</span><span class="sxs-lookup"><span data-stu-id="6e4f2-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e4f2-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6e4f2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6e4f2-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4f2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e4f2-105">특성</span><span class="sxs-lookup"><span data-stu-id="6e4f2-105">Attributes</span></span>  
  
|<span data-ttu-id="6e4f2-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6e4f2-106">Attribute</span></span>|<span data-ttu-id="6e4f2-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e4f2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e4f2-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="6e4f2-108">requireClientCertificate</span></span>|<span data-ttu-id="6e4f2-109">이 바인딩에 클라이언트 인증서가 필요한지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e4f2-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="6e4f2-110">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="6e4f2-110">The default is `false`.</span></span>|  
|<span data-ttu-id="6e4f2-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="6e4f2-111">sslProtocols</span></span>|<span data-ttu-id="6e4f2-112">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e4f2-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="6e4f2-113">기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12입니다.</span><span class="sxs-lookup"><span data-stu-id="6e4f2-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e4f2-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6e4f2-114">Child Elements</span></span>  

 <span data-ttu-id="6e4f2-115">없음</span><span class="sxs-lookup"><span data-stu-id="6e4f2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e4f2-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6e4f2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6e4f2-117">요소</span><span class="sxs-lookup"><span data-stu-id="6e4f2-117">Element</span></span>|<span data-ttu-id="6e4f2-118">설명</span><span class="sxs-lookup"><span data-stu-id="6e4f2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="6e4f2-119">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4f2-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e4f2-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e4f2-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="6e4f2-121">바인딩하</span><span class="sxs-lookup"><span data-stu-id="6e4f2-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6e4f2-122">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="6e4f2-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6e4f2-123">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="6e4f2-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
