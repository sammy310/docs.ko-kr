---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: dd984b2ab89060451b1b2d02c324e803766908ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397725"
---
# <a name="netpipe"></a><span data-ttu-id="9e07e-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="9e07e-102">\<net.pipe></span></span>
<span data-ttu-id="9e07e-103">명명된 파이프 연결의 수명을 관리하고 명명된 파이프을 통해 수신되는 활성화 요청을 처리하는 Named Pipe Activation Service의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
<span data-ttu-id="9e07e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e07e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9e07e-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="9e07e-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="9e07e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<net.pipe >**</span><span class="sxs-lookup"><span data-stu-id="9e07e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e07e-107">구문</span><span class="sxs-lookup"><span data-stu-id="9e07e-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="9e07e-108">형식</span><span class="sxs-lookup"><span data-stu-id="9e07e-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e07e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9e07e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9e07e-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e07e-111">특성</span><span class="sxs-lookup"><span data-stu-id="9e07e-111">Attributes</span></span>  
  
|<span data-ttu-id="9e07e-112">특성</span><span class="sxs-lookup"><span data-stu-id="9e07e-112">Attribute</span></span>|<span data-ttu-id="9e07e-113">Description</span><span class="sxs-lookup"><span data-stu-id="9e07e-113">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="9e07e-114">공유 서비스에 대한 수신 엔드포인트에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-114">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="9e07e-115">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-115">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="9e07e-116">디스패치를 대기할 수 있는 최대 연결 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-116">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="9e07e-117">기본값은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-117">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="9e07e-118">프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-118">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="9e07e-119">기본값은 "00:00:10"입니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-119">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e07e-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9e07e-120">Child Elements</span></span>  
  
|<span data-ttu-id="9e07e-121">요소</span><span class="sxs-lookup"><span data-stu-id="9e07e-121">Element</span></span>|<span data-ttu-id="9e07e-122">설명</span><span class="sxs-lookup"><span data-stu-id="9e07e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e07e-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="9e07e-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="9e07e-124">WCF 서비스를 호스팅하고 공유 서비스에 대 `securityIdentifier` 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 특성을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e07e-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9e07e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9e07e-126">요소</span><span class="sxs-lookup"><span data-stu-id="9e07e-126">Element</span></span>|<span data-ttu-id="9e07e-127">Description</span><span class="sxs-lookup"><span data-stu-id="9e07e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e07e-128">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="9e07e-128">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="9e07e-129">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9e07e-129">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e07e-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e07e-130">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
