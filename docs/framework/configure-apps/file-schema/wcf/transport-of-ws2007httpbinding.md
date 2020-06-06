---
title: <ws2007HttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732769"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="72e3d-102">\<ws2007HttpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="72e3d-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="72e3d-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="72e3d-104">구문</span><span class="sxs-lookup"><span data-stu-id="72e3d-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="72e3d-105">Type</span><span class="sxs-lookup"><span data-stu-id="72e3d-105">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72e3d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="72e3d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="72e3d-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72e3d-108">특성</span><span class="sxs-lookup"><span data-stu-id="72e3d-108">Attributes</span></span>  
  
|<span data-ttu-id="72e3d-109">attribute</span><span class="sxs-lookup"><span data-stu-id="72e3d-109">Attribute</span></span>|<span data-ttu-id="72e3d-110">Description</span><span class="sxs-lookup"><span data-stu-id="72e3d-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="72e3d-111">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="72e3d-112">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="72e3d-113">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="72e3d-114">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="72e3d-115">다이제스트 또는 기본 인증을 위한 인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="72e3d-116">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="72e3d-117">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="72e3d-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="72e3d-118">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="72e3d-119">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="72e3d-120">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="72e3d-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="72e3d-121">값</span><span class="sxs-lookup"><span data-stu-id="72e3d-121">Value</span></span>|<span data-ttu-id="72e3d-122">Description</span><span class="sxs-lookup"><span data-stu-id="72e3d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72e3d-123">None</span><span class="sxs-lookup"><span data-stu-id="72e3d-123">None</span></span>|<span data-ttu-id="72e3d-124">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-124">Security is disabled.</span></span>|  
|<span data-ttu-id="72e3d-125">Basic</span><span class="sxs-lookup"><span data-stu-id="72e3d-125">Basic</span></span>|<span data-ttu-id="72e3d-126">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="72e3d-127">다이제스트</span><span class="sxs-lookup"><span data-stu-id="72e3d-127">Digest</span></span>|<span data-ttu-id="72e3d-128">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="72e3d-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="72e3d-129">Ntlm</span></span>|<span data-ttu-id="72e3d-130">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="72e3d-131">Windows</span><span class="sxs-lookup"><span data-stu-id="72e3d-131">Windows</span></span>|<span data-ttu-id="72e3d-132">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="72e3d-133">인증서</span><span class="sxs-lookup"><span data-stu-id="72e3d-133">Certificate</span></span>|<span data-ttu-id="72e3d-134">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="72e3d-135">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="72e3d-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="72e3d-136">값</span><span class="sxs-lookup"><span data-stu-id="72e3d-136">Value</span></span>|<span data-ttu-id="72e3d-137">Description</span><span class="sxs-lookup"><span data-stu-id="72e3d-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72e3d-138">None</span><span class="sxs-lookup"><span data-stu-id="72e3d-138">None</span></span>|<span data-ttu-id="72e3d-139">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-139">Security is disabled.</span></span>|  
|<span data-ttu-id="72e3d-140">Basic</span><span class="sxs-lookup"><span data-stu-id="72e3d-140">Basic</span></span>|<span data-ttu-id="72e3d-141">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="72e3d-142">다이제스트</span><span class="sxs-lookup"><span data-stu-id="72e3d-142">Digest</span></span>|<span data-ttu-id="72e3d-143">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="72e3d-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="72e3d-144">Ntlm</span></span>|<span data-ttu-id="72e3d-145">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="72e3d-146">Windows</span><span class="sxs-lookup"><span data-stu-id="72e3d-146">Windows</span></span>|<span data-ttu-id="72e3d-147">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="72e3d-148">인증서</span><span class="sxs-lookup"><span data-stu-id="72e3d-148">Certificate</span></span>|<span data-ttu-id="72e3d-149">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="72e3d-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72e3d-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="72e3d-150">Child Elements</span></span>  
 <span data-ttu-id="72e3d-151">None</span><span class="sxs-lookup"><span data-stu-id="72e3d-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72e3d-152">부모 요소</span><span class="sxs-lookup"><span data-stu-id="72e3d-152">Parent Elements</span></span>  
  
|<span data-ttu-id="72e3d-153">요소</span><span class="sxs-lookup"><span data-stu-id="72e3d-153">Element</span></span>|<span data-ttu-id="72e3d-154">Description</span><span class="sxs-lookup"><span data-stu-id="72e3d-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="72e3d-155">요소의 보안 기능을 나타냅니다 [\<ws2007HttpBinding>](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="72e3d-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72e3d-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72e3d-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="72e3d-157">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="72e3d-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="72e3d-158">바인딩</span><span class="sxs-lookup"><span data-stu-id="72e3d-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="72e3d-159">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="72e3d-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="72e3d-160">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="72e3d-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
