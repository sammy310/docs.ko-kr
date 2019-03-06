---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cabf9d059a14411af48c165ab9c913156e696a4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500748"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="8bb5d-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb5d-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="8bb5d-103">가져옵니다는 [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) 지정 된 id 형식 사용 하 여 어셈블리에서 참조 된 어셈블리 id에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bb5d-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bb5d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bb5d-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="8bb5d-106">[in] WinNT.h에 정의 된 대로 프로세서 아키텍처를 지정 하는 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8bb5d-107">[in] 향후 확장성을 위해 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="8bb5d-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT에는 CLR (공용 언어 런타임)의 현재 버전을 지 원하는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="8bb5d-109">[in] 일반적으로 호출에서 반환 되는 불투명 한 어셈블리 바인딩 id에는 [iclrassemblyidentitymanager:: Getbindingidentityfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) 또는 [iclrassemblyidentitymanager:: Getbindingidentityfromstream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="8bb5d-110">[out] 에 대 한 인터페이스 포인터를 `ICLRProbingAssemblyEnum` 으로 식별 되는 어셈블리가 참조 하는 어셈블리에 대 한 참조를 포함 하는 열거자 `pwzReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bb5d-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="8bb5d-111">Return Value</span></span>  
  
|<span data-ttu-id="8bb5d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8bb5d-112">HRESULT</span></span>|<span data-ttu-id="8bb5d-113">설명</span><span class="sxs-lookup"><span data-stu-id="8bb5d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bb5d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8bb5d-114">S_OK</span></span>|<span data-ttu-id="8bb5d-115">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="8bb5d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8bb5d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8bb5d-117">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8bb5d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8bb5d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8bb5d-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-119">The call timed out.</span></span>|  
|<span data-ttu-id="8bb5d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8bb5d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8bb5d-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8bb5d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8bb5d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8bb5d-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8bb5d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8bb5d-124">E_FAIL</span></span>|<span data-ttu-id="8bb5d-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8bb5d-126">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8bb5d-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8bb5d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bb5d-128">Requirements</span></span>  
 <span data-ttu-id="8bb5d-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bb5d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb5d-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8bb5d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8bb5d-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8bb5d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bb5d-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb5d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb5d-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="8bb5d-133">See also</span></span>
- [<span data-ttu-id="8bb5d-134">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb5d-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8bb5d-135">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb5d-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8bb5d-136">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb5d-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
