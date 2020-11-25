---
title: ICLRProbingAssemblyEnum::Get 메서드
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
ms.openlocfilehash: 9a6145ff2874890f052f18a7e537e20ff259933c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728942"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="b15f9-102">ICLRProbingAssemblyEnum::Get 메서드</span><span class="sxs-lookup"><span data-stu-id="b15f9-102">ICLRProbingAssemblyEnum::Get Method</span></span>

<span data-ttu-id="b15f9-103">지정 된 인덱스에 있는 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="b15f9-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b15f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b15f9-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="b15f9-106">진행 반환할 어셈블리 id의 인덱스 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="b15f9-107">제한이 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="b15f9-108">[in, out] 버퍼의 크기 `pwzBuffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b15f9-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="b15f9-109">Return Value</span></span>  
  
|<span data-ttu-id="b15f9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b15f9-110">HRESULT</span></span>|<span data-ttu-id="b15f9-111">설명</span><span class="sxs-lookup"><span data-stu-id="b15f9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b15f9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b15f9-112">S_OK</span></span>|<span data-ttu-id="b15f9-113">`Get` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="b15f9-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b15f9-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b15f9-115">`pwzBuffer`가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="b15f9-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="b15f9-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="b15f9-117">열거형에 항목이 더 이상 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="b15f9-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b15f9-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b15f9-119">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b15f9-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b15f9-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b15f9-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-121">The call timed out.</span></span>|  
|<span data-ttu-id="b15f9-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b15f9-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b15f9-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b15f9-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b15f9-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b15f9-125">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b15f9-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b15f9-126">E_FAIL</span></span>|<span data-ttu-id="b15f9-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b15f9-128">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b15f9-129">모든 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b15f9-130">설명</span><span class="sxs-lookup"><span data-stu-id="b15f9-130">Remarks</span></span>  

 <span data-ttu-id="b15f9-131">인덱스 0의 id는 프로세서 아키텍처와 관련 된 id입니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="b15f9-132">인덱스 1의 id는 MSIL (Microsoft 중간 언어)에 대 한 아키텍처 중립적인 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="b15f9-133">인덱스 2의 id에 아키텍처 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="b15f9-134">`Get` 는 일반적으로 두 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-134">`Get` is typically called twice.</span></span> <span data-ttu-id="b15f9-135">첫 번째 호출은에 대해 null 값을 제공 하 `pwzBuffer` 고 `pcchBufferSize` 에 적절 한 크기로 설정 합니다 `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="b15f9-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="b15f9-136">두 번째 호출은 적절 한 크기 `pwzBuffer` 를 제공 하 고 완료 시 정식 어셈블리 id 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b15f9-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b15f9-137">Requirements</span></span>  

 <span data-ttu-id="b15f9-138">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b15f9-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b15f9-139">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b15f9-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b15f9-140">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b15f9-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b15f9-141">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b15f9-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15f9-142">참조</span><span class="sxs-lookup"><span data-stu-id="b15f9-142">See also</span></span>

- [<span data-ttu-id="b15f9-143">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b15f9-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="b15f9-144">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b15f9-144">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
