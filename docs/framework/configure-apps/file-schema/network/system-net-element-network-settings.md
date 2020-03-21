---
title: <system.Net> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154558"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="36cbd-102">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="36cbd-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="36cbd-103">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="36cbd-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="36cbd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="36cbd-105">&nbsp;&nbsp;**\<system.net>**</span><span class="sxs-lookup"><span data-stu-id="36cbd-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36cbd-106">구문</span><span class="sxs-lookup"><span data-stu-id="36cbd-106">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36cbd-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36cbd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="36cbd-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36cbd-109">특성</span><span class="sxs-lookup"><span data-stu-id="36cbd-109">Attributes</span></span>  
 <span data-ttu-id="36cbd-110">없음</span><span class="sxs-lookup"><span data-stu-id="36cbd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36cbd-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36cbd-111">Child Elements</span></span>  
  
|<span data-ttu-id="36cbd-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="36cbd-112">**Element**</span></span>|<span data-ttu-id="36cbd-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="36cbd-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="36cbd-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="36cbd-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="36cbd-115">인터넷 요청을 인증하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="36cbd-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="36cbd-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="36cbd-117">인터넷 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="36cbd-118">기본 프록시</span><span class="sxs-lookup"><span data-stu-id="36cbd-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="36cbd-119">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="36cbd-120">메일 설정</span><span class="sxs-lookup"><span data-stu-id="36cbd-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="36cbd-121">간단한 메일 전송 프로토콜(SMTP) 메일 전송 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="36cbd-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="36cbd-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="36cbd-123">네트워크 요청에 대한 캐싱 메커니즘을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="36cbd-124">설정</span><span class="sxs-lookup"><span data-stu-id="36cbd-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="36cbd-125"><xref:System.Net> 하위 네임스페이스 및 관련 하위 네임스페이스의 클래스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="36cbd-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="36cbd-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="36cbd-127">인터넷 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36cbd-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36cbd-128">Parent Elements</span></span>  
  
|<span data-ttu-id="36cbd-129">**요소**</span><span class="sxs-lookup"><span data-stu-id="36cbd-129">**Element**</span></span>|<span data-ttu-id="36cbd-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="36cbd-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="36cbd-131">구성</span><span class="sxs-lookup"><span data-stu-id="36cbd-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="36cbd-132">모든 네임스페이스에 대한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36cbd-133">설명</span><span class="sxs-lookup"><span data-stu-id="36cbd-133">Remarks</span></span>  
 <span data-ttu-id="36cbd-134">[ \<system.net>](system-net-element-network-settings.md) 요소에는 하위 네임스페이스및 관련 하위 네임스페이스의 클래스에 대한 설정이 <xref:System.Net> 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="36cbd-135">설정은 인터넷 호스트로부터 정보를 수신하기 위한 인증 모듈, 연결 관리, 메일 설정, 프록시 서버 및 인터넷 요청 모듈을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36cbd-136">예제</span><span class="sxs-lookup"><span data-stu-id="36cbd-136">Example</span></span>  
 <span data-ttu-id="36cbd-137">다음 예제에서는 클래스에서 사용하는 <xref:System.Net> 일반적인 구성을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36cbd-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36cbd-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36cbd-138">See also</span></span>

- [<span data-ttu-id="36cbd-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="36cbd-139">Network Settings Schema</span></span>](index.md)
