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
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202224"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="4c0a4-102">\<bypasslist > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4c0a4-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="4c0a4-103">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="4c0a4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4c0a4-104">\<configuration></span></span>  
<span data-ttu-id="4c0a4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4c0a4-105">\<system.net></span></span>  
<span data-ttu-id="4c0a4-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="4c0a4-106">\<defaultProxy></span></span>  
<span data-ttu-id="4c0a4-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="4c0a4-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c0a4-108">구문</span><span class="sxs-lookup"><span data-stu-id="4c0a4-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c0a4-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4c0a4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c0a4-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c0a4-111">특성</span><span class="sxs-lookup"><span data-stu-id="4c0a4-111">Attributes</span></span>  
 <span data-ttu-id="4c0a4-112">없음</span><span class="sxs-lookup"><span data-stu-id="4c0a4-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4c0a4-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4c0a4-113">Child Elements</span></span>  
  
|<span data-ttu-id="4c0a4-114">**요소**</span><span class="sxs-lookup"><span data-stu-id="4c0a4-114">**Element**</span></span>|<span data-ttu-id="4c0a4-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="4c0a4-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4c0a4-116">add</span><span class="sxs-lookup"><span data-stu-id="4c0a4-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="4c0a4-117">프록시 무시 목록에는 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="4c0a4-118">clear</span><span class="sxs-lookup"><span data-stu-id="4c0a4-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="4c0a4-119">무시 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="4c0a4-120">remove</span><span class="sxs-lookup"><span data-stu-id="4c0a4-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="4c0a4-121">프록시 무시 목록에서 IP 주소 또는 DNS 이름을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c0a4-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4c0a4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4c0a4-123">**요소**</span><span class="sxs-lookup"><span data-stu-id="4c0a4-123">**Element**</span></span>|<span data-ttu-id="4c0a4-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="4c0a4-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4c0a4-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="4c0a4-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="4c0a4-126">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c0a4-127">설명</span><span class="sxs-lookup"><span data-stu-id="4c0a4-127">Remarks</span></span>  
 <span data-ttu-id="4c0a4-128">바이패스 목록에는 Uri를 설명 하는 정규식을 포함 하는 <xref:System.Net.WebRequest> 인스턴스에서 직접 대신의 프록시 서버를 통해 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="4c0a4-129">이 요소에 대 한 정규식을 지정 하는 경우 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="4c0a4-130">정규식 "[a-z] +\\.contoso\\.com" contoso.com 도메인에 호스트 된 일치 항목의 모든 호스트 contoso.com.cpandl.com 도메인에 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="4c0a4-131">Contoso.com 도메인의 호스트 에서만 일치 하는 앵커 ("$") 사용 하 여: "[a-z] +\\.contoso\\.com$"입니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="4c0a4-132">정규식에 대 한 자세한 내용은 다음을 참조 하세요. [.NET framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4c0a4-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4c0a4-133">Configuration Files</span></span>  
 <span data-ttu-id="4c0a4-134">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c0a4-135">예제</span><span class="sxs-lookup"><span data-stu-id="4c0a4-135">Example</span></span>  
 <span data-ttu-id="4c0a4-136">다음 예제에서는 바이패스 목록에 두 개의 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="4c0a4-137">첫 번째는 contoso.com 도메인의 모든 서버에 대 한 프록시를 무시합니다. 두 번째 192.168 사용 하 여 모든 서버의 IP 주소가 시작에 대 한 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0a4-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c0a4-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="4c0a4-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="4c0a4-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4c0a4-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
