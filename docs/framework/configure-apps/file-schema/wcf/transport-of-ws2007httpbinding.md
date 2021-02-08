---
description: '다음에 대 한 자세한 정보:: <transport><ws2007HttpBinding>'
title: <ws2007HttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 8c6890bc291458ba0849ab7a206487431b279576
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773435"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="5b1b8-103">\<ws2007HttpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="5b1b8-103">\<transport> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="5b1b8-104">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-104">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="5b1b8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b1b8-105">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="5b1b8-106">Type</span><span class="sxs-lookup"><span data-stu-id="5b1b8-106">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b1b8-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5b1b8-107">Attributes and Elements</span></span>  

 <span data-ttu-id="5b1b8-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b1b8-109">특성</span><span class="sxs-lookup"><span data-stu-id="5b1b8-109">Attributes</span></span>  
  
|<span data-ttu-id="5b1b8-110">attribute</span><span class="sxs-lookup"><span data-stu-id="5b1b8-110">Attribute</span></span>|<span data-ttu-id="5b1b8-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b1b8-111">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="5b1b8-112">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-112">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="5b1b8-113">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="5b1b8-114">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-114">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="5b1b8-115">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-115">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="5b1b8-116">다이제스트 또는 기본 인증을 위한 인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-116">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="5b1b8-117">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-117">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="5b1b8-118">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="5b1b8-118">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="5b1b8-119">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-119">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="5b1b8-120">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-120">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="5b1b8-121">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="5b1b8-121">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="5b1b8-122">값</span><span class="sxs-lookup"><span data-stu-id="5b1b8-122">Value</span></span>|<span data-ttu-id="5b1b8-123">설명</span><span class="sxs-lookup"><span data-stu-id="5b1b8-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b1b8-124">없음</span><span class="sxs-lookup"><span data-stu-id="5b1b8-124">None</span></span>|<span data-ttu-id="5b1b8-125">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-125">Security is disabled.</span></span>|  
|<span data-ttu-id="5b1b8-126">Basic</span><span class="sxs-lookup"><span data-stu-id="5b1b8-126">Basic</span></span>|<span data-ttu-id="5b1b8-127">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-127">Uses basic authentication.</span></span>|  
|<span data-ttu-id="5b1b8-128">다이제스트</span><span class="sxs-lookup"><span data-stu-id="5b1b8-128">Digest</span></span>|<span data-ttu-id="5b1b8-129">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-129">Uses digest authentication.</span></span>|  
|<span data-ttu-id="5b1b8-130">Ntlm</span><span class="sxs-lookup"><span data-stu-id="5b1b8-130">Ntlm</span></span>|<span data-ttu-id="5b1b8-131">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-131">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="5b1b8-132">Windows</span><span class="sxs-lookup"><span data-stu-id="5b1b8-132">Windows</span></span>|<span data-ttu-id="5b1b8-133">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-133">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="5b1b8-134">인증서</span><span class="sxs-lookup"><span data-stu-id="5b1b8-134">Certificate</span></span>|<span data-ttu-id="5b1b8-135">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-135">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="5b1b8-136">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="5b1b8-136">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="5b1b8-137">값</span><span class="sxs-lookup"><span data-stu-id="5b1b8-137">Value</span></span>|<span data-ttu-id="5b1b8-138">설명</span><span class="sxs-lookup"><span data-stu-id="5b1b8-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b1b8-139">없음</span><span class="sxs-lookup"><span data-stu-id="5b1b8-139">None</span></span>|<span data-ttu-id="5b1b8-140">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-140">Security is disabled.</span></span>|  
|<span data-ttu-id="5b1b8-141">Basic</span><span class="sxs-lookup"><span data-stu-id="5b1b8-141">Basic</span></span>|<span data-ttu-id="5b1b8-142">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-142">Uses basic authentication.</span></span>|  
|<span data-ttu-id="5b1b8-143">다이제스트</span><span class="sxs-lookup"><span data-stu-id="5b1b8-143">Digest</span></span>|<span data-ttu-id="5b1b8-144">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-144">Uses digest authentication.</span></span>|  
|<span data-ttu-id="5b1b8-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="5b1b8-145">Ntlm</span></span>|<span data-ttu-id="5b1b8-146">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="5b1b8-147">Windows</span><span class="sxs-lookup"><span data-stu-id="5b1b8-147">Windows</span></span>|<span data-ttu-id="5b1b8-148">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-148">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="5b1b8-149">인증서</span><span class="sxs-lookup"><span data-stu-id="5b1b8-149">Certificate</span></span>|<span data-ttu-id="5b1b8-150">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-150">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b1b8-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5b1b8-151">Child Elements</span></span>  

 <span data-ttu-id="5b1b8-152">없음</span><span class="sxs-lookup"><span data-stu-id="5b1b8-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b1b8-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5b1b8-153">Parent Elements</span></span>  
  
|<span data-ttu-id="5b1b8-154">요소</span><span class="sxs-lookup"><span data-stu-id="5b1b8-154">Element</span></span>|<span data-ttu-id="5b1b8-155">설명</span><span class="sxs-lookup"><span data-stu-id="5b1b8-155">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="5b1b8-156">요소의 보안 기능을 나타냅니다 [\<ws2007HttpBinding>](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5b1b8-156">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b1b8-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b1b8-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="5b1b8-158">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5b1b8-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5b1b8-159">바인딩</span><span class="sxs-lookup"><span data-stu-id="5b1b8-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5b1b8-160">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5b1b8-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5b1b8-161">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5b1b8-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
