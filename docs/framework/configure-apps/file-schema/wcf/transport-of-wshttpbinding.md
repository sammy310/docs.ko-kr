---
title: <wsHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732743"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="7a934-102">\<wsHttpBinding의 \<전송 > ></span><span class="sxs-lookup"><span data-stu-id="7a934-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="7a934-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="7a934-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a934-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7a934-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="7a934-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7a934-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="7a934-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="7a934-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7a934-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="7a934-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="7a934-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7a934-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**security >** ](security-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7a934-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="7a934-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**전송 >**</span><span class="sxs-lookup"><span data-stu-id="7a934-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="7a934-111">구문</span><span class="sxs-lookup"><span data-stu-id="7a934-111">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="7a934-112">Type</span><span class="sxs-lookup"><span data-stu-id="7a934-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="7a934-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7a934-113">Attributes and Elements</span></span>

<span data-ttu-id="7a934-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7a934-115">특성</span><span class="sxs-lookup"><span data-stu-id="7a934-115">Attributes</span></span>

|<span data-ttu-id="7a934-116">특성</span><span class="sxs-lookup"><span data-stu-id="7a934-116">Attribute</span></span>|<span data-ttu-id="7a934-117">설명</span><span class="sxs-lookup"><span data-stu-id="7a934-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="7a934-118">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="7a934-119">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="7a934-120">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="7a934-121">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="7a934-122">다이제스트 또는 기본 인증에 대 한 인증 영역을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="7a934-123">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7a934-124">인증 영역은 최소한 인증을 수행 하는 호스트의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="7a934-125">또한 액세스 권한이 있는 사용자 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="7a934-126">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="7a934-127">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="7a934-128">1. Never – 정책이 적용 되지 않습니다 (확장 된 보호를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="7a934-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="7a934-129">2. 지원 됨 – 클라이언트에서 확장 된 보호를 지 원하는 경우에만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="7a934-130">3. 항상 – 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="7a934-131">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7a934-132">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="7a934-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="7a934-133">값</span><span class="sxs-lookup"><span data-stu-id="7a934-133">Value</span></span>|<span data-ttu-id="7a934-134">설명</span><span class="sxs-lookup"><span data-stu-id="7a934-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="7a934-135">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="7a934-136">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="7a934-137">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="7a934-138">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="7a934-139">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="7a934-140">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="7a934-141">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="7a934-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="7a934-142">값</span><span class="sxs-lookup"><span data-stu-id="7a934-142">Value</span></span>|<span data-ttu-id="7a934-143">설명</span><span class="sxs-lookup"><span data-stu-id="7a934-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="7a934-144">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="7a934-145">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="7a934-146">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="7a934-147">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="7a934-148">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="7a934-149">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7a934-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7a934-150">Child Elements</span></span>

<span data-ttu-id="7a934-151">없음.</span><span class="sxs-lookup"><span data-stu-id="7a934-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7a934-152">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7a934-152">Parent Elements</span></span>

|<span data-ttu-id="7a934-153">요소</span><span class="sxs-lookup"><span data-stu-id="7a934-153">Element</span></span>|<span data-ttu-id="7a934-154">설명</span><span class="sxs-lookup"><span data-stu-id="7a934-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7a934-155">\<security ></span><span class="sxs-lookup"><span data-stu-id="7a934-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="7a934-156">[\<wsHttpBinding >](wshttpbinding.md)의 보안 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a934-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="7a934-157">참조</span><span class="sxs-lookup"><span data-stu-id="7a934-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="7a934-158">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7a934-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7a934-159">바인딩</span><span class="sxs-lookup"><span data-stu-id="7a934-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7a934-160">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="7a934-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7a934-161">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="7a934-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7a934-162">\<binding ></span><span class="sxs-lookup"><span data-stu-id="7a934-162">\<binding></span></span>](bindings.md)
