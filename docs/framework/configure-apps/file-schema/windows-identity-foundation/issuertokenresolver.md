---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152673"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="bea27-101">\<발행자토큰해결러></span><span class="sxs-lookup"><span data-stu-id="bea27-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="bea27-102">토큰 처리기 컬렉션의 처리기에서 사용되는 발급자 토큰 확인자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="bea27-103">발급자 토큰 확인기는 들어오는 토큰 및 메시지에 서명 토큰을 해결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="bea27-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bea27-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bea27-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="bea27-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="bea27-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bea27-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="bea27-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="bea27-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="bea27-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기구성>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bea27-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="bea27-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<발행자토큰해결러>**</span><span class="sxs-lookup"><span data-stu-id="bea27-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea27-110">구문</span><span class="sxs-lookup"><span data-stu-id="bea27-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bea27-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bea27-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bea27-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bea27-113">특성</span><span class="sxs-lookup"><span data-stu-id="bea27-113">Attributes</span></span>  
  
|<span data-ttu-id="bea27-114">attribute</span><span class="sxs-lookup"><span data-stu-id="bea27-114">Attribute</span></span>|<span data-ttu-id="bea27-115">Description</span><span class="sxs-lookup"><span data-stu-id="bea27-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bea27-116">type</span><span class="sxs-lookup"><span data-stu-id="bea27-116">type</span></span>|<span data-ttu-id="bea27-117">발급자 토큰 확인자의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="bea27-118"><xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스 또는 클래스에서 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 파생 되는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="bea27-119">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bea27-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bea27-120">Child Elements</span></span>  
 <span data-ttu-id="bea27-121">None</span><span class="sxs-lookup"><span data-stu-id="bea27-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bea27-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bea27-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bea27-123">요소</span><span class="sxs-lookup"><span data-stu-id="bea27-123">Element</span></span>|<span data-ttu-id="bea27-124">Description</span><span class="sxs-lookup"><span data-stu-id="bea27-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bea27-125">\<보안토큰처리기구성></span><span class="sxs-lookup"><span data-stu-id="bea27-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="bea27-126">보안 토큰 처리기 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bea27-127">설명</span><span class="sxs-lookup"><span data-stu-id="bea27-127">Remarks</span></span>  
 <span data-ttu-id="bea27-128">발급자 토큰 확인기는 들어오는 토큰 및 메시지에 서명 토큰을 해결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="bea27-129">서명을 확인하는 데 사용되는 암호화 자료를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="bea27-130">특성을 `type` 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="bea27-131">지정된 형식은 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스에서 파생되는 사용자 지정 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="bea27-132">일부 토큰 처리기를 사용하면 구성에서 발급자 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="bea27-133">개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정된 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bea27-134">idConfiguration>요소의 자식 요소로 요소를 지정 하는 데 사용 하지 않습니다. [ \<](identityconfiguration.md) `<issuerTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="bea27-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="bea27-135">요소의 `<securityTokenHandlerConfiguration>` 설정은 요소의 `<identityConfiguration>` 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bea27-136">예제</span><span class="sxs-lookup"><span data-stu-id="bea27-136">Example</span></span>  
 <span data-ttu-id="bea27-137">다음 XML은 에서 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>파생된 사용자 지정 클래스를 기반으로 하는 발급자 토큰 확인자의 구성을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="bea27-138">토큰 확인프로그램은 클래스에 정의된 사용자 지정 구성 요소()`<AddAudienceKeyPair>`에서 초기화되는 잠재고객 키 쌍의 사전을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="bea27-139">클래스는 이 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> 요소를 처리하는 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="bea27-140">재정의는 다음 예제에 나와 있습니다. 그러나 호출하는 메서드는 간결성을 위해 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bea27-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="bea27-141">전체 예제는 `CustomToken` 샘플을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bea27-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="bea27-142">예제</span><span class="sxs-lookup"><span data-stu-id="bea27-142">Example</span></span>
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="bea27-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bea27-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
