---
title: bypasslist의 <add> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155079"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="af1d6-102">\<바이패스리스트에> 요소 추가(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="af1d6-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="af1d6-103">프록시 바이패스 목록에 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="af1d6-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="af1d6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="af1d6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="af1d6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="af1d6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<기본 프록시>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="af1d6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="af1d6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<바이패스리스트>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="af1d6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="af1d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="af1d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af1d6-109">구문</span><span class="sxs-lookup"><span data-stu-id="af1d6-109">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af1d6-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="af1d6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af1d6-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af1d6-112">특성</span><span class="sxs-lookup"><span data-stu-id="af1d6-112">Attributes</span></span>  
  
|<span data-ttu-id="af1d6-113">**특성**</span><span class="sxs-lookup"><span data-stu-id="af1d6-113">**Attribute**</span></span>|<span data-ttu-id="af1d6-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="af1d6-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="af1d6-115">**주소**</span><span class="sxs-lookup"><span data-stu-id="af1d6-115">**address**</span></span>|<span data-ttu-id="af1d6-116">IP 주소 또는 DNS 이름을 설명하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af1d6-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="af1d6-117">Child Elements</span></span>  
 <span data-ttu-id="af1d6-118">없음</span><span class="sxs-lookup"><span data-stu-id="af1d6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af1d6-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="af1d6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="af1d6-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="af1d6-120">**Element**</span></span>|<span data-ttu-id="af1d6-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="af1d6-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="af1d6-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="af1d6-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="af1d6-123">프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af1d6-124">설명</span><span class="sxs-lookup"><span data-stu-id="af1d6-124">Remarks</span></span>  
 <span data-ttu-id="af1d6-125">이 `add` 요소는 IP 주소 또는 DNS 서버 이름을 설명하는 정규식을 프록시 서버를 우회하는 주소 목록에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="af1d6-126">특성값은 `address` IP 주소 또는 호스트 이름 집합을 설명하는 정규식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="af1d6-127">이 요소에 대한 정규식을 지정할 때는 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="af1d6-128">정규표현식 "[a-z]+\\.contoso.com"은\\contoso.com 도메인의 모든 호스트와 일치하지만 contoso.com.cpandl.com 도메인의 모든 호스트와도 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="af1d6-129">contoso.com 도메인의 호스트만 일치하려면 "a-z]+\\.contoso\\.com$"을 앵커("$")를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="af1d6-130">정규식에 대한 자세한 내용은 을 참조하십시오. [.NET 프레임워크 정규 표현식](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="af1d6-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="af1d6-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="af1d6-131">Configuration Files</span></span>  
 <span data-ttu-id="af1d6-132">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af1d6-133">예제</span><span class="sxs-lookup"><span data-stu-id="af1d6-133">Example</span></span>  
 <span data-ttu-id="af1d6-134">다음 예제는 바이패스 목록에 두 개의 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="af1d6-135">첫 번째는 contoso.com 도메인의 모든 서버에 대한 프록시를 무시합니다. 두 번째는 IP 주소가 192.168로 시작하는 모든 서버의 프록시를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="af1d6-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af1d6-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af1d6-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="af1d6-137">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="af1d6-137">Network Settings Schema</span></span>](index.md)
