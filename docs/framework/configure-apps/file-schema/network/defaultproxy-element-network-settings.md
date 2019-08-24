---
title: <defaultProxy> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 7e49762ee017564734bfb2b2f7074d94b7eabe11
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659388"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="22161-102">\<defaultProxy > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="22161-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="22161-103">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="22161-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22161-104">\<configuration></span></span>  
<span data-ttu-id="22161-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="22161-105">\<system.net></span></span>  
<span data-ttu-id="22161-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="22161-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22161-107">구문</span><span class="sxs-lookup"><span data-stu-id="22161-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22161-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="22161-108">Attributes and Elements</span></span>  
 <span data-ttu-id="22161-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22161-110">특성</span><span class="sxs-lookup"><span data-stu-id="22161-110">Attributes</span></span>  
  
|<span data-ttu-id="22161-111">**요소**</span><span class="sxs-lookup"><span data-stu-id="22161-111">**Element**</span></span>|<span data-ttu-id="22161-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="22161-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="22161-113">웹 프록시의 사용 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="22161-114">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="22161-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="22161-115">이 호스트에 대한 기본 자격 증명을 사용하여 웹 프록시에 액세스하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="22161-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="22161-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22161-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="22161-117">Child Elements</span></span>  
  
|<span data-ttu-id="22161-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="22161-118">**Element**</span></span>|<span data-ttu-id="22161-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="22161-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="22161-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="22161-120">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="22161-121">프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="22161-122">module</span><span class="sxs-lookup"><span data-stu-id="22161-122">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="22161-123">애플리케이션에 새 프록시 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="22161-124">proxy</span><span class="sxs-lookup"><span data-stu-id="22161-124">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="22161-125">프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22161-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="22161-126">Parent Elements</span></span>  
  
|<span data-ttu-id="22161-127">**요소**</span><span class="sxs-lookup"><span data-stu-id="22161-127">**Element**</span></span>|<span data-ttu-id="22161-128">**설명**</span><span class="sxs-lookup"><span data-stu-id="22161-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="22161-129">system.net</span><span class="sxs-lookup"><span data-stu-id="22161-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="22161-130">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22161-131">설명</span><span class="sxs-lookup"><span data-stu-id="22161-131">Remarks</span></span>  
 <span data-ttu-id="22161-132">DefaultProxy 요소 비어 있으면 Internet Explorer의 프록시 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22161-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="22161-133">이 동작은 .NET Framework 버전 1.1과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="22161-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="22161-134">[모듈](module-element-network-settings.md) 요소가 public이 아닌 형식을 지정 하거나, 형식이 <xref:System.Net.IWebProxy> 클래스에서 파생 되지 않거나,이 개체의 매개 변수가 없는 생성자에서 예외가 발생 했거나,를 검색 하는 동안 예외가 발생 한 경우 예외가 throw 됩니다. 시스템에서 지정한 기본 프록시입니다.</span><span class="sxs-lookup"><span data-stu-id="22161-134">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="22161-135">예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="22161-136">구성 파일</span><span class="sxs-lookup"><span data-stu-id="22161-136">Configuration Files</span></span>  
 <span data-ttu-id="22161-137">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22161-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22161-138">예제</span><span class="sxs-lookup"><span data-stu-id="22161-138">Example</span></span>  
 <span data-ttu-id="22161-139">다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 고, 프록시 주소를 지정 하 고, 로컬 액세스 및 contoso.com 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="22161-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22161-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="22161-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="22161-141">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="22161-141">Network Settings Schema</span></span>](index.md)
