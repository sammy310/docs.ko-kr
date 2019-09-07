---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397687"
---
# <a name="nettcp"></a><span data-ttu-id="b2a15-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="b2a15-102">\<net.tcp></span></span>
<span data-ttu-id="b2a15-103">여러 프로세스에서 동일한 TCP 포트를 공유할 수 있도록 하는 NET.TCP Port Sharing Service에 대한 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
<span data-ttu-id="b2a15-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b2a15-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b2a15-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="b2a15-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="b2a15-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<net.tcp >**</span><span class="sxs-lookup"><span data-stu-id="b2a15-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a15-107">구문</span><span class="sxs-lookup"><span data-stu-id="b2a15-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="b2a15-108">형식</span><span class="sxs-lookup"><span data-stu-id="b2a15-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2a15-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2a15-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b2a15-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2a15-111">특성</span><span class="sxs-lookup"><span data-stu-id="b2a15-111">Attributes</span></span>  
  
|<span data-ttu-id="b2a15-112">특성</span><span class="sxs-lookup"><span data-stu-id="b2a15-112">Attribute</span></span>|<span data-ttu-id="b2a15-113">설명</span><span class="sxs-lookup"><span data-stu-id="b2a15-113">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="b2a15-114">공유 연결에서 수락 되었지만 아직 WCF (Windows Communication Foundation) 서비스로 디스패치되 지 않은 미해결 연결의 최대 수를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-114">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="b2a15-115">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-115">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="b2a15-116">공유 서비스에 대한 수신 엔드포인트에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-116">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="b2a15-117">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-117">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="b2a15-118">애플리케이션에서 수락할 때까지 수신기에서 기다릴 수 있는 최대 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-118">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="b2a15-119">이 할당량 값을 초과하면 새 들어 오는 연결은 수락될 때까지 기다리지 않고 연결이 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-119">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="b2a15-120">메시지 보안과 같은 연결 기능을 통해 클라이언트가 둘 이상의 연결을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-120">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="b2a15-121">서비스 관리자는 이 할당량 값을 설정할 때 이러한 추가 연결을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-121">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="b2a15-122">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-122">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b2a15-123">프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-123">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="b2a15-124">기본값은 "00:00:10"입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-124">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="b2a15-125">포트 공유 서비스가 WCF 서비스 대신 Microsoft Teredo 서비스를 사용 하 여 TCP 포트에서 수신 하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-125">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="b2a15-126">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2a15-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2a15-127">Child Elements</span></span>  
  
|<span data-ttu-id="b2a15-128">요소</span><span class="sxs-lookup"><span data-stu-id="b2a15-128">Element</span></span>|<span data-ttu-id="b2a15-129">Description</span><span class="sxs-lookup"><span data-stu-id="b2a15-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2a15-130">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="b2a15-130">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="b2a15-131">WCF 서비스를 호스팅하고 공유 서비스에 대 `securityIdentifier` 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 특성을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-131">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2a15-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2a15-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b2a15-133">요소</span><span class="sxs-lookup"><span data-stu-id="b2a15-133">Element</span></span>|<span data-ttu-id="b2a15-134">Description</span><span class="sxs-lookup"><span data-stu-id="b2a15-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2a15-135">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="b2a15-135">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="b2a15-136">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a15-136">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2a15-137">설명</span><span class="sxs-lookup"><span data-stu-id="b2a15-137">Remarks</span></span>  
 <span data-ttu-id="b2a15-138">포트 공유에 대 한 자세한 내용은 [Net.tcp 포트 공유](../../../wcf/feature-details/net-tcp-port-sharing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2a15-138">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="b2a15-139">포트 공유 서비스를 구성 하는 방법을 이해 하려면 [Net.tcp 포트 공유 서비스 구성](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2a15-139">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a15-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2a15-140">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="b2a15-141">Net.TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="b2a15-141">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="b2a15-142">Net.TCP Port Sharing Service 구성</span><span class="sxs-lookup"><span data-stu-id="b2a15-142">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
