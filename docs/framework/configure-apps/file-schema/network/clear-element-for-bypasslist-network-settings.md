---
title: bypasslist의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: 4d078dac14103560423bfccdd4a1717031e7a60f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699505"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="91209-102">bypasslist에 대 한 \<clear > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="91209-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="91209-103">프록시 무시 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="91209-103">Clears the proxy bypass list.</span></span>  
  
[<span data-ttu-id="91209-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="91209-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="91209-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="91209-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="91209-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="91209-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="91209-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5[ **\<bypasslist >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="91209-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="91209-108">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="91209-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91209-109">구문</span><span class="sxs-lookup"><span data-stu-id="91209-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91209-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91209-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91209-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91209-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91209-112">특성</span><span class="sxs-lookup"><span data-stu-id="91209-112">Attributes</span></span>  
 <span data-ttu-id="91209-113">없음</span><span class="sxs-lookup"><span data-stu-id="91209-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91209-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91209-114">Child Elements</span></span>  
 <span data-ttu-id="91209-115">없음</span><span class="sxs-lookup"><span data-stu-id="91209-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91209-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91209-116">Parent Elements</span></span>  
  
|<span data-ttu-id="91209-117">**요소**</span><span class="sxs-lookup"><span data-stu-id="91209-117">**Element**</span></span>|<span data-ttu-id="91209-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="91209-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="91209-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="91209-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="91209-120">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91209-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91209-121">설명</span><span class="sxs-lookup"><span data-stu-id="91209-121">Remarks</span></span>  
 <span data-ttu-id="91209-122">@No__t-0 요소는 바이패스 목록에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="91209-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="91209-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="91209-123">Configuration Files</span></span>  
 <span data-ttu-id="91209-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91209-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91209-125">예제</span><span class="sxs-lookup"><span data-stu-id="91209-125">Example</span></span>  
 <span data-ttu-id="91209-126">다음 예에서는 바이패스 목록을 지운 다음 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="91209-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="91209-127">첫 번째는 contoso.com 도메인에 있는 모든 서버에 대 한 프록시를 무시 합니다. 두 번째는 IP 주소가 192.168으로 시작 하는 모든 서버에 대해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="91209-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="91209-128">참조</span><span class="sxs-lookup"><span data-stu-id="91209-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="91209-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="91209-129">Network Settings Schema</span></span>](index.md)
