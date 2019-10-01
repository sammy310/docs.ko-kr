---
title: <socket> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: ec2c8388411e24940041dc9dcb7f6a6755e89805
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697581"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="99113-102">\<socket > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="99113-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="99113-103">소켓 작업에서 완료 포트를 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-103">Specifies whether socket operations use completion ports.</span></span>  
  
[<span data-ttu-id="99113-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="99113-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="99113-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="99113-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="99113-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="99113-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="99113-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<socket >**</span><span class="sxs-lookup"><span data-stu-id="99113-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99113-108">구문</span><span class="sxs-lookup"><span data-stu-id="99113-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99113-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="99113-109">Attributes and Elements</span></span>  
 <span data-ttu-id="99113-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99113-111">특성</span><span class="sxs-lookup"><span data-stu-id="99113-111">Attributes</span></span>  
  
|<span data-ttu-id="99113-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="99113-112">**Attribute**</span></span>|<span data-ttu-id="99113-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="99113-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="99113-114">소켓이 항상 허용 메서드 호출에 대해 완료 포트를 사용 해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99113-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="99113-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="99113-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="99113-116">소켓이 연결 메서드 호출에 대해 항상 완료 포트를 사용 해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99113-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="99113-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="99113-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="99113-118">소켓에 사용할 기본값 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="99113-119">기본값은 Windows 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="99113-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99113-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="99113-120">Child Elements</span></span>  
 <span data-ttu-id="99113-121">없음</span><span class="sxs-lookup"><span data-stu-id="99113-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99113-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="99113-122">Parent Elements</span></span>  
  
|<span data-ttu-id="99113-123">**요소**</span><span class="sxs-lookup"><span data-stu-id="99113-123">**Element**</span></span>|<span data-ttu-id="99113-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="99113-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="99113-125">settings</span><span class="sxs-lookup"><span data-stu-id="99113-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="99113-126"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99113-127">설명</span><span class="sxs-lookup"><span data-stu-id="99113-127">Remarks</span></span>  
 <span data-ttu-id="99113-128">`alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성이 <xref:System.Net.Sockets?displayProperty=nameWithType> 네임스페이스에 있는 클래스에 의해 완료 포트의 사용과 관련된 기본 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99113-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="99113-129">고성능 서버 응용 프로그램에는 완료 포트를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="99113-130">@No__t-0 및 `alwaysUseCompletionPortsForConnect` 특성의 기본값은 **false**입니다.</span><span class="sxs-lookup"><span data-stu-id="99113-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="99113-131">@No__t-0은 적용 가능한 구성 파일에서 `alwaysUseCompletionPortsForAccept` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="99113-132">@No__t-0은 적용 가능한 구성 파일에서 `alwaysUseCompletionPortsForConnect` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="99113-133">@No__t-0 특성은 소켓에 사용할 기본값 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="99113-134"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 속성 주소 같은 링크 로컬 또는 사이트 로컬 접두사가 같은 지정된 된 범위에 IPv6 소켓에 대 한 제한 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="99113-135">이 옵션에는 응용 프로그램을으로 IPv6 소켓에 대 한 액세스 제한을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="99113-136">이러한 제한을 사용하면 사설 LAN에서 실행되는 응용 프로그램을 간단하고 강력하게 외부 공격으로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="99113-137">이 옵션의 공용 및 개인 사용자가 해당 하는 경우 필요에 따라 같은 사이트로 액세스를 제한 또는 무제한 액세스를 수신 대기 소켓의 범위를 넓히거나 설정.</span><span class="sxs-lookup"><span data-stu-id="99113-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="99113-138">이 `ipProtectionLevel` 특성 설정은 초기 들어오는 트래픽에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99113-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="99113-139">소켓에서 들어오는 연결을 수신 대기 하는 TCP 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="99113-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="99113-140">소켓에서 패킷을 수신 하는 UDP 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="99113-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="99113-141">이 구성 설정은 이미 설정 된 TCP 연결에는 영향을 주지 않습니다. (트래픽은 양방향으로 제한 되지 않음), UDP 패킷을 보내는 응용 프로그램에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="99113-142">@No__t-0 특성 설정에 사용할 수 있는 값은 다음과 같이 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 열거에 지정 된 정의 된 보호 수준에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="99113-143">**특성 값**</span><span class="sxs-lookup"><span data-stu-id="99113-143">**Attribute Value**</span></span>|<span data-ttu-id="99113-144">**설명**</span><span class="sxs-lookup"><span data-stu-id="99113-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="99113-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="99113-145">EdgeRestricted</span></span>|<span data-ttu-id="99113-146">IP 보호 수준이 경계 제한 됨입니다.</span><span class="sxs-lookup"><span data-stu-id="99113-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="99113-147">이 값은 인터넷을 통해 작동 하도록 디자인 된 응용 프로그램에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99113-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="99113-148">이 설정은 Windows Teredo 구현을 사용 하 여 네트워크 주소 변환 (NAT) 통과 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="99113-149">열린 포트로 향하는 인터넷 공격에 대 한 응용 프로그램 보안을 강화 해야 하므로 이러한 응용 프로그램에서는 IPv4 방화벽이 무시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="99113-150">Windows Server 2003 및 Windows XP에서는 소켓에 IP 보호 수준에 대 한 기본값인 경계 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="99113-151">액세스가</span><span class="sxs-lookup"><span data-stu-id="99113-151">Restricted</span></span>|<span data-ttu-id="99113-152">IP 보호 수준이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99113-152">The IP protection level is restricted.</span></span> <span data-ttu-id="99113-153">이 값은 인터넷 시나리오를 구현 하지 않는 인트라넷 응용 프로그램에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99113-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="99113-154">이러한 응용 프로그램은 일반적으로 테스트 않거나 인터넷 형 공격에 대 한 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="99113-155">이 설정은 링크 로컬 에서만 트래픽이 받도록된 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="99113-156">제한 없음</span><span class="sxs-lookup"><span data-stu-id="99113-156">Unrestricted</span></span>|<span data-ttu-id="99113-157">IP 보호 수준이 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="99113-158">이 값은 기본 제공 되는 IPv6 NAT traversal 기능을 활용 하는 응용 프로그램을 포함 하 여 인터넷을 통해 작동 하도록 디자인 된 응용 프로그램에서 사용 됩니다 (예: Teredo) Windows에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="99113-159">열린 포트로 향하는 인터넷 공격에 대 한 응용 프로그램 보안을 강화 해야 하므로 이러한 응용 프로그램에서는 IPv4 방화벽이 무시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="99113-160">Windows Server 2008 R2 및 Windows Vista에서는 소켓에 IP 보호 수준에 대 한 기본 값 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="99113-161">Unspecified</span><span class="sxs-lookup"><span data-stu-id="99113-161">Unspecified</span></span>|<span data-ttu-id="99113-162">IP 보호 수준이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="99113-163">Windows 7 및 Windows Server 2008 R2에서는 소켓에 IP 보호 수준이 기본값이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="99113-164">@No__t-0 특성의 기본값은 **지정**되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="99113-165">@No__t-0 속성은 적용 가능한 구성 파일에서 `ipProtectionLevel` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="99113-166">구성 파일</span><span class="sxs-lookup"><span data-stu-id="99113-166">Configuration Files</span></span>  
 <span data-ttu-id="99113-167">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99113-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99113-168">예제</span><span class="sxs-lookup"><span data-stu-id="99113-168">Example</span></span>  
 <span data-ttu-id="99113-169">다음 예에서는 완료 포트를 사용 하도록 지정 하는 방법을 보여 줍니다. 기본값 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>은 무제한 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99113-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99113-170">참조</span><span class="sxs-lookup"><span data-stu-id="99113-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="99113-171">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="99113-171">Network Settings Schema</span></span>](index.md)
