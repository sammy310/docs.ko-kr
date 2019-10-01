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
ms.openlocfilehash: 1dda43be8c0e0c94bdf7b57b67aa4d403b547f97
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699550"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="12861-102">\<bypasslist > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="12861-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="12861-103">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
[<span data-ttu-id="12861-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="12861-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="12861-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="12861-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="12861-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="12861-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="12861-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<bypasslist >**</span><span class="sxs-lookup"><span data-stu-id="12861-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12861-108">구문</span><span class="sxs-lookup"><span data-stu-id="12861-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12861-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="12861-109">Attributes and Elements</span></span>  
 <span data-ttu-id="12861-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12861-111">특성</span><span class="sxs-lookup"><span data-stu-id="12861-111">Attributes</span></span>  
 <span data-ttu-id="12861-112">없음</span><span class="sxs-lookup"><span data-stu-id="12861-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12861-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="12861-113">Child Elements</span></span>  
  
|<span data-ttu-id="12861-114">**요소**</span><span class="sxs-lookup"><span data-stu-id="12861-114">**Element**</span></span>|<span data-ttu-id="12861-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="12861-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="12861-116">add</span><span class="sxs-lookup"><span data-stu-id="12861-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="12861-117">프록시 무시 목록에 IP 주소 또는 DNS 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="12861-118">clear</span><span class="sxs-lookup"><span data-stu-id="12861-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="12861-119">바이패스 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="12861-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="12861-120">remove</span><span class="sxs-lookup"><span data-stu-id="12861-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="12861-121">프록시 바이패스 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12861-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="12861-122">Parent Elements</span></span>  
  
|<span data-ttu-id="12861-123">**요소**</span><span class="sxs-lookup"><span data-stu-id="12861-123">**Element**</span></span>|<span data-ttu-id="12861-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="12861-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="12861-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="12861-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="12861-126">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12861-127">설명</span><span class="sxs-lookup"><span data-stu-id="12861-127">Remarks</span></span>  
 <span data-ttu-id="12861-128">바이패스 목록에는 프록시 서버를 통하지 않고 직접 액세스 @no__t는 Uri를 설명 하는 정규식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12861-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="12861-129">이 요소에 대 한 정규식을 지정할 때는 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="12861-130">정규식 "[a-z] + @no__t -0.contoso\\.com"는 contoso.com 도메인에 있는 모든 호스트와 일치 하지만 contoso.com.cpandl.com 도메인의 모든 호스트와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="12861-131">Contoso.com 도메인의 호스트만 일치 시키려면 앵커 ("$"): "[a-z] + @no__t -0.contoso\\.com $"를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="12861-132">정규식에 대 한 자세한 내용은을 참조 하십시오. [정규식을 .NET Framework](../../../../standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="12861-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="12861-133">Configuration Files</span></span>  
 <span data-ttu-id="12861-134">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12861-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12861-135">예제</span><span class="sxs-lookup"><span data-stu-id="12861-135">Example</span></span>  
 <span data-ttu-id="12861-136">다음 예에서는 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="12861-137">첫 번째는 contoso.com 도메인에 있는 모든 서버에 대 한 프록시를 무시 합니다. 두 번째는 IP 주소가 192.168으로 시작 하는 모든 서버에 대해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="12861-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12861-138">참조</span><span class="sxs-lookup"><span data-stu-id="12861-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="12861-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="12861-139">Network Settings Schema</span></span>](index.md)
