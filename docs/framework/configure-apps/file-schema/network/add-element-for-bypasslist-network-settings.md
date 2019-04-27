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
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674670"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="31fd9-102">\<추가 > bypasslist (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="31fd9-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="31fd9-103">프록시 무시 목록에는 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="31fd9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="31fd9-104">\<configuration></span></span>  
<span data-ttu-id="31fd9-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="31fd9-105">\<system.net></span></span>  
<span data-ttu-id="31fd9-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="31fd9-106">\<defaultProxy></span></span>  
<span data-ttu-id="31fd9-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="31fd9-107">\<bypasslist></span></span>  
<span data-ttu-id="31fd9-108">\<add></span><span class="sxs-lookup"><span data-stu-id="31fd9-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31fd9-109">구문</span><span class="sxs-lookup"><span data-stu-id="31fd9-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31fd9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="31fd9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="31fd9-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31fd9-112">특성</span><span class="sxs-lookup"><span data-stu-id="31fd9-112">Attributes</span></span>  
  
|<span data-ttu-id="31fd9-113">**특성**</span><span class="sxs-lookup"><span data-stu-id="31fd9-113">**Attribute**</span></span>|<span data-ttu-id="31fd9-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="31fd9-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="31fd9-115">**address**</span><span class="sxs-lookup"><span data-stu-id="31fd9-115">**address**</span></span>|<span data-ttu-id="31fd9-116">IP 주소 또는 DNS 이름을 설명 하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31fd9-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="31fd9-117">Child Elements</span></span>  
 <span data-ttu-id="31fd9-118">없음</span><span class="sxs-lookup"><span data-stu-id="31fd9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31fd9-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="31fd9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="31fd9-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="31fd9-120">**Element**</span></span>|<span data-ttu-id="31fd9-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="31fd9-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="31fd9-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="31fd9-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="31fd9-123">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31fd9-124">설명</span><span class="sxs-lookup"><span data-stu-id="31fd9-124">Remarks</span></span>  
 <span data-ttu-id="31fd9-125">`add` 요소 IP 주소 또는 프록시 서버를 바이패스 하는 주소 목록에 DNS 서버 이름을 설명 하는 정규식을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="31fd9-126">값을 `address` 특성에는 IP 주소 또는 호스트 이름 집합을 설명 하는 정규식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="31fd9-127">이 요소에 대 한 정규식을 지정 하는 경우 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="31fd9-128">정규식 "[a-z] +\\.contoso\\.com" contoso.com 도메인에 호스트 된 일치 항목의 모든 호스트 contoso.com.cpandl.com 도메인에 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="31fd9-129">Contoso.com 도메인의 호스트 에서만 일치 하는 앵커 ("$") 사용 하 여: "[a-z] +\\.contoso\\.com$"입니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="31fd9-130">정규식에 대 한 자세한 내용은 다음을 참조 하세요. [.NET framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="31fd9-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="31fd9-131">Configuration Files</span></span>  
 <span data-ttu-id="31fd9-132">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31fd9-133">예제</span><span class="sxs-lookup"><span data-stu-id="31fd9-133">Example</span></span>  
 <span data-ttu-id="31fd9-134">다음 예제에서는 바이패스 목록에 두 개의 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="31fd9-135">첫 번째는 contoso.com 도메인의 모든 서버에 대 한 프록시를 무시합니다. 두 번째 192.168 사용 하 여 IP 주소가 시작 되는 모든 서버에 대 한 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="31fd9-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="31fd9-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="31fd9-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="31fd9-137">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="31fd9-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
