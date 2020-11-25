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
ms.openlocfilehash: 35805d277774e1de03bb7dee1740a2e1305a97c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732998"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="e2904-102">IHostAssemblyStore::ProvideModule 메서드</span><span class="sxs-lookup"><span data-stu-id="e2904-102">IHostAssemblyStore::ProvideModule Method</span></span>

<span data-ttu-id="e2904-103">어셈블리 또는 연결 된 (포함 된) 리소스 파일 내에서 모듈을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2904-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2904-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2904-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2904-105">Parameters</span></span>  

 `pBindInfo`  
 <span data-ttu-id="e2904-106">진행 요청 된 모듈의, 어셈블리 및 모듈 이름을 설명 하는 [Modulebindinfo](modulebindinfo-structure.md) 인스턴스에 대 한 포인터입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="e2904-106">[in] A pointer to a [ModuleBindInfo](modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="e2904-107">제한이 로드 된 모듈을 포함 하는의 고유 식별자에 대 한 포인터 `IStream` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="e2904-108">제한이 `IStream` 로드할 PE (이식 가능한 실행) 이미지를 포함 하는 개체의 주소에 대 한 포인터 이거나, 모듈을 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="e2904-109">제한이 `IStream` 요청 된 모듈에 대 한 pdb (프로그램 디버그) 정보를 포함 하는 개체의 주소에 대 한 포인터 이거나 .pdb 파일을 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2904-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="e2904-110">Return Value</span></span>  
  
|<span data-ttu-id="e2904-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2904-111">HRESULT</span></span>|<span data-ttu-id="e2904-112">설명</span><span class="sxs-lookup"><span data-stu-id="e2904-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2904-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2904-113">S_OK</span></span>|<span data-ttu-id="e2904-114">`ProvideModule` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="e2904-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2904-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2904-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e2904-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e2904-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e2904-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-118">The call timed out.</span></span>|  
|<span data-ttu-id="e2904-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e2904-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e2904-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e2904-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e2904-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e2904-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e2904-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2904-123">E_FAIL</span></span>|<span data-ttu-id="e2904-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e2904-125">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e2904-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e2904-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="e2904-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="e2904-128">요청 된 어셈블리 또는 링크 된 리소스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="e2904-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e2904-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e2904-130">`pdwModuleId` 는 호스트가 반환 하려고 하는 식별자를 포함 하기에 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2904-131">설명</span><span class="sxs-lookup"><span data-stu-id="e2904-131">Remarks</span></span>  

 <span data-ttu-id="e2904-132">에 대해 반환 된 id 값은 `pdwModuleId` 호스트에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="e2904-133">식별자는 프로세스의 수명 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="e2904-134">CLR은이 값을 연결 된 스트림에 대 한 고유 식별자로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="e2904-135">`pAssemblyId` [ProvideAssembly](ihostassemblystore-provideassembly-method.md) 에 대 한 호출에 의해 반환 되는 값과에 대 한 `pdwModuleId` 다른 호출에서 반환 된 값에 대해 각 값을 검사 `ProvideModule` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="e2904-136">호스트에서 다른에 대해 동일한 id 값을 반환 하는 경우 `IStream` CLR은 해당 스트림의 내용이 이미 매핑 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="e2904-137">그렇다면 CLR은 새 이미지를 매핑하는 대신 이미지의 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="e2904-138">따라서 식별자도에서 반환 된 어셈블리 식별자와 겹치면 안 `ProvideAssembly` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2904-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2904-139">Requirements</span></span>  

 <span data-ttu-id="e2904-140">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2904-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2904-141">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e2904-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2904-142">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2904-143">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2904-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2904-144">참조</span><span class="sxs-lookup"><span data-stu-id="e2904-144">See also</span></span>

- [<span data-ttu-id="e2904-145">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2904-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e2904-146">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2904-146">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="e2904-147">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2904-147">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
