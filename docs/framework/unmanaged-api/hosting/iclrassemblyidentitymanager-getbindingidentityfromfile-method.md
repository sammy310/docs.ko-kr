---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3d5e53dd0845fbd01dbd9d20ce8feef12748c04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213925"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="4ace4-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="4ace4-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="4ace4-103">지정된 된 파일 경로에서 어셈블리에 대 한 데이터 바인딩 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ace4-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ace4-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ace4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ace4-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="4ace4-106">[in] 평가할 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4ace4-107">[in] 값을 [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) 어셈블리의 id 유형을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="4ace4-108">향후 확장성을 위해 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-108">Provided for future extensibility.</span></span> <span data-ttu-id="4ace4-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT에는 CLR (공용 언어 런타임) 버전 2.0 지 원하는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="4ace4-110">[out] 불투명 한 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="4ace4-111">[out에서] 크기에 대 한 포인터 `pwzBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ace4-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="4ace4-112">Return Value</span></span>  
  
|<span data-ttu-id="4ace4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ace4-113">HRESULT</span></span>|<span data-ttu-id="4ace4-114">설명</span><span class="sxs-lookup"><span data-stu-id="4ace4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ace4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ace4-115">S_OK</span></span>|<span data-ttu-id="4ace4-116">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="4ace4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4ace4-117">E_INVALIDARG</span></span>|<span data-ttu-id="4ace4-118">제공 된 `pwzFilePath` null입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="4ace4-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4ace4-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4ace4-120">크기 `pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="4ace4-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4ace4-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ace4-122">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4ace4-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4ace4-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4ace4-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-124">The call timed out.</span></span>|  
|<span data-ttu-id="4ace4-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4ace4-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4ace4-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4ace4-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4ace4-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4ace4-128">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4ace4-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ace4-129">E_FAIL</span></span>|<span data-ttu-id="4ace4-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4ace4-131">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4ace4-132">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ace4-133">설명</span><span class="sxs-lookup"><span data-stu-id="4ace4-133">Remarks</span></span>  
 `GetBindingIdentityFromFile` <span data-ttu-id="4ace4-134">두 번 호출 일반적으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-134">is typically called twice.</span></span> <span data-ttu-id="4ace4-135">첫 번째 호출에 대 한 null 값이 제공 `pwzBuffer`에서 적절 한 크기를 반환 하는 메서드 및 `pcchBufferSize`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="4ace4-136">두 번째 호출을 적절 하 게 할당 된 버퍼를 제공 하 고 메서드 완료 시 실제 버퍼 데이터를 사용 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace4-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ace4-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ace4-137">Requirements</span></span>  
 <span data-ttu-id="4ace4-138">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ace4-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ace4-139">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4ace4-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ace4-140">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4ace4-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4ace4-141">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="4ace4-141">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4ace4-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ace4-142">See also</span></span>

- [<span data-ttu-id="4ace4-143">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ace4-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4ace4-144">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ace4-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4ace4-145">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ace4-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
