---
description: '자세히 알아보기: ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile 메서드'
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
ms.openlocfilehash: 82e72155b38f71fe2c024994f07178638095be9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689550"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="e2254-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e2254-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>

<span data-ttu-id="e2254-104">지정 된 파일 경로에서 어셈블리의 어셈블리 id 바인딩 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-104">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2254-105">구문</span><span class="sxs-lookup"><span data-stu-id="e2254-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2254-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2254-106">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="e2254-107">진행 평가할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-107">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e2254-108">진행 어셈블리의 id 유형을 나타내는 [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-108">[in] A value of the [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="e2254-109">향후 확장성을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-109">Provided for future extensibility.</span></span> <span data-ttu-id="e2254-110">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 CLR (공용 언어 런타임) 버전 2.0에서 지 원하는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-110">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="e2254-111">제한이 불투명 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-111">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="e2254-112">[in, out] 의 크기에 대 한 포인터입니다 `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="e2254-112">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2254-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="e2254-113">Return Value</span></span>  
  
|<span data-ttu-id="e2254-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2254-114">HRESULT</span></span>|<span data-ttu-id="e2254-115">설명</span><span class="sxs-lookup"><span data-stu-id="e2254-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2254-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2254-116">S_OK</span></span>|<span data-ttu-id="e2254-117">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-117">The method returned successfully.</span></span>|  
|<span data-ttu-id="e2254-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e2254-118">E_INVALIDARG</span></span>|<span data-ttu-id="e2254-119">제공 된 `pwzFilePath` 가 null 인 경우</span><span class="sxs-lookup"><span data-stu-id="e2254-119">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="e2254-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e2254-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e2254-121">의 크기가 `pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-121">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="e2254-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2254-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2254-123">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-123">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e2254-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e2254-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e2254-125">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-125">The call timed out.</span></span>|  
|<span data-ttu-id="e2254-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e2254-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e2254-127">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e2254-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e2254-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e2254-129">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e2254-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2254-130">E_FAIL</span></span>|<span data-ttu-id="e2254-131">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e2254-132">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-132">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e2254-133">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2254-134">설명</span><span class="sxs-lookup"><span data-stu-id="e2254-134">Remarks</span></span>  

 <span data-ttu-id="e2254-135">`GetBindingIdentityFromFile` 는 일반적으로 두 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-135">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="e2254-136">첫 번째 호출은에 null 값을 제공 `pwzBuffer` 하 고, 메서드는에서 적절 한 크기를 반환 합니다 `pcchBufferSize` .</span><span class="sxs-lookup"><span data-stu-id="e2254-136">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="e2254-137">두 번째 호출은 적절 하 게 할당 된 버퍼를 제공 하 고, 메서드는 완료 시 실제 버퍼 데이터와 함께를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-137">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2254-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2254-138">Requirements</span></span>  

 <span data-ttu-id="e2254-139">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2254-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2254-140">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e2254-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2254-141">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2254-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2254-142">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2254-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2254-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2254-143">See also</span></span>

- [<span data-ttu-id="e2254-144">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2254-144">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e2254-145">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2254-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e2254-146">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2254-146">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
