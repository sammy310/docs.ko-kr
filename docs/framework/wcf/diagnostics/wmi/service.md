---
description: '자세한 정보: 서비스'
title: 서비스
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: e66f9a23f8c182327899904c26ff6a6368b9bdc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715628"
---
# <a name="service"></a><span data-ttu-id="e5307-103">서비스</span><span class="sxs-lookup"><span data-stu-id="e5307-103">Service</span></span>

<span data-ttu-id="e5307-104">서비스</span><span class="sxs-lookup"><span data-stu-id="e5307-104">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5307-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5307-105">Syntax</span></span>  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e5307-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e5307-106">Methods</span></span>  

 <span data-ttu-id="e5307-107">Service 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-107">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e5307-108">속성</span><span class="sxs-lookup"><span data-stu-id="e5307-108">Properties</span></span>  

 <span data-ttu-id="e5307-109">Service 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-109">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="e5307-110">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="e5307-110">BaseAddresses</span></span>  

 <span data-ttu-id="e5307-111">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="e5307-111">Data type: string array</span></span>  
  
 <span data-ttu-id="e5307-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-113">서비스가 사용하는 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-113">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="e5307-114">동작</span><span class="sxs-lookup"><span data-stu-id="e5307-114">Behaviors</span></span>  

 <span data-ttu-id="e5307-115">데이터 형식: Behavior array</span><span class="sxs-lookup"><span data-stu-id="e5307-115">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="e5307-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-117">이 서비스와 연관된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-117">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="e5307-118">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="e5307-118">ConfigurationName</span></span>  

 <span data-ttu-id="e5307-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e5307-119">Data type: string</span></span>  
  
 <span data-ttu-id="e5307-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-121">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e5307-121">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="e5307-122">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="e5307-122">CounterInstanceName</span></span>  

 <span data-ttu-id="e5307-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e5307-123">Data type: string</span></span>  
  
 <span data-ttu-id="e5307-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-125">서비스의 성능 카운터 인스턴스의 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-125">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="e5307-126">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="e5307-126">DistinguishedName</span></span>  

 <span data-ttu-id="e5307-127">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e5307-127">Data type: string</span></span>  
  
 <span data-ttu-id="e5307-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-129">주소의 서비스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-129">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="e5307-130">확장</span><span class="sxs-lookup"><span data-stu-id="e5307-130">Extensions</span></span>  

 <span data-ttu-id="e5307-131">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="e5307-131">Data type: string array</span></span>  
  
 <span data-ttu-id="e5307-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-133">서비스 인스턴스의 확장에 대한 인스턴스 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-133">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="e5307-134">메타데이터</span><span class="sxs-lookup"><span data-stu-id="e5307-134">Metadata</span></span>  

 <span data-ttu-id="e5307-135">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="e5307-135">Data type: string array</span></span>  
  
 <span data-ttu-id="e5307-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-137">서비스 메타데이터 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-137">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="e5307-138">Name</span><span class="sxs-lookup"><span data-stu-id="e5307-138">Name</span></span>  

 <span data-ttu-id="e5307-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e5307-139">Data type: string</span></span>  
  
 <span data-ttu-id="e5307-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-141">이 서비스의 고유한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-141">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="e5307-142">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e5307-142">Namespace</span></span>  

 <span data-ttu-id="e5307-143">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e5307-143">Data type: string</span></span>  
  
 <span data-ttu-id="e5307-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-145">서비스의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-145">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="e5307-146">열림</span><span class="sxs-lookup"><span data-stu-id="e5307-146">Opened</span></span>  

 <span data-ttu-id="e5307-147">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="e5307-147">Data type: datetime</span></span>  
  
 <span data-ttu-id="e5307-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-149">서비스가 열린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-149">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="e5307-150">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="e5307-150">OutgoingChannels</span></span>  

 <span data-ttu-id="e5307-151">데이터 형식: Channel array</span><span class="sxs-lookup"><span data-stu-id="e5307-151">Data type: Channel array</span></span>  
  
 <span data-ttu-id="e5307-152">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-153">서비스 인스턴스에서 보내는 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-153">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="e5307-154">ProcessId</span><span class="sxs-lookup"><span data-stu-id="e5307-154">ProcessId</span></span>  

 <span data-ttu-id="e5307-155">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="e5307-155">Data type: sint32</span></span>  
  
 <span data-ttu-id="e5307-156">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e5307-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5307-157">서비스를 호스팅하는 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-157">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5307-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5307-158">Requirements</span></span>  
  
|<span data-ttu-id="e5307-159">MOF</span><span class="sxs-lookup"><span data-stu-id="e5307-159">MOF</span></span>|<span data-ttu-id="e5307-160">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e5307-161">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e5307-161">Namespace</span></span>|<span data-ttu-id="e5307-162">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5307-162">Defined in root\ServiceModel</span></span>|
