---
title: <webHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: b9efc732832a8862373b14f657796a59fb52c1a1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162116"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="9d110-102">\<webHttpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="9d110-102">\<transport> of \<webHttpBinding></span></span>

<span data-ttu-id="9d110-103">HTTP 요청을 수신하도록 구성된 서비스 엔드포인트의 전송 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="9d110-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d110-104">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="9d110-105">형식</span><span class="sxs-lookup"><span data-stu-id="9d110-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d110-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9d110-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9d110-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d110-108">특성</span><span class="sxs-lookup"><span data-stu-id="9d110-108">Attributes</span></span>  
  
|<span data-ttu-id="9d110-109">attribute</span><span class="sxs-lookup"><span data-stu-id="9d110-109">Attribute</span></span>|<span data-ttu-id="9d110-110">설명</span><span class="sxs-lookup"><span data-stu-id="9d110-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="9d110-111">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9d110-112">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="9d110-113">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9d110-114">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="9d110-115">다이제스트 또는 기본 인증을 위한 인증 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9d110-116">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9d110-117">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="9d110-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9d110-118">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="9d110-119">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="9d110-120">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9d110-121">1. Never – 정책이 적용 되지 않습니다 (확장 된 보호를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9d110-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9d110-122">2. 지원 됨 – 클라이언트에서 확장 된 보호를 지 원하는 경우에만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9d110-123">3. 항상 – 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9d110-124">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9d110-125">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="9d110-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9d110-126">Value</span><span class="sxs-lookup"><span data-stu-id="9d110-126">Value</span></span>|<span data-ttu-id="9d110-127">설명</span><span class="sxs-lookup"><span data-stu-id="9d110-127">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="9d110-128">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-128">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="9d110-129">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-129">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="9d110-130">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-130">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="9d110-131">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-131">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="9d110-132">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-132">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="9d110-133">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-133">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9d110-134">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="9d110-134">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9d110-135">Value</span><span class="sxs-lookup"><span data-stu-id="9d110-135">Value</span></span>|<span data-ttu-id="9d110-136">설명</span><span class="sxs-lookup"><span data-stu-id="9d110-136">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="9d110-137">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-137">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="9d110-138">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-138">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="9d110-139">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-139">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="9d110-140">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-140">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="9d110-141">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d110-141">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d110-142">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9d110-142">Child Elements</span></span>  

 <span data-ttu-id="9d110-143">없음</span><span class="sxs-lookup"><span data-stu-id="9d110-143">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d110-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9d110-144">Parent Elements</span></span>  
  
|<span data-ttu-id="9d110-145">요소</span><span class="sxs-lookup"><span data-stu-id="9d110-145">Element</span></span>|<span data-ttu-id="9d110-146">설명</span><span class="sxs-lookup"><span data-stu-id="9d110-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|<span data-ttu-id="9d110-147">요소의 보안 기능을 나타냅니다 [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9d110-147">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d110-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d110-148">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="9d110-149">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9d110-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9d110-150">바인딩하</span><span class="sxs-lookup"><span data-stu-id="9d110-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9d110-151">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="9d110-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9d110-152">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9d110-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="9d110-153">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="9d110-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
