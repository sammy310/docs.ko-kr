---
description: 다음에 대해 자세히 알아보세요. <xmlElement>
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 891f1a95c1f6a79127d48a1572bc805574225530
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682009"
---
# \<xmlElement>

<span data-ttu-id="771b2-102">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="771b2-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="771b2-103">구문</span><span class="sxs-lookup"><span data-stu-id="771b2-103">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="771b2-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="771b2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="771b2-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="771b2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="771b2-106">특성</span><span class="sxs-lookup"><span data-stu-id="771b2-106">Attributes</span></span>  
  
|<span data-ttu-id="771b2-107">attribute</span><span class="sxs-lookup"><span data-stu-id="771b2-107">Attribute</span></span>|<span data-ttu-id="771b2-108">설명</span><span class="sxs-lookup"><span data-stu-id="771b2-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="771b2-109">xmlElement</span><span class="sxs-lookup"><span data-stu-id="771b2-109">xmlElement</span></span>|<span data-ttu-id="771b2-110">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="771b2-110">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="771b2-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="771b2-111">Child Elements</span></span>  

 <span data-ttu-id="771b2-112">없음</span><span class="sxs-lookup"><span data-stu-id="771b2-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="771b2-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="771b2-113">Parent Elements</span></span>  
  
|<span data-ttu-id="771b2-114">요소</span><span class="sxs-lookup"><span data-stu-id="771b2-114">Element</span></span>|<span data-ttu-id="771b2-115">설명</span><span class="sxs-lookup"><span data-stu-id="771b2-115">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="771b2-116">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="771b2-116">A collection of token request parameters.</span></span> <span data-ttu-id="771b2-117">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="771b2-117">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="771b2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="771b2-118">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="771b2-119">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="771b2-119">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="771b2-120">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="771b2-120">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="771b2-121">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="771b2-121">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="771b2-122">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="771b2-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="771b2-123">바인딩</span><span class="sxs-lookup"><span data-stu-id="771b2-123">Bindings</span></span>](../../../wcf/bindings.md)
