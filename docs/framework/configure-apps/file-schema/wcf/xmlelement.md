---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398993"
---
# \<xmlElement>
<span data-ttu-id="15c42-101">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="15c42-102">구문</span><span class="sxs-lookup"><span data-stu-id="15c42-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15c42-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="15c42-103">Attributes and Elements</span></span>  
 <span data-ttu-id="15c42-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15c42-105">특성</span><span class="sxs-lookup"><span data-stu-id="15c42-105">Attributes</span></span>  
  
|<span data-ttu-id="15c42-106">attribute</span><span class="sxs-lookup"><span data-stu-id="15c42-106">Attribute</span></span>|<span data-ttu-id="15c42-107">Description</span><span class="sxs-lookup"><span data-stu-id="15c42-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15c42-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="15c42-108">xmlElement</span></span>|<span data-ttu-id="15c42-109">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15c42-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="15c42-110">Child Elements</span></span>  
 <span data-ttu-id="15c42-111">없음</span><span class="sxs-lookup"><span data-stu-id="15c42-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15c42-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="15c42-112">Parent Elements</span></span>  
  
|<span data-ttu-id="15c42-113">요소</span><span class="sxs-lookup"><span data-stu-id="15c42-113">Element</span></span>|<span data-ttu-id="15c42-114">Description</span><span class="sxs-lookup"><span data-stu-id="15c42-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="15c42-115">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-115">A collection of token request parameters.</span></span> <span data-ttu-id="15c42-116">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15c42-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15c42-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="15c42-118">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="15c42-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="15c42-119">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="15c42-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="15c42-120">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="15c42-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="15c42-121">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="15c42-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="15c42-122">바인딩</span><span class="sxs-lookup"><span data-stu-id="15c42-122">Bindings</span></span>](../../../wcf/bindings.md)
