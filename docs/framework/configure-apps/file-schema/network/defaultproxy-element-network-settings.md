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
ms.openlocfilehash: 0945629c1395917bc1cf825f2ba84d20afa99957
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698203"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="e25d3-102">\<defaultProxy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="e25d3-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="e25d3-103">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="e25d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="e25d3-104">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e25d3-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e25d3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e25d3-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e25d3-107">특성</span><span class="sxs-lookup"><span data-stu-id="e25d3-107">Attributes</span></span>  
  
|<span data-ttu-id="e25d3-108">**요소**</span><span class="sxs-lookup"><span data-stu-id="e25d3-108">**Element**</span></span>|<span data-ttu-id="e25d3-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="e25d3-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="e25d3-110">웹 프록시의 사용 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-110">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="e25d3-111">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-111">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="e25d3-112">이 호스트에 대한 기본 자격 증명을 사용하여 웹 프록시에 액세스하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-112">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="e25d3-113">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-113">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e25d3-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e25d3-114">Child Elements</span></span>  
  
|<span data-ttu-id="e25d3-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="e25d3-115">**Element**</span></span>|<span data-ttu-id="e25d3-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="e25d3-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e25d3-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="e25d3-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="e25d3-118">프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-118">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="e25d3-119">모듈</span><span class="sxs-lookup"><span data-stu-id="e25d3-119">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="e25d3-120">애플리케이션에 새 프록시 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-120">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="e25d3-121">proxy</span><span class="sxs-lookup"><span data-stu-id="e25d3-121">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="e25d3-122">프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-122">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e25d3-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e25d3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e25d3-124">**요소**</span><span class="sxs-lookup"><span data-stu-id="e25d3-124">**Element**</span></span>|<span data-ttu-id="e25d3-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="e25d3-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e25d3-126">system.net</span><span class="sxs-lookup"><span data-stu-id="e25d3-126">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="e25d3-127">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-127">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e25d3-128">설명</span><span class="sxs-lookup"><span data-stu-id="e25d3-128">Remarks</span></span>  
 <span data-ttu-id="e25d3-129">DefaultProxy 요소 비어 있으면 Internet Explorer의 프록시 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-129">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="e25d3-130">이 동작은 .NET Framework 버전 1.1과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-130">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e25d3-131">[모듈](module-element-network-settings.md) 요소가 public이 아닌 형식을 지정 하거나, 형식이 클래스에서 파생 되지 않거나, <xref:System.Net.IWebProxy> 이 개체의 매개 변수가 없는 생성자에서 예외가 발생 했거나, 시스템에서 지정한 기본 프록시를 검색 하는 동안 예외가 발생 한 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-131">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="e25d3-132">예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-132">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e25d3-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="e25d3-133">Configuration Files</span></span>  
 <span data-ttu-id="e25d3-134">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25d3-135">예제</span><span class="sxs-lookup"><span data-stu-id="e25d3-135">Example</span></span>  
 <span data-ttu-id="e25d3-136">다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 고, 프록시 주소를 지정 하 고, 로컬 액세스 및 contoso.com 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25d3-136">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e25d3-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e25d3-137">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="e25d3-138">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e25d3-138">Network Settings Schema</span></span>](index.md)
