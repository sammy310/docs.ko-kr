---
title: bypasslist의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 97b49a8a520d6a4f72945366874991d2deb18710
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697903"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="820f8-102">bypasslist의 \<remove> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="820f8-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="820f8-103">프록시 바이패스 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  

## <a name="syntax"></a><span data-ttu-id="820f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="820f8-104">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="820f8-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="820f8-105">Attributes and Elements</span></span>

<span data-ttu-id="820f8-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="820f8-107">특성</span><span class="sxs-lookup"><span data-stu-id="820f8-107">Attributes</span></span>

|<span data-ttu-id="820f8-108">**특성**</span><span class="sxs-lookup"><span data-stu-id="820f8-108">**Attribute**</span></span>|<span data-ttu-id="820f8-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="820f8-109">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="820f8-110">IP 주소 또는 DNS 이름을 설명 하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-110">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="820f8-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="820f8-111">Child Elements</span></span>

<span data-ttu-id="820f8-112">없음</span><span class="sxs-lookup"><span data-stu-id="820f8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="820f8-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="820f8-113">Parent Elements</span></span>

|<span data-ttu-id="820f8-114">**요소**</span><span class="sxs-lookup"><span data-stu-id="820f8-114">**Element**</span></span>|<span data-ttu-id="820f8-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="820f8-115">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="820f8-116">bypasslist</span><span class="sxs-lookup"><span data-stu-id="820f8-116">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="820f8-117">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-117">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="820f8-118">설명</span><span class="sxs-lookup"><span data-stu-id="820f8-118">Remarks</span></span>

<span data-ttu-id="820f8-119">`remove`요소는 프록시 서버를 우회 하는 주소 목록에서 IP 주소 또는 DNS 서버 이름을 설명 하는 정규식을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-119">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="820f8-120">주소가 구성 파일에서 이전에 정의 되었거나 구성 계층 구조의 상위 수준에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-120">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="820f8-121">특성 값은 `address` IP 주소 또는 호스트 이름 집합을 설명 하는 정규식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-121">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="820f8-122">정규식에 대 한 자세한 내용은을 참조 하십시오. [정규식을 .NET Framework](../../../../standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-122">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="820f8-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="820f8-123">Configuration Files</span></span>

<span data-ttu-id="820f8-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="820f8-125">예제</span><span class="sxs-lookup"><span data-stu-id="820f8-125">Example</span></span>

<span data-ttu-id="820f8-126">다음 예에서는 adventure-works.com 도메인에 대 한 이전 정의를 제거 하 고 contoso.com 도메인을 바이패스 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="820f8-126">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="820f8-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="820f8-127">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="820f8-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="820f8-128">Network Settings Schema</span></span>](index.md)
