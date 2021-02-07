---
description: '자세히 알아보기: AppDomainInfo'
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 1e527f2a25c48a3bf35d974e3ac192d937a8a86e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757971"
---
# <a name="appdomaininfo"></a><span data-ttu-id="359dd-103">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="359dd-103">AppDomainInfo</span></span>

<span data-ttu-id="359dd-104">애플리케이션 도메인 정보</span><span class="sxs-lookup"><span data-stu-id="359dd-104">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359dd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="359dd-105">Syntax</span></span>  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="359dd-106">메서드</span><span class="sxs-lookup"><span data-stu-id="359dd-106">Methods</span></span>  

 <span data-ttu-id="359dd-107">AppDomainInfo 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-107">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="359dd-108">속성</span><span class="sxs-lookup"><span data-stu-id="359dd-108">Properties</span></span>  

 <span data-ttu-id="359dd-109">AppDomainInfo 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-109">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="359dd-110">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="359dd-110">AppDomainId</span></span>  

 <span data-ttu-id="359dd-111">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="359dd-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="359dd-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-113">appdomain의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-113">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="359dd-114">IsDefault</span><span class="sxs-lookup"><span data-stu-id="359dd-114">IsDefault</span></span>  

 <span data-ttu-id="359dd-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="359dd-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="359dd-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-117">appdomain이 기본 appdomain인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-117">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="359dd-118">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="359dd-118">LogMalformedMessages</span></span>  

 <span data-ttu-id="359dd-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="359dd-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="359dd-120">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="359dd-120">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="359dd-121">잘못된 형식의 메시지를 기록할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-121">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="359dd-122">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="359dd-122">LogMessagesAtServiceLevel</span></span>  

 <span data-ttu-id="359dd-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="359dd-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="359dd-124">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="359dd-124">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="359dd-125">암호화 및 전송 관련 변형 전에 메시지를 서비스 수준에서 추적할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-125">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="359dd-126">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="359dd-126">LogMessagesAtTransportLevel</span></span>  

 <span data-ttu-id="359dd-127">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="359dd-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="359dd-128">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="359dd-128">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="359dd-129">메시지를 전송 수준에서 추적할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-129">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="359dd-130">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="359dd-130">MessageLoggingTraceListeners</span></span>  

 <span data-ttu-id="359dd-131">데이터 형식: TraceListener 배열</span><span class="sxs-lookup"><span data-stu-id="359dd-131">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="359dd-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-133">System.Wmi.MessageLogging 추적 소스를 수신 대기하는 컬렉션 추적 수신기입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-133">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="359dd-134">Name</span><span class="sxs-lookup"><span data-stu-id="359dd-134">Name</span></span>  

 <span data-ttu-id="359dd-135">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="359dd-135">Data type: string</span></span>  
  
 <span data-ttu-id="359dd-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-137">appdomain의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-137">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="359dd-138">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="359dd-138">PerformanceCounters</span></span>  

 <span data-ttu-id="359dd-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="359dd-139">Data type: string</span></span>  
  
 <span data-ttu-id="359dd-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-141">appdomain의 활성 성능 카운터의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-141">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="359dd-142">ProcessId</span><span class="sxs-lookup"><span data-stu-id="359dd-142">ProcessId</span></span>  

 <span data-ttu-id="359dd-143">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="359dd-143">Data type: sint32</span></span>  
  
 <span data-ttu-id="359dd-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-145">프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-145">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="359dd-146">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="359dd-146">ServiceConfigPath</span></span>  

 <span data-ttu-id="359dd-147">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="359dd-147">Data type: string</span></span>  
  
 <span data-ttu-id="359dd-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-149">서비스의 구성 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-149">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="359dd-150">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="359dd-150">TraceLevel</span></span>  

 <span data-ttu-id="359dd-151">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="359dd-151">Data type: string</span></span>  
  
 <span data-ttu-id="359dd-152">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="359dd-152">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="359dd-153">System.Wmi 추적 소스의 추적 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-153">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="359dd-154">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="359dd-154">ServiceModelTraceListeners</span></span>  

 <span data-ttu-id="359dd-155">데이터 형식: TraceListener 배열</span><span class="sxs-lookup"><span data-stu-id="359dd-155">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="359dd-156">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="359dd-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="359dd-157">System.ServiceModel 추적 소스의 수신기 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-157">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="359dd-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="359dd-158">Requirements</span></span>  
  
|<span data-ttu-id="359dd-159">MOF</span><span class="sxs-lookup"><span data-stu-id="359dd-159">MOF</span></span>|<span data-ttu-id="359dd-160">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="359dd-161">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="359dd-161">Namespace</span></span>|<span data-ttu-id="359dd-162">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="359dd-162">Defined in root\ServiceModel</span></span>|
