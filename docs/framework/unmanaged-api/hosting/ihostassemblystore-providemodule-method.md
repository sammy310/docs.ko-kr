---
title: IHostAssemblyStore::ProvideModule 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078340"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="944a2-102">IHostAssemblyStore::ProvideModule 메서드</span><span class="sxs-lookup"><span data-stu-id="944a2-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="944a2-103">어셈블리 또는 연결 된 (그러나 포함이 아님) 내의 모듈 리소스 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="944a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="944a2-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="944a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="944a2-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="944a2-106">[in] 에 대 한 포인터를 [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) 요청된 된 모듈을 설명 하는 인스턴스 <xref:System.AppDomain>, 어셈블리 및 모듈 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="944a2-107">[out] 에 대 한 고유 식별자에 대 한 포인터를 `IStream` 로드 된 모듈을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="944a2-108">[out] 주소에 대 한 포인터는 `IStream` 이식 가능한 실행 파일 (PE) 이미지를 로드할 수를 포함 하는 개체 또는 모듈을 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="944a2-109">[out] 주소에 대 한 포인터는 `IStream` 요청된 된 모듈에 대 한 프로그램 디버그 (PDB) 정보를 포함 하는 개체 또는.pdb 파일을 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="944a2-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="944a2-110">Return Value</span></span>  
  
|<span data-ttu-id="944a2-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="944a2-111">HRESULT</span></span>|<span data-ttu-id="944a2-112">설명</span><span class="sxs-lookup"><span data-stu-id="944a2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="944a2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="944a2-113">S_OK</span></span>|`ProvideModule` <span data-ttu-id="944a2-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-114">returned successfully.</span></span>|  
|<span data-ttu-id="944a2-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="944a2-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="944a2-116">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="944a2-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="944a2-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="944a2-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-118">The call timed out.</span></span>|  
|<span data-ttu-id="944a2-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="944a2-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="944a2-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="944a2-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="944a2-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="944a2-122">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="944a2-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="944a2-123">E_FAIL</span></span>|<span data-ttu-id="944a2-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="944a2-125">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="944a2-126">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="944a2-127">COR_E_FILENOTFOUND (0X80070002)</span><span class="sxs-lookup"><span data-stu-id="944a2-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="944a2-128">요청 된 어셈블리 또는 연결 된 리소스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="944a2-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="944a2-129">E_NOT_SUFFICIENT_BUFFER</span></span>|`pdwModuleId` <span data-ttu-id="944a2-130">호스트를 반환 하려고 하는 식별자를 포함 하도록 충분히 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-130">is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="944a2-131">설명</span><span class="sxs-lookup"><span data-stu-id="944a2-131">Remarks</span></span>  
 <span data-ttu-id="944a2-132">에 대 한 id 값을 반환 `pdwModuleId` 호스트에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="944a2-133">식별자는 프로세스의 수명 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="944a2-134">CLR 연결 된 스트림에 대 한 고유 식별자로이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="944a2-135">값에 대해 각 값을 검사 하 `pAssemblyId` 에 대 한 호출에서 반환 된 [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 에 대 한 값과 비교 하 고 `pdwModuleId` 에 대 한 다른 호출에서 반환 된 `ProvideModule`합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="944a2-136">호스트가 다른 같은 식별자 값을 반환 하는 경우 `IStream`, CLR 해당 스트림의 내용을 이미 매핑되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="944a2-137">그렇다면 새 매핑 대신 이미지의 기존 복사본을 CLR에 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="944a2-138">따라서 식별자도 겹치지 않아야에서 반환 된 어셈블리 식별자를 사용 하 여 `ProvideAssembly`입니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="944a2-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="944a2-139">Requirements</span></span>  
 <span data-ttu-id="944a2-140">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="944a2-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="944a2-141">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="944a2-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="944a2-142">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="944a2-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="944a2-143">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="944a2-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="944a2-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="944a2-144">See also</span></span>

- [<span data-ttu-id="944a2-145">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="944a2-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="944a2-146">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="944a2-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="944a2-147">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="944a2-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
