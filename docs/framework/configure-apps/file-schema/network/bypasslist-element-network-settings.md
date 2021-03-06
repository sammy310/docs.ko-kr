---
title: <bypasslist> 요소(네트워크 설정)
description: <bypasslist>네트워크 설정 요소는 .NET Framework에서 프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 0a03b391c839b7255fdd423a305d474d0e48ad39
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259358"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="c20f0-103">\<bypasslist> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="c20f0-103">\<bypasslist> Element (Network Settings)</span></span>

<span data-ttu-id="c20f0-104">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-104">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a><span data-ttu-id="c20f0-105">구문</span><span class="sxs-lookup"><span data-stu-id="c20f0-105">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c20f0-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c20f0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c20f0-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c20f0-108">특성</span><span class="sxs-lookup"><span data-stu-id="c20f0-108">Attributes</span></span>  

 <span data-ttu-id="c20f0-109">없음</span><span class="sxs-lookup"><span data-stu-id="c20f0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c20f0-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c20f0-110">Child Elements</span></span>  
  
|<span data-ttu-id="c20f0-111">**요소**</span><span class="sxs-lookup"><span data-stu-id="c20f0-111">**Element**</span></span>|<span data-ttu-id="c20f0-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="c20f0-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c20f0-113">add</span><span class="sxs-lookup"><span data-stu-id="c20f0-113">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c20f0-114">프록시 무시 목록에 IP 주소 또는 DNS 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-114">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="c20f0-115">clear</span><span class="sxs-lookup"><span data-stu-id="c20f0-115">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c20f0-116">바이패스 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-116">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="c20f0-117">remove</span><span class="sxs-lookup"><span data-stu-id="c20f0-117">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c20f0-118">프록시 바이패스 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-118">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c20f0-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c20f0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c20f0-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="c20f0-120">**Element**</span></span>|<span data-ttu-id="c20f0-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="c20f0-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c20f0-122">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c20f0-122">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c20f0-123">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-123">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c20f0-124">설명</span><span class="sxs-lookup"><span data-stu-id="c20f0-124">Remarks</span></span>  

 <span data-ttu-id="c20f0-125">바이패스 목록에는 <xref:System.Net.WebRequest> 인스턴스가 프록시 서버를 통하지 않고 직접 액세스 하는 uri를 설명 하는 정규식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-125">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="c20f0-126">이 요소에 대 한 정규식을 지정할 때는 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-126">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="c20f0-127">정규식은 `[a-z]+\\.contoso\\.com` contoso.com 도메인의 모든 호스트와 일치 하지만 contoso.com.cpandl.com 도메인의 모든 호스트와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-127">The regular expression `[a-z]+\\.contoso\\.com` matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="c20f0-128">Contoso.com 도메인의 호스트만 일치 시키려면 앵커 ()를 사용 `$` `[a-z]+\\.contoso\\.com$` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-128">To match only a host in the contoso.com domain, use an anchor (`$`): `[a-z]+\\.contoso\\.com$`.</span></span>
  
 <span data-ttu-id="c20f0-129">정규식에 대 한 자세한 내용은을 참조 하십시오. [정규식을 .NET Framework](../../../../standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-129">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c20f0-130">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c20f0-130">Configuration Files</span></span>  

 <span data-ttu-id="c20f0-131">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c20f0-132">예</span><span class="sxs-lookup"><span data-stu-id="c20f0-132">Example</span></span>  

 <span data-ttu-id="c20f0-133">다음 예에서는 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-133">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="c20f0-134">첫 번째는 contoso.com 도메인에 있는 모든 서버에 대 한 프록시를 무시 합니다. 두 번째는 IP 주소가 192.168으로 시작 하는 모든 서버에 대해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20f0-134">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c20f0-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c20f0-135">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c20f0-136">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c20f0-136">Network Settings Schema</span></span>](index.md)
