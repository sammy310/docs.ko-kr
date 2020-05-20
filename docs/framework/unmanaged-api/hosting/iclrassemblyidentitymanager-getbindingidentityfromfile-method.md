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
ms.openlocfilehash: 5b537d59014afa783d3f8c5046cc02dad7ea7740
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615997"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="11c62-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="11c62-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="11c62-103">지정 된 파일 경로에서 어셈블리의 어셈블리 id 바인딩 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c62-104">구문</span><span class="sxs-lookup"><span data-stu-id="11c62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11c62-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11c62-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="11c62-106">진행 평가할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="11c62-107">진행 어셈블리의 id 유형을 나타내는 [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-107">[in] A value of the [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="11c62-108">향후 확장성을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-108">Provided for future extensibility.</span></span> <span data-ttu-id="11c62-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 CLR (공용 언어 런타임) 버전 2.0에서 지 원하는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="11c62-110">제한이 불투명 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="11c62-111">[in, out] 의 크기에 대 한 포인터입니다 `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="11c62-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11c62-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="11c62-112">Return Value</span></span>  
  
|<span data-ttu-id="11c62-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11c62-113">HRESULT</span></span>|<span data-ttu-id="11c62-114">설명</span><span class="sxs-lookup"><span data-stu-id="11c62-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11c62-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="11c62-115">S_OK</span></span>|<span data-ttu-id="11c62-116">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="11c62-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="11c62-117">E_INVALIDARG</span></span>|<span data-ttu-id="11c62-118">제공 된 `pwzFilePath` 가 null 인 경우</span><span class="sxs-lookup"><span data-stu-id="11c62-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="11c62-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="11c62-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="11c62-120">의 크기가 `pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="11c62-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11c62-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11c62-122">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11c62-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11c62-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11c62-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-124">The call timed out.</span></span>|  
|<span data-ttu-id="11c62-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11c62-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11c62-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11c62-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11c62-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11c62-128">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11c62-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11c62-129">E_FAIL</span></span>|<span data-ttu-id="11c62-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11c62-131">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11c62-132">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11c62-133">설명</span><span class="sxs-lookup"><span data-stu-id="11c62-133">Remarks</span></span>  
 <span data-ttu-id="11c62-134">`GetBindingIdentityFromFile`는 일반적으로 두 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="11c62-135">첫 번째 호출은에 null 값을 제공 `pwzBuffer` 하 고, 메서드는에서 적절 한 크기를 반환 합니다 `pcchBufferSize` .</span><span class="sxs-lookup"><span data-stu-id="11c62-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="11c62-136">두 번째 호출은 적절 하 게 할당 된 버퍼를 제공 하 고, 메서드는 완료 시 실제 버퍼 데이터와 함께를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c62-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11c62-137">Requirements</span></span>  
 <span data-ttu-id="11c62-138">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11c62-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c62-139">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="11c62-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11c62-140">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11c62-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11c62-141">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11c62-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c62-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11c62-142">See also</span></span>

- [<span data-ttu-id="11c62-143">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11c62-143">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="11c62-144">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11c62-144">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="11c62-145">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11c62-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
