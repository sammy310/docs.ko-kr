---
description: '자세한 정보: <add> bypasslist 요소에 대 한 요소 (네트워크 설정)'
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
ms.openlocfilehash: 6bbd42cdf5d3b9bc31326b619cde96cfac0c755a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698637"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="19f0a-103">bypasslist의 \<add> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="19f0a-103">\<add> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="19f0a-104">프록시 무시 목록에 IP 주소 또는 DNS 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-104">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="19f0a-105">구문</span><span class="sxs-lookup"><span data-stu-id="19f0a-105">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19f0a-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19f0a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="19f0a-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19f0a-108">특성</span><span class="sxs-lookup"><span data-stu-id="19f0a-108">Attributes</span></span>  
  
|<span data-ttu-id="19f0a-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="19f0a-109">**Attribute**</span></span>|<span data-ttu-id="19f0a-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="19f0a-110">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="19f0a-111">**address**</span><span class="sxs-lookup"><span data-stu-id="19f0a-111">**address**</span></span>|<span data-ttu-id="19f0a-112">IP 주소 또는 DNS 이름을 설명 하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-112">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19f0a-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19f0a-113">Child Elements</span></span>  

 <span data-ttu-id="19f0a-114">없음</span><span class="sxs-lookup"><span data-stu-id="19f0a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19f0a-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19f0a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="19f0a-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="19f0a-116">**Element**</span></span>|<span data-ttu-id="19f0a-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="19f0a-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="19f0a-118">bypasslist</span><span class="sxs-lookup"><span data-stu-id="19f0a-118">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="19f0a-119">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-119">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19f0a-120">설명</span><span class="sxs-lookup"><span data-stu-id="19f0a-120">Remarks</span></span>  

 <span data-ttu-id="19f0a-121">`add`요소는 IP 주소 또는 DNS 서버 이름을 설명 하는 정규식을 프록시 서버를 우회 하는 주소 목록에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-121">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="19f0a-122">특성의 값은 `address` IP 주소 또는 호스트 이름 집합을 설명 하는 정규식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-122">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="19f0a-123">이 요소에 대 한 정규식을 지정할 때는 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-123">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="19f0a-124">정규식 "[a-z] + \\ . \\ .com"은 contoso.com 도메인의 모든 호스트와 일치 하지만 contoso.com.cpandl.com 도메인의 모든 호스트와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-124">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="19f0a-125">Contoso.com 도메인의 호스트만 일치 시키려면 앵커 ("$"): "[a-z] + \\ . contoso \\ $"를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-125">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="19f0a-126">정규식에 대 한 자세한 내용은을 참조 하십시오. [정규식을 .NET Framework](../../../../standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-126">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="19f0a-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="19f0a-127">Configuration Files</span></span>  

 <span data-ttu-id="19f0a-128">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19f0a-129">예제</span><span class="sxs-lookup"><span data-stu-id="19f0a-129">Example</span></span>  

 <span data-ttu-id="19f0a-130">다음 예에서는 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-130">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="19f0a-131">첫 번째는 contoso.com 도메인에 있는 모든 서버에 대 한 프록시를 무시 합니다. 두 번째는 IP 주소가 192.168으로 시작 하는 모든 서버에 대해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f0a-131">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="19f0a-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19f0a-132">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="19f0a-133">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="19f0a-133">Network Settings Schema</span></span>](index.md)
