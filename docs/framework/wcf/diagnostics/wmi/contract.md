---
description: '자세한 정보: 계약'
title: 계약
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 3443a7d2eed1a34f07495bd3ceb98c1ba997fabf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757555"
---
# <a name="contract"></a><span data-ttu-id="9b677-103">계약</span><span class="sxs-lookup"><span data-stu-id="9b677-103">Contract</span></span>

<span data-ttu-id="9b677-104">계약</span><span class="sxs-lookup"><span data-stu-id="9b677-104">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b677-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b677-105">Syntax</span></span>  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9b677-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9b677-106">Methods</span></span>  

 <span data-ttu-id="9b677-107">Contract 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-107">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9b677-108">속성</span><span class="sxs-lookup"><span data-stu-id="9b677-108">Properties</span></span>  

 <span data-ttu-id="9b677-109">Contract 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-109">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="9b677-110">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="9b677-110">AppDomainId</span></span>  

 <span data-ttu-id="9b677-111">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9b677-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="9b677-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-113">계약을 호스팅하는 appdomain의 appdomain ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-113">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="9b677-114">동작</span><span class="sxs-lookup"><span data-stu-id="9b677-114">Behaviors</span></span>  

 <span data-ttu-id="9b677-115">데이터 형식: Behavior array</span><span class="sxs-lookup"><span data-stu-id="9b677-115">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="9b677-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-117">이 계약과 연결된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-117">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="9b677-118">Name</span><span class="sxs-lookup"><span data-stu-id="9b677-118">Name</span></span>  

 <span data-ttu-id="9b677-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9b677-119">Data type: string</span></span>  
  
 <span data-ttu-id="9b677-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-121">WSDL에 있는 계약의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-121">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="9b677-122">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9b677-122">Namespace</span></span>  

 <span data-ttu-id="9b677-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9b677-123">Data type: string</span></span>  
  
 <span data-ttu-id="9b677-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-125">WSDL에 있는 `portType` 요소의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-125">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="9b677-126">작업</span><span class="sxs-lookup"><span data-stu-id="9b677-126">Operations</span></span>  

 <span data-ttu-id="9b677-127">데이터 형식: Operation array</span><span class="sxs-lookup"><span data-stu-id="9b677-127">Data type: Operation array</span></span>  
  
 <span data-ttu-id="9b677-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-129">이 계약의 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-129">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="9b677-130">ProcessId</span><span class="sxs-lookup"><span data-stu-id="9b677-130">ProcessId</span></span>  

 <span data-ttu-id="9b677-131">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9b677-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="9b677-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-133">계약을 호스팅하는 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-133">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9b677-134">ref</span><span class="sxs-lookup"><span data-stu-id="9b677-134">ref</span></span>  

 <span data-ttu-id="9b677-135">데이터 형식: Contract</span><span class="sxs-lookup"><span data-stu-id="9b677-135">Data type: Contract</span></span>  
  
 <span data-ttu-id="9b677-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-137">계약이 이중 계약인 경우 콜백의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-137">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="9b677-138">SessionMode</span><span class="sxs-lookup"><span data-stu-id="9b677-138">SessionMode</span></span>  

 <span data-ttu-id="9b677-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9b677-139">Data type: string</span></span>  
  
 <span data-ttu-id="9b677-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-141">계약에서 채널 세션을 사용하기 위해 이 계약과 연결된 바인딩이 필요한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-141">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="9b677-142">Type</span><span class="sxs-lookup"><span data-stu-id="9b677-142">Type</span></span>  

 <span data-ttu-id="9b677-143">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9b677-143">Data type: string</span></span>  
  
 <span data-ttu-id="9b677-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9b677-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b677-145">계약의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-145">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b677-146">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b677-146">Requirements</span></span>  
  
|<span data-ttu-id="9b677-147">MOF</span><span class="sxs-lookup"><span data-stu-id="9b677-147">MOF</span></span>|<span data-ttu-id="9b677-148">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-148">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9b677-149">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9b677-149">Namespace</span></span>|<span data-ttu-id="9b677-150">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b677-150">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b677-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b677-151">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
