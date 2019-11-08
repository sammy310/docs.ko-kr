---
title: <ws2007HttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732769"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="6489a-102">\<전송 > \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="6489a-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="6489a-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-103">Defines authentication settings for the HTTP transport.</span></span>  
  
<span data-ttu-id="6489a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6489a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6489a-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="6489a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6489a-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="6489a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="6489a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6489a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="6489a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="6489a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6489a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**security >** ](security-of-ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6489a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)</span></span>\
<span data-ttu-id="6489a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**전송 >**</span><span class="sxs-lookup"><span data-stu-id="6489a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6489a-111">구문</span><span class="sxs-lookup"><span data-stu-id="6489a-111">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="6489a-112">Type</span><span class="sxs-lookup"><span data-stu-id="6489a-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6489a-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6489a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6489a-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6489a-115">특성</span><span class="sxs-lookup"><span data-stu-id="6489a-115">Attributes</span></span>  
  
|<span data-ttu-id="6489a-116">특성</span><span class="sxs-lookup"><span data-stu-id="6489a-116">Attribute</span></span>|<span data-ttu-id="6489a-117">설명</span><span class="sxs-lookup"><span data-stu-id="6489a-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="6489a-118">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="6489a-119">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="6489a-120">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="6489a-121">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="6489a-122">다이제스트 또는 기본 인증을 위한 인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-122">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="6489a-123">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="6489a-124">인증 영역은 최소한 인증을 수행 하는 호스트의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="6489a-125">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-125">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="6489a-126">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-126">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="6489a-127">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="6489a-127">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6489a-128">값</span><span class="sxs-lookup"><span data-stu-id="6489a-128">Value</span></span>|<span data-ttu-id="6489a-129">설명</span><span class="sxs-lookup"><span data-stu-id="6489a-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6489a-130">없음</span><span class="sxs-lookup"><span data-stu-id="6489a-130">None</span></span>|<span data-ttu-id="6489a-131">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-131">Security is disabled.</span></span>|  
|<span data-ttu-id="6489a-132">Basic</span><span class="sxs-lookup"><span data-stu-id="6489a-132">Basic</span></span>|<span data-ttu-id="6489a-133">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-133">Uses basic authentication.</span></span>|  
|<span data-ttu-id="6489a-134">Digest</span><span class="sxs-lookup"><span data-stu-id="6489a-134">Digest</span></span>|<span data-ttu-id="6489a-135">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-135">Uses digest authentication.</span></span>|  
|<span data-ttu-id="6489a-136">Ntlm</span><span class="sxs-lookup"><span data-stu-id="6489a-136">Ntlm</span></span>|<span data-ttu-id="6489a-137">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="6489a-138">창</span><span class="sxs-lookup"><span data-stu-id="6489a-138">Windows</span></span>|<span data-ttu-id="6489a-139">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-139">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="6489a-140">인증서</span><span class="sxs-lookup"><span data-stu-id="6489a-140">Certificate</span></span>|<span data-ttu-id="6489a-141">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-141">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="6489a-142">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="6489a-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6489a-143">값</span><span class="sxs-lookup"><span data-stu-id="6489a-143">Value</span></span>|<span data-ttu-id="6489a-144">설명</span><span class="sxs-lookup"><span data-stu-id="6489a-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6489a-145">없음</span><span class="sxs-lookup"><span data-stu-id="6489a-145">None</span></span>|<span data-ttu-id="6489a-146">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-146">Security is disabled.</span></span>|  
|<span data-ttu-id="6489a-147">Basic</span><span class="sxs-lookup"><span data-stu-id="6489a-147">Basic</span></span>|<span data-ttu-id="6489a-148">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-148">Uses basic authentication.</span></span>|  
|<span data-ttu-id="6489a-149">Digest</span><span class="sxs-lookup"><span data-stu-id="6489a-149">Digest</span></span>|<span data-ttu-id="6489a-150">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-150">Uses digest authentication.</span></span>|  
|<span data-ttu-id="6489a-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="6489a-151">Ntlm</span></span>|<span data-ttu-id="6489a-152">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-152">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="6489a-153">창</span><span class="sxs-lookup"><span data-stu-id="6489a-153">Windows</span></span>|<span data-ttu-id="6489a-154">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-154">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="6489a-155">인증서</span><span class="sxs-lookup"><span data-stu-id="6489a-155">Certificate</span></span>|<span data-ttu-id="6489a-156">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-156">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6489a-157">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6489a-157">Child Elements</span></span>  
 <span data-ttu-id="6489a-158">없음</span><span class="sxs-lookup"><span data-stu-id="6489a-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6489a-159">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6489a-159">Parent Elements</span></span>  
  
|<span data-ttu-id="6489a-160">요소</span><span class="sxs-lookup"><span data-stu-id="6489a-160">Element</span></span>|<span data-ttu-id="6489a-161">설명</span><span class="sxs-lookup"><span data-stu-id="6489a-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6489a-162">\<security ></span><span class="sxs-lookup"><span data-stu-id="6489a-162">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="6489a-163">[\<ws2007HttpBinding >](ws2007httpbinding.md) 요소의 보안 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6489a-163">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6489a-164">참조</span><span class="sxs-lookup"><span data-stu-id="6489a-164">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="6489a-165">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="6489a-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6489a-166">바인딩</span><span class="sxs-lookup"><span data-stu-id="6489a-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6489a-167">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="6489a-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6489a-168">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6489a-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6489a-169">\<binding ></span><span class="sxs-lookup"><span data-stu-id="6489a-169">\<binding></span></span>](bindings.md)
