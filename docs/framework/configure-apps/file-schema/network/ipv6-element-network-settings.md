---
title: <ipv6> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088127"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="4cf56-102">\<ipv6> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4cf56-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="4cf56-103">클래스의 사용 되지 않는 멤버에서 IPv6 (인터넷 프로토콜 버전 6) 응답을 사용 하도록 설정 <xref:System.Net.Dns> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="4cf56-104">구문</span><span class="sxs-lookup"><span data-stu-id="4cf56-104">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cf56-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4cf56-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4cf56-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cf56-107">특성</span><span class="sxs-lookup"><span data-stu-id="4cf56-107">Attributes</span></span>  
  
|<span data-ttu-id="4cf56-108">**특성**</span><span class="sxs-lookup"><span data-stu-id="4cf56-108">**Attribute**</span></span>|<span data-ttu-id="4cf56-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="4cf56-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="4cf56-110">클래스의 멤버가 <xref:System.Net.Dns> IPv6 (인터넷 프로토콜 버전 6) 주소를 반환 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-110">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="4cf56-111">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4cf56-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4cf56-112">Child Elements</span></span>  
 <span data-ttu-id="4cf56-113">없음</span><span class="sxs-lookup"><span data-stu-id="4cf56-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4cf56-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4cf56-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4cf56-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="4cf56-115">**Element**</span></span>|<span data-ttu-id="4cf56-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="4cf56-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4cf56-117">설정</span><span class="sxs-lookup"><span data-stu-id="4cf56-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="4cf56-118"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cf56-119">설명</span><span class="sxs-lookup"><span data-stu-id="4cf56-119">Remarks</span></span>  
 <span data-ttu-id="4cf56-120">이 설정은,,,,, 및 클래스의 사용 되지 않는 멤버에 대 한 IPv6 지원을 사용 하도록 설정 <xref:System.Net.Dns> <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndGetHostByName%2A> <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.GetHostByAddress%2A> <xref:System.Net.Dns.GetHostByName%2A> <xref:System.Net.Dns.Resolve%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-120">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="4cf56-121">네임 스페이스의 다른 구성원의 경우 ipv6 <xref:System.Net?displayProperty=nameWithType> 주소가 운영 체제에서 사용 하도록 설정 된 경우 ipv6 주소가 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-121">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4cf56-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4cf56-122">Configuration Files</span></span>  
 <span data-ttu-id="4cf56-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf56-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf56-124">예제</span><span class="sxs-lookup"><span data-stu-id="4cf56-124">Example</span></span>  
 <span data-ttu-id="4cf56-125">다음 예제에서는 클래스에 대 한 IPv6 지원을 사용 하도록 설정 하는 방법을 보여 줍니다 <xref:System.Net.Dns> .</span><span class="sxs-lookup"><span data-stu-id="4cf56-125">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cf56-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cf56-126">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4cf56-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4cf56-127">Network Settings Schema</span></span>](index.md)
