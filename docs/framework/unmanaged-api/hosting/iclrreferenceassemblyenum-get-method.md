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
ms.openlocfilehash: 5afa7b37b804b6a11a894e0e6c7708c7787a20ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703356"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="b57bd-102">ICLRReferenceAssemblyEnum::Get 메서드</span><span class="sxs-lookup"><span data-stu-id="b57bd-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="b57bd-103">제공 된 인덱스에서 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="b57bd-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b57bd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b57bd-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="b57bd-106">진행 반환할 어셈블리 id의 인덱스 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="b57bd-107">제한이 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="b57bd-108">[in, out] 버퍼의 크기 `pwzBuffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b57bd-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="b57bd-109">Return Value</span></span>  
  
|<span data-ttu-id="b57bd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b57bd-110">HRESULT</span></span>|<span data-ttu-id="b57bd-111">설명</span><span class="sxs-lookup"><span data-stu-id="b57bd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b57bd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b57bd-112">S_OK</span></span>|<span data-ttu-id="b57bd-113">`Get`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="b57bd-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b57bd-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b57bd-115">`pwzBuffer`가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="b57bd-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="b57bd-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="b57bd-117">열거형에 항목이 더 이상 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="b57bd-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b57bd-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b57bd-119">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b57bd-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b57bd-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b57bd-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-121">The call timed out.</span></span>|  
|<span data-ttu-id="b57bd-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b57bd-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b57bd-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b57bd-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b57bd-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b57bd-125">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b57bd-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b57bd-126">E_FAIL</span></span>|<span data-ttu-id="b57bd-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b57bd-128">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b57bd-129">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b57bd-130">설명</span><span class="sxs-lookup"><span data-stu-id="b57bd-130">Remarks</span></span>  
 <span data-ttu-id="b57bd-131">`Get`는 일반적으로 두 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-131">`Get` is typically called twice.</span></span> <span data-ttu-id="b57bd-132">첫 번째 호출은에 대해 null 값을 제공 하 `pwzBuffer` 고 `pcchBufferSize` 에 적절 한 크기로 설정 합니다 `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="b57bd-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="b57bd-133">두 번째 호출은 적절 한 크기 `pwzBuffer` 를 제공 하 고 완료 시 정식 어셈블리 id 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b57bd-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b57bd-134">Requirements</span></span>  
 <span data-ttu-id="b57bd-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b57bd-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b57bd-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b57bd-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b57bd-137">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57bd-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b57bd-138">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b57bd-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57bd-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b57bd-139">See also</span></span>

- [<span data-ttu-id="b57bd-140">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b57bd-140">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b57bd-141">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b57bd-141">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
