---
title: <bypasslist> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154948"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="f11f0-102">\<바이패스리스트> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="f11f0-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="f11f0-103">프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="f11f0-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f11f0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f11f0-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f11f0-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="f11f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<기본 프록시>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f11f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="f11f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<바이패스리스트>**</span><span class="sxs-lookup"><span data-stu-id="f11f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f11f0-108">구문</span><span class="sxs-lookup"><span data-stu-id="f11f0-108">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f11f0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f11f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f11f0-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f11f0-111">특성</span><span class="sxs-lookup"><span data-stu-id="f11f0-111">Attributes</span></span>  
 <span data-ttu-id="f11f0-112">없음</span><span class="sxs-lookup"><span data-stu-id="f11f0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f11f0-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f11f0-113">Child Elements</span></span>  
  
|<span data-ttu-id="f11f0-114">**요소**</span><span class="sxs-lookup"><span data-stu-id="f11f0-114">**Element**</span></span>|<span data-ttu-id="f11f0-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="f11f0-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f11f0-116">추가</span><span class="sxs-lookup"><span data-stu-id="f11f0-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f11f0-117">프록시 바이패스 목록에 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="f11f0-118">명확한</span><span class="sxs-lookup"><span data-stu-id="f11f0-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f11f0-119">바이패스 목록을 지웁습니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="f11f0-120">제거</span><span class="sxs-lookup"><span data-stu-id="f11f0-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f11f0-121">프록시 바이패스 목록에서 IP 주소 또는 DNS 이름을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f11f0-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f11f0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f11f0-123">**요소**</span><span class="sxs-lookup"><span data-stu-id="f11f0-123">**Element**</span></span>|<span data-ttu-id="f11f0-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="f11f0-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f11f0-125">기본 프록시</span><span class="sxs-lookup"><span data-stu-id="f11f0-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="f11f0-126">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f11f0-127">설명</span><span class="sxs-lookup"><span data-stu-id="f11f0-127">Remarks</span></span>  
 <span data-ttu-id="f11f0-128">바이패스 목록에는 인스턴스가 프록시 서버대신 <xref:System.Net.WebRequest> 직접 액세스하는 URI를 설명하는 정규식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="f11f0-129">이 요소에 대한 정규식을 지정할 때는 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="f11f0-130">정규표현식 "[a-z]+\\.contoso.com"은\\contoso.com 도메인의 모든 호스트와 일치하지만 contoso.com.cpandl.com 도메인의 모든 호스트와도 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="f11f0-131">contoso.com 도메인의 호스트만 일치하려면 "a-z]+\\.contoso\\.com$"을 앵커("$")를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="f11f0-132">정규식에 대한 자세한 내용은 을 참조하십시오. [.NET 프레임워크 정규 표현식](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f11f0-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f11f0-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f11f0-133">Configuration Files</span></span>  
 <span data-ttu-id="f11f0-134">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f11f0-135">예제</span><span class="sxs-lookup"><span data-stu-id="f11f0-135">Example</span></span>  
 <span data-ttu-id="f11f0-136">다음 예제는 바이패스 목록에 두 개의 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="f11f0-137">첫 번째는 contoso.com 도메인의 모든 서버에 대한 프록시를 무시합니다. 두 번째는 IP 주소가 192.168로 시작하는 모든 서버의 프록시를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="f11f0-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f11f0-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f11f0-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f11f0-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f11f0-139">Network Settings Schema</span></span>](index.md)
