---
title: IHostAssemblyStore::ProvideAssembly 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 778664dea16c5183945e25e0261f4a65bb646ac0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467976"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="e404d-102">IHostAssemblyStore::ProvideAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e404d-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="e404d-103">참조 되지 않은 어셈블리에 대 한 참조를 가져옵니다 합니다 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에서 반환 되는 [ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="e404d-104">호출 하는 CLR (공용 언어 런타임) `ProvideAssembly` 목록에 나타나지 않는 각 어셈블리에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e404d-105">구문</span><span class="sxs-lookup"><span data-stu-id="e404d-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e404d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e404d-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="e404d-107">[in] 에 대 한 포인터를 [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) 버전 관리 정책의 유무를 포함 하 여 특정 바인딩 특성을 결정 하는 호스트 인스턴스 및 바인딩할 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="e404d-108">[out] 이 요청된 된 어셈블리에 대 한 고유 식별자에 대 한 포인터 `IStream`합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="e404d-109">[out] 플랫폼에 대 한 필요 없이 요청된 된 어셈블리의 증명 정보를 확인 하는 데 사용 되는 호스트 관련 데이터에 대 한 포인터를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="e404d-110">`pHostContext` 에 해당 하는 <xref:System.Reflection.Assembly.HostContext%2A> 관리 되는 속성 <xref:System.Reflection.Assembly> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="e404d-111">[out] 주소에 대 한 포인터는 `IStream` 를 로드할 어셈블리를 찾을 수 없는 경우 null 또는 이식 가능한 실행 파일 (PE) 이미지를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="e404d-112">[out] 주소에 대 한 포인터는 `IStream` 경우 포함 된 null을 프로그램 디버그 (PDB) 정보를.pdb 파일을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e404d-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="e404d-113">Return Value</span></span>  
  
|<span data-ttu-id="e404d-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e404d-114">HRESULT</span></span>|<span data-ttu-id="e404d-115">설명</span><span class="sxs-lookup"><span data-stu-id="e404d-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e404d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="e404d-116">S_OK</span></span>|<span data-ttu-id="e404d-117">`ProvideAssembly` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="e404d-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e404d-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e404d-119">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e404d-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e404d-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e404d-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-121">The call timed out.</span></span>|  
|<span data-ttu-id="e404d-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e404d-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e404d-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e404d-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e404d-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e404d-125">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e404d-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e404d-126">E_FAIL</span></span>|<span data-ttu-id="e404d-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e404d-128">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e404d-129">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e404d-130">COR_E_FILENOTFOUND (0X80070002)</span><span class="sxs-lookup"><span data-stu-id="e404d-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="e404d-131">요청된 된 어셈블리를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="e404d-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e404d-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e404d-133">지정 된 버퍼 크기가 `pAssemblyId` 호스트 반환 하려고 하는 식별자를 보유할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e404d-134">설명</span><span class="sxs-lookup"><span data-stu-id="e404d-134">Remarks</span></span>  
 <span data-ttu-id="e404d-135">에 대 한 id 값을 반환 `pAssemblyId` 호스트에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="e404d-136">식별자는 프로세스의 수명 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="e404d-137">CLR은 스트림에 대 한 고유 식별자로이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="e404d-138">값에 대해 각 값을 검사 `pAssemblyId` 에 대 한 다른 호출에서 반환 된 `ProvideAssembly`합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="e404d-139">동일한 호스트 반환 `pAssemblyId` 다른 값 `IStream`, CLR 해당 스트림의 내용을 이미 매핑되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="e404d-140">그렇다면 런타임 대신 새 이미지의 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e404d-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e404d-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e404d-141">Requirements</span></span>  
 <span data-ttu-id="e404d-142">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e404d-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e404d-143">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e404d-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e404d-144">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e404d-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e404d-145">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e404d-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e404d-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="e404d-146">See also</span></span>
- [<span data-ttu-id="e404d-147">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e404d-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e404d-148">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e404d-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="e404d-149">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e404d-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
