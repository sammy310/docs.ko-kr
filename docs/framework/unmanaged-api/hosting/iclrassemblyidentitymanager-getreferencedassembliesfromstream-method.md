---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
ms.openlocfilehash: a5e71d6ca90c8d0aa489176eb5a90bfe6896b1cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679324"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="40baa-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="40baa-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>

<span data-ttu-id="40baa-103">지정 된 스트림의 어셈블리에서 참조 하는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40baa-104">구문</span><span class="sxs-lookup"><span data-stu-id="40baa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40baa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40baa-105">Parameters</span></span>  

 `pStream`  
 <span data-ttu-id="40baa-106">진행 평가할 어셈블리를 포함 하는에 대 한 인터페이스 포인터 `IStream` 입니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="40baa-107">진행 향후 확장성을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="40baa-108">현재 버전의 CLR (공용 언어 런타임)에서 지 원하는 유일한 값은 CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT입니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="40baa-109">진행 제외할 어셈블리의 어셈블리 id 데이터를 포함 하는 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 개체에 대 한 포인터입니다 `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="40baa-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="40baa-110">제한이 에서 어셈블리를 제외 하 고 어셈블리에서 참조 하는 어셈블리의 `ICLRReferenceAssemblyEnum` 어셈블리 id 데이터를 포함 하는 개체의 주소에 대 한 포인터입니다 `pStream` `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="40baa-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40baa-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="40baa-111">Return Value</span></span>  
  
|<span data-ttu-id="40baa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40baa-112">HRESULT</span></span>|<span data-ttu-id="40baa-113">설명</span><span class="sxs-lookup"><span data-stu-id="40baa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40baa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="40baa-114">S_OK</span></span>|<span data-ttu-id="40baa-115">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="40baa-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40baa-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40baa-117">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40baa-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40baa-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40baa-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-119">The call timed out.</span></span>|  
|<span data-ttu-id="40baa-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40baa-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40baa-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40baa-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40baa-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40baa-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40baa-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40baa-124">E_FAIL</span></span>|<span data-ttu-id="40baa-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40baa-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40baa-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40baa-128">설명</span><span class="sxs-lookup"><span data-stu-id="40baa-128">Remarks</span></span>  

 <span data-ttu-id="40baa-129">호출자는 반환 된 목록에서 알려진 어셈블리 참조 집합을 제외 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="40baa-130">이 집합은에 의해 정의 됩니다 `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="40baa-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40baa-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40baa-131">Requirements</span></span>  

 <span data-ttu-id="40baa-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40baa-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40baa-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="40baa-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40baa-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40baa-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40baa-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40baa-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40baa-136">참조</span><span class="sxs-lookup"><span data-stu-id="40baa-136">See also</span></span>

- [<span data-ttu-id="40baa-137">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40baa-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="40baa-138">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40baa-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="40baa-139">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40baa-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
