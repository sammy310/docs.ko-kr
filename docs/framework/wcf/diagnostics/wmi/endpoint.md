---
description: '자세한 정보: 끝점'
title: 엔드포인트
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 1c28be37d1b1abfe1813e6da8903809affd309e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757464"
---
# <a name="endpoint"></a><span data-ttu-id="38a93-103">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="38a93-103">Endpoint</span></span>

<span data-ttu-id="38a93-104">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="38a93-104">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a93-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="38a93-105">Syntax</span></span>  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="38a93-106">메서드</span><span class="sxs-lookup"><span data-stu-id="38a93-106">Methods</span></span>  

 <span data-ttu-id="38a93-107">Endpoint 클래스는 다음과 같은 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-107">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="38a93-108">메서드</span><span class="sxs-lookup"><span data-stu-id="38a93-108">Method</span></span>|<span data-ttu-id="38a93-109">설명</span><span class="sxs-lookup"><span data-stu-id="38a93-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38a93-110">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="38a93-110">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="38a93-111">작업 성능 카운터 인스턴스 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-111">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="38a93-112">속성</span><span class="sxs-lookup"><span data-stu-id="38a93-112">Properties</span></span>  

 <span data-ttu-id="38a93-113">Endpoint 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-113">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="38a93-114">주소</span><span class="sxs-lookup"><span data-stu-id="38a93-114">Address</span></span>  

 <span data-ttu-id="38a93-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="38a93-115">Data type: string</span></span>  
  
 <span data-ttu-id="38a93-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-117">엔드포인트의 주소를 포함하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-117">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="38a93-118">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="38a93-118">AddressHeaders</span></span>  

 <span data-ttu-id="38a93-119">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="38a93-119">Data type: string array</span></span>  
  
 <span data-ttu-id="38a93-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-121">이 엔드포인트에 연결된 주소 헤더의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-121">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="38a93-122">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="38a93-122">AddressIdentity</span></span>  

 <span data-ttu-id="38a93-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="38a93-123">Data type: string</span></span>  
  
 <span data-ttu-id="38a93-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-125">엔드포인트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-125">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="38a93-126">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="38a93-126">AppDomainId</span></span>  

 <span data-ttu-id="38a93-127">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="38a93-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="38a93-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-129">엔드포인트를 호스트하는 appdomain의 appdomain ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-129">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="38a93-130">동작</span><span class="sxs-lookup"><span data-stu-id="38a93-130">Behaviors</span></span>  

 <span data-ttu-id="38a93-131">데이터 형식: Behavior array</span><span class="sxs-lookup"><span data-stu-id="38a93-131">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="38a93-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-133">이 엔드포인트에서 구현된 동작의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-133">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="38a93-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="38a93-134">Binding</span></span>  

 <span data-ttu-id="38a93-135">데이터 형식: 바인딩</span><span class="sxs-lookup"><span data-stu-id="38a93-135">Data type: Binding</span></span>  
  
 <span data-ttu-id="38a93-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-137">이 엔드포인트에서 사용하는 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-137">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="38a93-138">ContractName</span><span class="sxs-lookup"><span data-stu-id="38a93-138">ContractName</span></span>  

 <span data-ttu-id="38a93-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="38a93-139">Data type: string</span></span>  
  
 <span data-ttu-id="38a93-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-141">이 엔드포인트가 공개하는 계약을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-141">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="38a93-142">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="38a93-142">CounterInstanceName</span></span>  

 <span data-ttu-id="38a93-143">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="38a93-143">Data type: string</span></span>  
  
 <span data-ttu-id="38a93-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-145">엔드포인트의 성능 카운터 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-145">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="38a93-146">ListenUri</span><span class="sxs-lookup"><span data-stu-id="38a93-146">ListenUri</span></span>  

 <span data-ttu-id="38a93-147">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="38a93-147">Data type: string</span></span>  
  
 <span data-ttu-id="38a93-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-149">엔드포인트가 수신하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-149">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="38a93-150">Name</span><span class="sxs-lookup"><span data-stu-id="38a93-150">Name</span></span>  

 <span data-ttu-id="38a93-151">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="38a93-151">Data type: string</span></span>  
  
 <span data-ttu-id="38a93-152">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-153">이 엔드포인트의 고유한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-153">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="38a93-154">ProcessId</span><span class="sxs-lookup"><span data-stu-id="38a93-154">ProcessId</span></span>  

 <span data-ttu-id="38a93-155">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="38a93-155">Data type: sint32</span></span>  
  
 <span data-ttu-id="38a93-156">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-157">엔드포인트를 호스트하는 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-157">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="38a93-158">ref</span><span class="sxs-lookup"><span data-stu-id="38a93-158">ref</span></span>  

 <span data-ttu-id="38a93-159">데이터 형식: Contract</span><span class="sxs-lookup"><span data-stu-id="38a93-159">Data type: Contract</span></span>  
  
 <span data-ttu-id="38a93-160">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="38a93-160">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38a93-161">이 엔드포인트가 공개하는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-161">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a93-162">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38a93-162">Requirements</span></span>  
  
|<span data-ttu-id="38a93-163">MOF</span><span class="sxs-lookup"><span data-stu-id="38a93-163">MOF</span></span>|<span data-ttu-id="38a93-164">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-164">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="38a93-165">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="38a93-165">Namespace</span></span>|<span data-ttu-id="38a93-166">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a93-166">Defined in root\ServiceModel</span></span>|
