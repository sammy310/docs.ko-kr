---
title: <wsHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732743"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="46ea6-102">\<wsHttpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="46ea6-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="46ea6-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-103">Defines authentication settings for the HTTP transport.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  

## <a name="syntax"></a><span data-ttu-id="46ea6-104">구문</span><span class="sxs-lookup"><span data-stu-id="46ea6-104">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="46ea6-105">Type</span><span class="sxs-lookup"><span data-stu-id="46ea6-105">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="46ea6-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="46ea6-106">Attributes and Elements</span></span>

<span data-ttu-id="46ea6-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="46ea6-108">특성</span><span class="sxs-lookup"><span data-stu-id="46ea6-108">Attributes</span></span>

|<span data-ttu-id="46ea6-109">attribute</span><span class="sxs-lookup"><span data-stu-id="46ea6-109">Attribute</span></span>|<span data-ttu-id="46ea6-110">Description</span><span class="sxs-lookup"><span data-stu-id="46ea6-110">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="46ea6-111">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="46ea6-112">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="46ea6-113">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="46ea6-114">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="46ea6-115">다이제스트 또는 기본 인증을 위한 인증 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="46ea6-116">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="46ea6-117">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="46ea6-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="46ea6-118">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="46ea6-119">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="46ea6-120">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="46ea6-121">1. Never – 정책이 적용 되지 않습니다 (확장 된 보호를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="46ea6-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="46ea6-122">2. 지원 됨 – 클라이언트에서 확장 된 보호를 지 원하는 경우에만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="46ea6-123">3. 항상 – 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="46ea6-124">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="46ea6-125">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="46ea6-125">clientCredentialType Attribute</span></span>

|<span data-ttu-id="46ea6-126">값</span><span class="sxs-lookup"><span data-stu-id="46ea6-126">Value</span></span>|<span data-ttu-id="46ea6-127">Description</span><span class="sxs-lookup"><span data-stu-id="46ea6-127">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="46ea6-128">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-128">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="46ea6-129">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-129">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="46ea6-130">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-130">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="46ea6-131">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-131">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="46ea6-132">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-132">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="46ea6-133">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-133">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="46ea6-134">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="46ea6-134">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="46ea6-135">값</span><span class="sxs-lookup"><span data-stu-id="46ea6-135">Value</span></span>|<span data-ttu-id="46ea6-136">Description</span><span class="sxs-lookup"><span data-stu-id="46ea6-136">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="46ea6-137">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-137">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="46ea6-138">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-138">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="46ea6-139">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-139">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="46ea6-140">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-140">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="46ea6-141">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-141">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="46ea6-142">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="46ea6-142">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="46ea6-143">자식 요소</span><span class="sxs-lookup"><span data-stu-id="46ea6-143">Child Elements</span></span>

<span data-ttu-id="46ea6-144">없음</span><span class="sxs-lookup"><span data-stu-id="46ea6-144">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="46ea6-145">부모 요소</span><span class="sxs-lookup"><span data-stu-id="46ea6-145">Parent Elements</span></span>

|<span data-ttu-id="46ea6-146">요소</span><span class="sxs-lookup"><span data-stu-id="46ea6-146">Element</span></span>|<span data-ttu-id="46ea6-147">Description</span><span class="sxs-lookup"><span data-stu-id="46ea6-147">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="46ea6-148">의 보안 기능을 나타냅니다 [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="46ea6-148">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="46ea6-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46ea6-149">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="46ea6-150">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="46ea6-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="46ea6-151">바인딩</span><span class="sxs-lookup"><span data-stu-id="46ea6-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="46ea6-152">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="46ea6-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="46ea6-153">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="46ea6-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
