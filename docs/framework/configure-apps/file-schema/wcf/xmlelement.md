---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230501"
---
# <a name="xmlelement"></a><span data-ttu-id="036c8-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="036c8-101">\<xmlElement></span></span>
<span data-ttu-id="036c8-102">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="036c8-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="036c8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="036c8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="036c8-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="036c8-104">\<bindings></span></span>  
<span data-ttu-id="036c8-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="036c8-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="036c8-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="036c8-106">\<binding></span></span>  
<span data-ttu-id="036c8-107">\<security></span><span class="sxs-lookup"><span data-stu-id="036c8-107">\<security></span></span>  
<span data-ttu-id="036c8-108">\<message></span><span class="sxs-lookup"><span data-stu-id="036c8-108">\<message></span></span>  
<span data-ttu-id="036c8-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="036c8-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="036c8-110">구문</span><span class="sxs-lookup"><span data-stu-id="036c8-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="036c8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="036c8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="036c8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="036c8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="036c8-113">특성</span><span class="sxs-lookup"><span data-stu-id="036c8-113">Attributes</span></span>  
  
|<span data-ttu-id="036c8-114">특성</span><span class="sxs-lookup"><span data-stu-id="036c8-114">Attribute</span></span>|<span data-ttu-id="036c8-115">설명</span><span class="sxs-lookup"><span data-stu-id="036c8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="036c8-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="036c8-116">xmlElement</span></span>|<span data-ttu-id="036c8-117">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="036c8-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="036c8-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="036c8-118">Child Elements</span></span>  
 <span data-ttu-id="036c8-119">없음</span><span class="sxs-lookup"><span data-stu-id="036c8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="036c8-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="036c8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="036c8-121">요소</span><span class="sxs-lookup"><span data-stu-id="036c8-121">Element</span></span>|<span data-ttu-id="036c8-122">설명</span><span class="sxs-lookup"><span data-stu-id="036c8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="036c8-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="036c8-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="036c8-124">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="036c8-124">A collection of token request parameters.</span></span> <span data-ttu-id="036c8-125">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="036c8-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="036c8-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="036c8-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="036c8-127">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="036c8-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="036c8-128">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="036c8-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="036c8-129">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="036c8-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="036c8-130">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="036c8-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="036c8-131">바인딩</span><span class="sxs-lookup"><span data-stu-id="036c8-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
