---
title: <ws2007HttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: a1540b53d4af76141c1daee60a6bddbbecd9d6da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153870"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="3ea37-102">\<전송 >의 \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3ea37-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="3ea37-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="3ea37-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3ea37-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3ea37-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3ea37-105">\<bindings></span></span>  
<span data-ttu-id="3ea37-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="3ea37-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="3ea37-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3ea37-107">\<binding></span></span>  
<span data-ttu-id="3ea37-108">\<security></span><span class="sxs-lookup"><span data-stu-id="3ea37-108">\<security></span></span>  
<span data-ttu-id="3ea37-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="3ea37-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ea37-110">구문</span><span class="sxs-lookup"><span data-stu-id="3ea37-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="3ea37-111">형식</span><span class="sxs-lookup"><span data-stu-id="3ea37-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ea37-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3ea37-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3ea37-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ea37-114">특성</span><span class="sxs-lookup"><span data-stu-id="3ea37-114">Attributes</span></span>  
  
|<span data-ttu-id="3ea37-115">특성</span><span class="sxs-lookup"><span data-stu-id="3ea37-115">Attribute</span></span>|<span data-ttu-id="3ea37-116">설명</span><span class="sxs-lookup"><span data-stu-id="3ea37-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="3ea37-117">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="3ea37-118">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="3ea37-119">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="3ea37-120">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="3ea37-121">다이제스트 또는 기본 인증을 위한 인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="3ea37-122">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="3ea37-123">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="3ea37-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="3ea37-124">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="3ea37-125">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="3ea37-126">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="3ea37-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3ea37-127">값</span><span class="sxs-lookup"><span data-stu-id="3ea37-127">Value</span></span>|<span data-ttu-id="3ea37-128">설명</span><span class="sxs-lookup"><span data-stu-id="3ea37-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ea37-129">없음</span><span class="sxs-lookup"><span data-stu-id="3ea37-129">None</span></span>|<span data-ttu-id="3ea37-130">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-130">Security is disabled.</span></span>|  
|<span data-ttu-id="3ea37-131">Basic</span><span class="sxs-lookup"><span data-stu-id="3ea37-131">Basic</span></span>|<span data-ttu-id="3ea37-132">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="3ea37-133">Digest</span><span class="sxs-lookup"><span data-stu-id="3ea37-133">Digest</span></span>|<span data-ttu-id="3ea37-134">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="3ea37-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3ea37-135">Ntlm</span></span>|<span data-ttu-id="3ea37-136">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="3ea37-137">Windows</span><span class="sxs-lookup"><span data-stu-id="3ea37-137">Windows</span></span>|<span data-ttu-id="3ea37-138">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="3ea37-139">인증서</span><span class="sxs-lookup"><span data-stu-id="3ea37-139">Certificate</span></span>|<span data-ttu-id="3ea37-140">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="3ea37-141">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="3ea37-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3ea37-142">값</span><span class="sxs-lookup"><span data-stu-id="3ea37-142">Value</span></span>|<span data-ttu-id="3ea37-143">설명</span><span class="sxs-lookup"><span data-stu-id="3ea37-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ea37-144">없음</span><span class="sxs-lookup"><span data-stu-id="3ea37-144">None</span></span>|<span data-ttu-id="3ea37-145">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-145">Security is disabled.</span></span>|  
|<span data-ttu-id="3ea37-146">Basic</span><span class="sxs-lookup"><span data-stu-id="3ea37-146">Basic</span></span>|<span data-ttu-id="3ea37-147">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="3ea37-148">Digest</span><span class="sxs-lookup"><span data-stu-id="3ea37-148">Digest</span></span>|<span data-ttu-id="3ea37-149">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="3ea37-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3ea37-150">Ntlm</span></span>|<span data-ttu-id="3ea37-151">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="3ea37-152">Windows</span><span class="sxs-lookup"><span data-stu-id="3ea37-152">Windows</span></span>|<span data-ttu-id="3ea37-153">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="3ea37-154">인증서</span><span class="sxs-lookup"><span data-stu-id="3ea37-154">Certificate</span></span>|<span data-ttu-id="3ea37-155">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ea37-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3ea37-156">Child Elements</span></span>  
 <span data-ttu-id="3ea37-157">없음</span><span class="sxs-lookup"><span data-stu-id="3ea37-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ea37-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3ea37-158">Parent Elements</span></span>  
  
|<span data-ttu-id="3ea37-159">요소</span><span class="sxs-lookup"><span data-stu-id="3ea37-159">Element</span></span>|<span data-ttu-id="3ea37-160">설명</span><span class="sxs-lookup"><span data-stu-id="3ea37-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ea37-161">\<security></span><span class="sxs-lookup"><span data-stu-id="3ea37-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="3ea37-162">보안 기능을 나타내는 합니다 [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3ea37-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ea37-163">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ea37-163">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="3ea37-164">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="3ea37-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3ea37-165">바인딩</span><span class="sxs-lookup"><span data-stu-id="3ea37-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="3ea37-166">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="3ea37-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3ea37-167">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="3ea37-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3ea37-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="3ea37-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
