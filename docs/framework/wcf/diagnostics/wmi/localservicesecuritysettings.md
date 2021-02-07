---
description: '자세히 알아보기: LocalServiceSecuritySettings'
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: f7220e8253c6ab218414c1be7ed90e5d593b4692
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743943"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="61b6b-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="61b6b-103">LocalServiceSecuritySettings</span></span>

<span data-ttu-id="61b6b-104">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="61b6b-104">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61b6b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="61b6b-105">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="61b6b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="61b6b-106">Methods</span></span>  

 <span data-ttu-id="61b6b-107">LocalServiceSecuritySettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-107">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="61b6b-108">속성</span><span class="sxs-lookup"><span data-stu-id="61b6b-108">Properties</span></span>  

 <span data-ttu-id="61b6b-109">LocalServiceSecuritySettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-109">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="61b6b-110">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="61b6b-110">DetectReplays</span></span>  

 <span data-ttu-id="61b6b-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="61b6b-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="61b6b-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-113">채널에 대한 재생 공격이 검색되어 자동으로 처리되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-113">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="61b6b-114">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="61b6b-114">InactivityTimeout</span></span>  

 <span data-ttu-id="61b6b-115">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-117">서비스가 지원하는 보류 중인 보안 세션의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-117">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="61b6b-118">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-118">IssuedCookieLifetime</span></span>  

 <span data-ttu-id="61b6b-119">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-119">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-121">모든 새 보안 쿠키에 발급된 수명을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-121">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="61b6b-122">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="61b6b-122">MaxCachedCookies</span></span>  

 <span data-ttu-id="61b6b-123">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="61b6b-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="61b6b-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-125">캐시될 수 있는 최대 쿠키 수입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-125">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="61b6b-126">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="61b6b-126">MaxClockSkew</span></span>  

 <span data-ttu-id="61b6b-127">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-127">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-129">통신하는 두 상대방의 시스템 시계 사이의 최대 시간 차이를 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-129">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="61b6b-130">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="61b6b-130">MaxPendingSessions</span></span>  

 <span data-ttu-id="61b6b-131">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="61b6b-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="61b6b-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-133">서비스에서 보류 중인 최대 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-133">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="61b6b-134">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="61b6b-134">MaxStatefulNegotiations</span></span>  

 <span data-ttu-id="61b6b-135">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="61b6b-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="61b6b-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-137">동시에 활성화될 수 있는 보안 협상의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-137">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="61b6b-138">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="61b6b-138">NegotiationTimeout</span></span>  

 <span data-ttu-id="61b6b-139">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-139">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-141">서버와 클라이언트 간 보안 협상 단계에 대한 최대 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-141">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="61b6b-142">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="61b6b-142">ReconnectTransportOnFailure</span></span>  

 <span data-ttu-id="61b6b-143">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="61b6b-143">Data type: boolean</span></span>  
  
 <span data-ttu-id="61b6b-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-145">WS-Reliable Messaging을 사용하는 연결에서 전송 실패 후 다시 연결을 시도할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-145">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="61b6b-146">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="61b6b-146">ReplayCacheSize</span></span>  

 <span data-ttu-id="61b6b-147">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="61b6b-147">Data type: sint32</span></span>  
  
 <span data-ttu-id="61b6b-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-149">재생 검색에 사용되는 캐시된 nonces 수입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-149">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="61b6b-150">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="61b6b-150">ReplayWindow</span></span>  

 <span data-ttu-id="61b6b-151">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-151">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-152">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-153">개별 메시지 nonce를 사용할 수 있는 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-153">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="61b6b-154">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="61b6b-154">SessionKeyRenewalInterval</span></span>  

 <span data-ttu-id="61b6b-155">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-155">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-156">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-157">해당 기간이 지나면 개시자가 보안 세션에 대한 키를 갱신할 수 있는 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-157">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="61b6b-158">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="61b6b-158">SessionKeyRolloverInterval</span></span>  

 <span data-ttu-id="61b6b-159">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-159">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-160">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-160">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-161">키 갱신 중에 들어오는 메시지에서 이전 세션 키를 사용할 수 있는 시간 간격을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-161">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="61b6b-162">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="61b6b-162">TimestampValidityDuration</span></span>  

 <span data-ttu-id="61b6b-163">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="61b6b-163">Data type: datetime</span></span>  
  
 <span data-ttu-id="61b6b-164">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="61b6b-164">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61b6b-165">타임스탬프를 사용할 수 있는 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-165">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61b6b-166">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61b6b-166">Requirements</span></span>  
  
|<span data-ttu-id="61b6b-167">MOF</span><span class="sxs-lookup"><span data-stu-id="61b6b-167">MOF</span></span>|<span data-ttu-id="61b6b-168">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-168">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="61b6b-169">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="61b6b-169">Namespace</span></span>|<span data-ttu-id="61b6b-170">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-170">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61b6b-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61b6b-171">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
