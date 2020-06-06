---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152673"
---
# \<issuerTokenResolver>
<span data-ttu-id="e8229-101">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-101">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e8229-102">발급자 토큰 확인자는 들어오는 토큰과 메시지의 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-102">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="e8229-103">구문</span><span class="sxs-lookup"><span data-stu-id="e8229-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8229-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e8229-104">Attributes and Elements</span></span>  
 <span data-ttu-id="e8229-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8229-106">특성</span><span class="sxs-lookup"><span data-stu-id="e8229-106">Attributes</span></span>  
  
|<span data-ttu-id="e8229-107">attribute</span><span class="sxs-lookup"><span data-stu-id="e8229-107">Attribute</span></span>|<span data-ttu-id="e8229-108">Description</span><span class="sxs-lookup"><span data-stu-id="e8229-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8229-109">type</span><span class="sxs-lookup"><span data-stu-id="e8229-109">type</span></span>|<span data-ttu-id="e8229-110">발급자 토큰 확인자 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-110">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="e8229-111">클래스 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 또는 클래스에서 파생 되는 형식 이어야 합니다 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="e8229-111">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="e8229-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e8229-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8229-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8229-113">Child Elements</span></span>  
 <span data-ttu-id="e8229-114">None</span><span class="sxs-lookup"><span data-stu-id="e8229-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8229-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8229-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e8229-116">요소</span><span class="sxs-lookup"><span data-stu-id="e8229-116">Element</span></span>|<span data-ttu-id="e8229-117">Description</span><span class="sxs-lookup"><span data-stu-id="e8229-117">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e8229-118">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-118">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8229-119">설명</span><span class="sxs-lookup"><span data-stu-id="e8229-119">Remarks</span></span>  
 <span data-ttu-id="e8229-120">발급자 토큰 확인자는 들어오는 토큰과 메시지의 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-120">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e8229-121">서명을 확인 하는 데 사용 되는 암호화 자료를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-121">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="e8229-122">특성을 지정 해야 합니다 `type` .</span><span class="sxs-lookup"><span data-stu-id="e8229-122">You must specify the `type` attribute.</span></span> <span data-ttu-id="e8229-123">지정 된 형식은 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 이거나 클래스에서 파생 되는 사용자 지정 형식일 수 있습니다 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="e8229-123">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e8229-124">일부 토큰 처리기를 사용 하면 구성에서 발급자 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-124">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="e8229-125">개별 토큰 처리기의 설정은 보안 토큰 처리기 컬렉션에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-125">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8229-126">요소를 요소의 자식 요소로 지정 하는 것은 `<issuerTokenResolver>` [\<identityConfiguration>](identityconfiguration.md) 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-126">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e8229-127">`<securityTokenHandlerConfiguration>`요소의 설정은 요소의 설정을 재정의 `<identityConfiguration>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-127">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8229-128">예제</span><span class="sxs-lookup"><span data-stu-id="e8229-128">Example</span></span>  
 <span data-ttu-id="e8229-129">다음 XML에서는에서 파생 되는 사용자 지정 클래스를 기반으로 하는 발급자 토큰 확인자에 대 한 구성을 보여 줍니다 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="e8229-129">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="e8229-130">토큰 확인자는 `<AddAudienceKeyPair>` 클래스에 대해 정의 된 사용자 지정 구성 요소 ()에서 초기화 되는 대상 키 쌍의 사전을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-130">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="e8229-131">클래스는 메서드를 재정의 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> 하 여이 요소를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-131">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="e8229-132">재정의는 다음 예제에 나와 있습니다. 그러나 호출 하는 메서드는 간결 하 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8229-132">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="e8229-133">전체 예제는 샘플을 참조 `CustomToken` 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8229-133">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="e8229-134">예제</span><span class="sxs-lookup"><span data-stu-id="e8229-134">Example</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="e8229-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8229-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
