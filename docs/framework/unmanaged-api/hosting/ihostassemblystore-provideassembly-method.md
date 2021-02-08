---
description: IHostAssemblyStore::P rovideAssembly 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: f8917cb28dd3898343a7b6ee08bd54096df8cfa7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789504"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="cdf04-103">IHostAssemblyStore::ProvideAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="cdf04-103">IHostAssemblyStore::ProvideAssembly Method</span></span>

<span data-ttu-id="cdf04-104">[IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md)에서 반환 된 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 에서 참조 하지 않는 어셈블리에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-104">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="cdf04-105">CLR (공용 언어 런타임)은 `ProvideAssembly` 목록에 표시 되지 않는 각 어셈블리에 대해를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-105">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdf04-106">구문</span><span class="sxs-lookup"><span data-stu-id="cdf04-106">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdf04-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdf04-107">Parameters</span></span>  

 `pBindInfo`  
 <span data-ttu-id="cdf04-108">진행 호스트에서 버전 관리 정책 유무를 비롯 하 여 특정 바인딩 특성을 확인 하는 데 사용 하는 [Assemblybindinfo](assemblybindinfo-structure.md) 인스턴스에 대 한 포인터와 바인딩할 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-108">[in] A pointer to an [AssemblyBindInfo](assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="cdf04-109">제한이 이의 요청 된 어셈블리에 대 한 고유 식별자에 대 한 포인터 `IStream` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-109">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="cdf04-110">제한이 플랫폼 호출이 없어도 요청 된 어셈블리의 증명 정보를 확인 하는 데 사용 되는 호스트 관련 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-110">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="cdf04-111">`pHostContext`<xref:System.Reflection.Assembly.HostContext%2A>관리 되는 클래스의 속성에 해당 <xref:System.Reflection.Assembly> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-111">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="cdf04-112">제한이 `IStream` 로드할 PE (이식 가능한 실행) 이미지를 포함 하는의 주소에 대 한 포인터 이거나, 어셈블리를 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-112">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="cdf04-113">제한이 `IStream` Pdb (프로그램 디버그) 정보를 포함 하는의 주소에 대 한 포인터 이거나 .pdb 파일을 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-113">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdf04-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="cdf04-114">Return Value</span></span>  
  
|<span data-ttu-id="cdf04-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cdf04-115">HRESULT</span></span>|<span data-ttu-id="cdf04-116">설명</span><span class="sxs-lookup"><span data-stu-id="cdf04-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cdf04-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="cdf04-117">S_OK</span></span>|<span data-ttu-id="cdf04-118">`ProvideAssembly` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-118">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="cdf04-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cdf04-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cdf04-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cdf04-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cdf04-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cdf04-122">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-122">The call timed out.</span></span>|  
|<span data-ttu-id="cdf04-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cdf04-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cdf04-124">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cdf04-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cdf04-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cdf04-126">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cdf04-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cdf04-127">E_FAIL</span></span>|<span data-ttu-id="cdf04-128">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cdf04-129">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cdf04-130">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cdf04-131">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="cdf04-131">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="cdf04-132">요청 된 어셈블리를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-132">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="cdf04-133">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="cdf04-133">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="cdf04-134">로 지정 된 버퍼 크기가 `pAssemblyId` 호스트에서 반환 하려는 식별자를 보유할 만큼 크지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="cdf04-134">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdf04-135">설명</span><span class="sxs-lookup"><span data-stu-id="cdf04-135">Remarks</span></span>  

 <span data-ttu-id="cdf04-136">에 대해 반환 된 id 값은 `pAssemblyId` 호스트에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-136">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="cdf04-137">식별자는 프로세스의 수명 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-137">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="cdf04-138">CLR은이 값을 스트림의 고유 식별자로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-138">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="cdf04-139">이 메서드는에 대 한 `pAssemblyId` 다른 호출에서 반환 된 값을 기준으로 각 값을 검사 `ProvideAssembly` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-139">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="cdf04-140">호스트에서 다른 값을 반환 하는 경우 `pAssemblyId` `IStream` CLR은 해당 스트림의 내용이 이미 매핑 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-140">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="cdf04-141">이 경우 런타임에서는 새 이미지를 매핑하는 대신 이미지의 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-141">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdf04-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdf04-142">Requirements</span></span>  

 <span data-ttu-id="cdf04-143">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdf04-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdf04-144">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cdf04-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cdf04-145">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdf04-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdf04-146">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdf04-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdf04-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdf04-147">See also</span></span>

- [<span data-ttu-id="cdf04-148">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdf04-148">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="cdf04-149">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdf04-149">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="cdf04-150">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdf04-150">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
