---
title: <ws2007HttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 60e8758d653848176ca3f287e253bd7990e78470
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162051"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="b7203-102">\<ws2007HttpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="b7203-102">\<transport> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="b7203-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="b7203-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7203-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="b7203-105">형식</span><span class="sxs-lookup"><span data-stu-id="b7203-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7203-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b7203-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b7203-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7203-108">특성</span><span class="sxs-lookup"><span data-stu-id="b7203-108">Attributes</span></span>  
  
|<span data-ttu-id="b7203-109">attribute</span><span class="sxs-lookup"><span data-stu-id="b7203-109">Attribute</span></span>|<span data-ttu-id="b7203-110">설명</span><span class="sxs-lookup"><span data-stu-id="b7203-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="b7203-111">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="b7203-112">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="b7203-113">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="b7203-114">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="b7203-115">다이제스트 또는 기본 인증을 위한 인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="b7203-116">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="b7203-117">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="b7203-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="b7203-118">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="b7203-119">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="b7203-120">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="b7203-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b7203-121">Value</span><span class="sxs-lookup"><span data-stu-id="b7203-121">Value</span></span>|<span data-ttu-id="b7203-122">설명</span><span class="sxs-lookup"><span data-stu-id="b7203-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7203-123">없음</span><span class="sxs-lookup"><span data-stu-id="b7203-123">None</span></span>|<span data-ttu-id="b7203-124">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-124">Security is disabled.</span></span>|  
|<span data-ttu-id="b7203-125">Basic</span><span class="sxs-lookup"><span data-stu-id="b7203-125">Basic</span></span>|<span data-ttu-id="b7203-126">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="b7203-127">다이제스트</span><span class="sxs-lookup"><span data-stu-id="b7203-127">Digest</span></span>|<span data-ttu-id="b7203-128">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="b7203-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b7203-129">Ntlm</span></span>|<span data-ttu-id="b7203-130">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="b7203-131">Windows</span><span class="sxs-lookup"><span data-stu-id="b7203-131">Windows</span></span>|<span data-ttu-id="b7203-132">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="b7203-133">인증서</span><span class="sxs-lookup"><span data-stu-id="b7203-133">Certificate</span></span>|<span data-ttu-id="b7203-134">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="b7203-135">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="b7203-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b7203-136">Value</span><span class="sxs-lookup"><span data-stu-id="b7203-136">Value</span></span>|<span data-ttu-id="b7203-137">설명</span><span class="sxs-lookup"><span data-stu-id="b7203-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7203-138">없음</span><span class="sxs-lookup"><span data-stu-id="b7203-138">None</span></span>|<span data-ttu-id="b7203-139">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-139">Security is disabled.</span></span>|  
|<span data-ttu-id="b7203-140">Basic</span><span class="sxs-lookup"><span data-stu-id="b7203-140">Basic</span></span>|<span data-ttu-id="b7203-141">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="b7203-142">다이제스트</span><span class="sxs-lookup"><span data-stu-id="b7203-142">Digest</span></span>|<span data-ttu-id="b7203-143">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="b7203-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b7203-144">Ntlm</span></span>|<span data-ttu-id="b7203-145">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="b7203-146">Windows</span><span class="sxs-lookup"><span data-stu-id="b7203-146">Windows</span></span>|<span data-ttu-id="b7203-147">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="b7203-148">인증서</span><span class="sxs-lookup"><span data-stu-id="b7203-148">Certificate</span></span>|<span data-ttu-id="b7203-149">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="b7203-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7203-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b7203-150">Child Elements</span></span>  

 <span data-ttu-id="b7203-151">없음</span><span class="sxs-lookup"><span data-stu-id="b7203-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7203-152">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b7203-152">Parent Elements</span></span>  
  
|<span data-ttu-id="b7203-153">요소</span><span class="sxs-lookup"><span data-stu-id="b7203-153">Element</span></span>|<span data-ttu-id="b7203-154">설명</span><span class="sxs-lookup"><span data-stu-id="b7203-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="b7203-155">요소의 보안 기능을 나타냅니다 [\<ws2007HttpBinding>](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b7203-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7203-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7203-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="b7203-157">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b7203-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b7203-158">바인딩하</span><span class="sxs-lookup"><span data-stu-id="b7203-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b7203-159">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b7203-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b7203-160">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b7203-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
