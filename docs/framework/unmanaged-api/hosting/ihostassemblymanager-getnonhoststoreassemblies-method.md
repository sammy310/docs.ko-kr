---
title: IHostAssemblyManager::GetNonHostStoreAssemblies 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
ms.openlocfilehash: 0dc2f625da7f4e37583f198c8d6dba86f6dcdb10
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805061"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="dc430-102">IHostAssemblyManager::GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="dc430-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="dc430-103">호스트에서 CLR (공용 언어 런타임)을 로드 하는 데 필요한 어셈블리 목록을 나타내는 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc430-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc430-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc430-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc430-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="dc430-106">제한이 `ICLRAssemblyReferenceList`호스트가 CLR에서 로드할 것으로 예상 하는 어셈블리에 대 한 참조 목록을 포함 하는의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc430-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="dc430-107">Return Value</span></span>  
  
|<span data-ttu-id="dc430-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc430-108">HRESULT</span></span>|<span data-ttu-id="dc430-109">Description</span><span class="sxs-lookup"><span data-stu-id="dc430-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc430-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc430-110">S_OK</span></span>|<span data-ttu-id="dc430-111">`GetNonHostStoreAssemblies`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="dc430-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc430-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc430-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc430-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc430-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc430-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-115">The call timed out.</span></span>|  
|<span data-ttu-id="dc430-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc430-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc430-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc430-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc430-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc430-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc430-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc430-120">E_FAIL</span></span>|<span data-ttu-id="dc430-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc430-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc430-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dc430-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dc430-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dc430-125">요청한에 대 한 참조 목록을 만드는 데 사용할 수 있는 메모리가 부족 `ICLRAssemblyReferenceList` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc430-126">설명</span><span class="sxs-lookup"><span data-stu-id="dc430-126">Remarks</span></span>  
 <span data-ttu-id="dc430-127">CLR은 다음 지침 집합을 사용 하 여 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="dc430-128">먼저에서 반환 하는 어셈블리 참조의 목록을 참조 합니다 `GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="dc430-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="dc430-129">어셈블리가 목록에 표시 되 면 CLR은이를 정상적으로 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="dc430-130">어셈블리가 목록에 표시 되지 않고 호스트에서 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)의 구현을 제공한 경우 CLR은 [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) 를 호출 하 여 호스트가 바인딩할 어셈블리를 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="dc430-131">그렇지 않으면 CLR이 어셈블리에 바인딩하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="dc430-132">호스트가 null로 설정 된 경우 `ppReferenceList` CLR은 먼저 전역 어셈블리 캐시를 검색 하 고를 호출한 `ProvideAssembly` 다음 응용 프로그램 기반을 검색 하 여 어셈블리 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc430-133">초기화 되 면 CLR은 `GetNonHostStoreAssemblies` 한 번만 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="dc430-134">메서드가 다시 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc430-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc430-135">Requirements</span></span>  
 <span data-ttu-id="dc430-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc430-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc430-137">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dc430-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc430-138">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc430-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc430-139">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc430-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc430-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc430-140">See also</span></span>

- [<span data-ttu-id="dc430-141">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc430-141">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="dc430-142">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc430-142">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="dc430-143">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc430-143">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
