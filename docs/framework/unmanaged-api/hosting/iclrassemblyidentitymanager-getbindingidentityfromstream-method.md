---
description: '자세히 알아보기: ICLRAssemblyIdentityManager:: GetBindingIdentityFromStream 메서드'
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
ms.openlocfilehash: aed5968a5f5c22a2f5cbea66a350dbe452368325
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716891"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="45ed4-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="45ed4-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>

<span data-ttu-id="45ed4-104">지정 된 스트림의 어셈블리에 대 한 정식 어셈블리 id 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-104">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ed4-105">구문</span><span class="sxs-lookup"><span data-stu-id="45ed4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45ed4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45ed4-106">Parameters</span></span>  

 `pStream`  
 <span data-ttu-id="45ed4-107">진행 평가할 어셈블리 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-107">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="45ed4-108">진행 향후 확장성을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-108">[in] Provided for future extensibility.</span></span> <span data-ttu-id="45ed4-109">현재 버전의 CLR (공용 언어 런타임)에서 지 원하는 유일한 값은 CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT입니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="45ed4-110">제한이 불투명 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="45ed4-111">[in, out] 의 크기 `pwzBuffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-111">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45ed4-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="45ed4-112">Return Value</span></span>  
  
|<span data-ttu-id="45ed4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45ed4-113">HRESULT</span></span>|<span data-ttu-id="45ed4-114">설명</span><span class="sxs-lookup"><span data-stu-id="45ed4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45ed4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="45ed4-115">S_OK</span></span>|<span data-ttu-id="45ed4-116">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="45ed4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="45ed4-117">E_INVALIDARG</span></span>|<span data-ttu-id="45ed4-118">제공 된 `pStream` 가 null 인 경우</span><span class="sxs-lookup"><span data-stu-id="45ed4-118">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="45ed4-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="45ed4-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="45ed4-120">의 크기가 `pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="45ed4-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="45ed4-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="45ed4-122">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="45ed4-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="45ed4-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="45ed4-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-124">The call timed out.</span></span>|  
|<span data-ttu-id="45ed4-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="45ed4-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="45ed4-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="45ed4-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="45ed4-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="45ed4-128">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="45ed4-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="45ed4-129">E_FAIL</span></span>|<span data-ttu-id="45ed4-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="45ed4-131">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="45ed4-132">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45ed4-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45ed4-133">Requirements</span></span>  

 <span data-ttu-id="45ed4-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45ed4-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ed4-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="45ed4-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45ed4-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ed4-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45ed4-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45ed4-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ed4-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45ed4-138">See also</span></span>

- [<span data-ttu-id="45ed4-139">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45ed4-139">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="45ed4-140">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45ed4-140">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
