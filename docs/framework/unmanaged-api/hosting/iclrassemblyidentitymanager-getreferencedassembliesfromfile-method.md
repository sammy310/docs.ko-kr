---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
ms.openlocfilehash: 3c4f673d88594e86004c6d51a4d58a0ac4642875
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615945"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="c0b56-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="c0b56-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="c0b56-103">지정 된 파일 경로에서 어셈블리가 참조 하는 어셈블리의 목록을 포함 하는 [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-103">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b56-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0b56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0b56-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0b56-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="c0b56-106">진행 평가할 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c0b56-107">진행 향후 확장성을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="c0b56-108">현재 버전의 CLR (공용 언어 런타임)에서 지 원하는 유일한 값은 CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT입니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="c0b56-109">진행 에서 제외 해야 하는 어셈블리를 나타내는 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 개체에 대 한 포인터입니다 `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="c0b56-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="c0b56-110">제한이 에서 나타내는 어셈블리를 제외 하 고에서 `ICLRReferenceAssemblyEnum` 어셈블리에 의해 참조 되는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체의 주소에 대 한 포인터입니다 `pwzFilePath` `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="c0b56-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0b56-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="c0b56-111">Return Value</span></span>  
  
|<span data-ttu-id="c0b56-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0b56-112">HRESULT</span></span>|<span data-ttu-id="c0b56-113">설명</span><span class="sxs-lookup"><span data-stu-id="c0b56-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0b56-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0b56-114">S_OK</span></span>|<span data-ttu-id="c0b56-115">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="c0b56-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c0b56-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c0b56-117">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c0b56-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c0b56-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c0b56-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-119">The call timed out.</span></span>|  
|<span data-ttu-id="c0b56-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c0b56-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c0b56-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c0b56-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c0b56-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c0b56-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c0b56-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c0b56-124">E_FAIL</span></span>|<span data-ttu-id="c0b56-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c0b56-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c0b56-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0b56-128">설명</span><span class="sxs-lookup"><span data-stu-id="c0b56-128">Remarks</span></span>  
 <span data-ttu-id="c0b56-129">호출자는 반환 된 목록에서 알려진 어셈블리 참조 집합을 제외 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="c0b56-130">이 집합은 매개 변수에 의해 정의 됩니다 `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="c0b56-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0b56-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0b56-131">Requirements</span></span>  
 <span data-ttu-id="c0b56-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0b56-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0b56-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c0b56-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0b56-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b56-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0b56-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0b56-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b56-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0b56-136">See also</span></span>

- [<span data-ttu-id="c0b56-137">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0b56-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c0b56-138">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0b56-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c0b56-139">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0b56-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
