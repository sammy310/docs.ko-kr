---
title: 계약
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: e4a21e95a6f1f1860ed36c968d17bb8ac8465dce
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868438"
---
# <a name="contract"></a><span data-ttu-id="a26d0-102">계약</span><span class="sxs-lookup"><span data-stu-id="a26d0-102">Contract</span></span>
<span data-ttu-id="a26d0-103">계약</span><span class="sxs-lookup"><span data-stu-id="a26d0-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a26d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="a26d0-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a26d0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a26d0-105">Methods</span></span>  
 <span data-ttu-id="a26d0-106">Contract 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a26d0-107">속성</span><span class="sxs-lookup"><span data-stu-id="a26d0-107">Properties</span></span>  
 <span data-ttu-id="a26d0-108">Contract 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="a26d0-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="a26d0-109">AppDomainId</span></span>  
 <span data-ttu-id="a26d0-110">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="a26d0-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a26d0-111">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-112">계약을 호스팅하는 appdomain의 appdomain ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="a26d0-113">동작</span><span class="sxs-lookup"><span data-stu-id="a26d0-113">Behaviors</span></span>  
 <span data-ttu-id="a26d0-114">데이터 형식: 동작 배열</span><span class="sxs-lookup"><span data-stu-id="a26d0-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="a26d0-115">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-116">이 계약과 연결된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="a26d0-117">이름</span><span class="sxs-lookup"><span data-stu-id="a26d0-117">Name</span></span>  
 <span data-ttu-id="a26d0-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="a26d0-118">Data type: string</span></span>  
  
 <span data-ttu-id="a26d0-119">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-120">WSDL에 있는 계약의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="a26d0-121">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a26d0-121">Namespace</span></span>  
 <span data-ttu-id="a26d0-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="a26d0-122">Data type: string</span></span>  
  
 <span data-ttu-id="a26d0-123">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-124">WSDL에 있는 `portType` 요소의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="a26d0-125">작업</span><span class="sxs-lookup"><span data-stu-id="a26d0-125">Operations</span></span>  
 <span data-ttu-id="a26d0-126">데이터 형식: 작업 배열</span><span class="sxs-lookup"><span data-stu-id="a26d0-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="a26d0-127">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-128">이 계약의 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="a26d0-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="a26d0-129">ProcessId</span></span>  
 <span data-ttu-id="a26d0-130">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="a26d0-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="a26d0-131">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-132">계약을 호스팅하는 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a26d0-133">ref</span><span class="sxs-lookup"><span data-stu-id="a26d0-133">ref</span></span>  
 <span data-ttu-id="a26d0-134">데이터 형식: 계약</span><span class="sxs-lookup"><span data-stu-id="a26d0-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="a26d0-135">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-136">계약이 이중 계약인 경우 콜백의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="a26d0-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="a26d0-137">SessionMode</span></span>  
 <span data-ttu-id="a26d0-138">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="a26d0-138">Data type: string</span></span>  
  
 <span data-ttu-id="a26d0-139">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-140">계약에서 채널 세션을 사용하기 위해 이 계약과 연결된 바인딩이 필요한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="a26d0-141">형식</span><span class="sxs-lookup"><span data-stu-id="a26d0-141">Type</span></span>  
 <span data-ttu-id="a26d0-142">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="a26d0-142">Data type: string</span></span>  
  
 <span data-ttu-id="a26d0-143">액세스 유형: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a26d0-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a26d0-144">계약의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a26d0-145">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a26d0-145">Requirements</span></span>  
  
|<span data-ttu-id="a26d0-146">MOF</span><span class="sxs-lookup"><span data-stu-id="a26d0-146">MOF</span></span>|<span data-ttu-id="a26d0-147">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a26d0-148">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a26d0-148">Namespace</span></span>|<span data-ttu-id="a26d0-149">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26d0-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a26d0-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="a26d0-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
