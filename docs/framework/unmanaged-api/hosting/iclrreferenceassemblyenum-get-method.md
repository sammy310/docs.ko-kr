---
title: ICLRReferenceAssemblyEnum::Get 메서드
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a69e32d418478071f9b99a391e6bef9095d6f4ad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749927"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="81892-102">ICLRReferenceAssemblyEnum::Get 메서드</span><span class="sxs-lookup"><span data-stu-id="81892-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="81892-103">제공 된 인덱스에 있는 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81892-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81892-104">구문</span><span class="sxs-lookup"><span data-stu-id="81892-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81892-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81892-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="81892-106">[in] 반환할 어셈블리 id의 0부터 시작 하는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="81892-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="81892-107">[out] 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="81892-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="81892-108">[out에서] 크기는 `pwzBuffer` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="81892-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81892-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="81892-109">Return Value</span></span>  
  
|<span data-ttu-id="81892-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81892-110">HRESULT</span></span>|<span data-ttu-id="81892-111">설명</span><span class="sxs-lookup"><span data-stu-id="81892-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81892-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="81892-112">S_OK</span></span>|<span data-ttu-id="81892-113">`Get` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="81892-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="81892-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="81892-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="81892-115">`pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="81892-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="81892-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="81892-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="81892-117">열거형에는 더 이상 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81892-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="81892-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81892-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81892-119">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81892-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81892-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81892-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81892-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81892-121">The call timed out.</span></span>|  
|<span data-ttu-id="81892-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81892-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81892-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81892-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81892-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81892-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81892-125">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81892-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81892-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81892-126">E_FAIL</span></span>|<span data-ttu-id="81892-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="81892-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81892-128">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81892-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81892-129">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="81892-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81892-130">설명</span><span class="sxs-lookup"><span data-stu-id="81892-130">Remarks</span></span>  
 <span data-ttu-id="81892-131">`Get` 두 번 호출 일반적으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81892-131">`Get` is typically called twice.</span></span> <span data-ttu-id="81892-132">첫 번째 호출에 대 한 null 값이 제공 `pwzBuffer`를 설정 하 고 `pcchBufferSize` 에 대 한 적절 한 크기로 `pwzBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="81892-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="81892-133">두 번째 호출을 적절 하 게 크기가 제공 `pwzBuffer`, 완료 되 면 정식 어셈블리 id 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="81892-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81892-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81892-134">Requirements</span></span>  
 <span data-ttu-id="81892-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81892-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81892-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81892-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81892-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="81892-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81892-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81892-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81892-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="81892-139">See also</span></span>

- [<span data-ttu-id="81892-140">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81892-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="81892-141">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81892-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
