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
ms.openlocfilehash: 810e942394c75c192e4423afe4c674ef3a2b9900
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697500"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="e8d6f-102">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="e8d6f-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="e8d6f-103">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="e8d6f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e8d6f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e8d6f-105">&nbsp;&nbsp; **\<.net >**</span><span class="sxs-lookup"><span data-stu-id="e8d6f-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d6f-106">구문</span><span class="sxs-lookup"><span data-stu-id="e8d6f-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8d6f-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e8d6f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e8d6f-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8d6f-109">특성</span><span class="sxs-lookup"><span data-stu-id="e8d6f-109">Attributes</span></span>  
 <span data-ttu-id="e8d6f-110">None.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8d6f-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8d6f-111">Child Elements</span></span>  
  
|<span data-ttu-id="e8d6f-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="e8d6f-112">**Element**</span></span>|<span data-ttu-id="e8d6f-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="e8d6f-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e8d6f-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="e8d6f-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="e8d6f-115">인터넷 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="e8d6f-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="e8d6f-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="e8d6f-117">인터넷 호스트에 대 한 최대 연결 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="e8d6f-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="e8d6f-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="e8d6f-119">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="e8d6f-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="e8d6f-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="e8d6f-121">SMTP (Simple Mail Transport Protocol) 메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="e8d6f-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="e8d6f-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="e8d6f-123">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="e8d6f-124">settings</span><span class="sxs-lookup"><span data-stu-id="e8d6f-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e8d6f-125"><xref:System.Net> 및 관련 자식 네임 스페이스의 클래스에 대 한 기본 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="e8d6f-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="e8d6f-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="e8d6f-127">인터넷 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8d6f-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8d6f-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e8d6f-129">**요소**</span><span class="sxs-lookup"><span data-stu-id="e8d6f-129">**Element**</span></span>|<span data-ttu-id="e8d6f-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="e8d6f-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e8d6f-131">configuration</span><span class="sxs-lookup"><span data-stu-id="e8d6f-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="e8d6f-132">모든 네임 스페이스에 대 한 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8d6f-133">주의</span><span class="sxs-lookup"><span data-stu-id="e8d6f-133">Remarks</span></span>  
 <span data-ttu-id="e8d6f-134">[\<net.tcp >](system-net-element-network-settings.md) 요소에는 <xref:System.Net> 및 관련 자식 네임 스페이스의 클래스에 대 한 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="e8d6f-135">설정은 인터넷 호스트에서 정보를 수신 하기 위한 인증 모듈, 연결 관리, 메일 설정, 프록시 서버 및 인터넷 요청 모듈을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8d6f-136">예제</span><span class="sxs-lookup"><span data-stu-id="e8d6f-136">Example</span></span>  
 <span data-ttu-id="e8d6f-137">다음 예제에서는 <xref:System.Net> 클래스에서 사용 하는 일반적인 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8d6f-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e8d6f-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8d6f-138">See also</span></span>

- [<span data-ttu-id="e8d6f-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e8d6f-139">Network Settings Schema</span></span>](index.md)
