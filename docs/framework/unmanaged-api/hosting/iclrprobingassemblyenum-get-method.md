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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 268462db51435b87194aafc374d5d8e8ec1df165
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638653"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="e3b96-102">ICLRProbingAssemblyEnum::Get 메서드</span><span class="sxs-lookup"><span data-stu-id="e3b96-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="e3b96-103">지정된 된 인덱스에서 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b96-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3b96-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3b96-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3b96-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="e3b96-106">[in] 반환할 어셈블리 id의 0부터 시작 하는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="e3b96-107">[out] 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="e3b96-108">[out에서] 크기는 `pwzBuffer` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3b96-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e3b96-109">Return Value</span></span>  
  
|<span data-ttu-id="e3b96-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3b96-110">HRESULT</span></span>|<span data-ttu-id="e3b96-111">설명</span><span class="sxs-lookup"><span data-stu-id="e3b96-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3b96-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3b96-112">S_OK</span></span>|<span data-ttu-id="e3b96-113">`Get` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="e3b96-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e3b96-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e3b96-115">`pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="e3b96-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="e3b96-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="e3b96-117">열거형에는 더 이상 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="e3b96-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3b96-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3b96-119">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3b96-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3b96-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3b96-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-121">The call timed out.</span></span>|  
|<span data-ttu-id="e3b96-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3b96-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3b96-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3b96-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3b96-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3b96-125">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3b96-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3b96-126">E_FAIL</span></span>|<span data-ttu-id="e3b96-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3b96-128">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3b96-129">호스팅 메서드를 이후에 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3b96-130">설명</span><span class="sxs-lookup"><span data-stu-id="e3b96-130">Remarks</span></span>  
 <span data-ttu-id="e3b96-131">인덱스 0에 id에는 프로세서 아키텍처의 id가입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="e3b96-132">인덱스 1에 있는 id에는 MSIL (Microsoft intermediate language)에 대 한 아키텍처 중립 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="e3b96-133">인덱스 2에 id 아키텍처 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="e3b96-134">`Get` 두 번 호출 일반적으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-134">`Get` is typically called twice.</span></span> <span data-ttu-id="e3b96-135">첫 번째 호출에 대 한 null 값이 제공 `pwzBuffer`를 설정 하 고 `pcchBufferSize` 에 대 한 적절 한 크기로 `pwzBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="e3b96-136">두 번째 호출을 적절 하 게 크기가 제공 `pwzBuffer`, 완료 되 면 정식 어셈블리 id 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b96-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3b96-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3b96-137">Requirements</span></span>  
 <span data-ttu-id="e3b96-138">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3b96-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3b96-139">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3b96-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3b96-140">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e3b96-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3b96-141">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3b96-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b96-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3b96-142">See also</span></span>

- [<span data-ttu-id="e3b96-143">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3b96-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="e3b96-144">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3b96-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
