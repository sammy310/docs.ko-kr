---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
ms.openlocfilehash: f1e6a47c0838782ae0610d49ca7fce3eb8554458
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716709"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="34d59-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="34d59-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>

<span data-ttu-id="34d59-103">지정 된 스트림의 어셈블리에 대 한 정식 어셈블리 id 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d59-104">구문</span><span class="sxs-lookup"><span data-stu-id="34d59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34d59-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34d59-105">Parameters</span></span>  

 `pStream`  
 <span data-ttu-id="34d59-106">진행 평가할 어셈블리 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="34d59-107">진행 향후 확장성을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="34d59-108">현재 버전의 CLR (공용 언어 런타임)에서 지 원하는 유일한 값은 CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT입니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="34d59-109">제한이 불투명 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="34d59-110">[in, out] 의 크기 `pwzBuffer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34d59-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="34d59-111">Return Value</span></span>  
  
|<span data-ttu-id="34d59-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34d59-112">HRESULT</span></span>|<span data-ttu-id="34d59-113">설명</span><span class="sxs-lookup"><span data-stu-id="34d59-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34d59-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="34d59-114">S_OK</span></span>|<span data-ttu-id="34d59-115">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="34d59-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="34d59-116">E_INVALIDARG</span></span>|<span data-ttu-id="34d59-117">제공 된 `pStream` 가 null 인 경우</span><span class="sxs-lookup"><span data-stu-id="34d59-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="34d59-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="34d59-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="34d59-119">의 크기가 `pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="34d59-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34d59-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34d59-121">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34d59-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34d59-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34d59-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-123">The call timed out.</span></span>|  
|<span data-ttu-id="34d59-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34d59-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34d59-125">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34d59-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34d59-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34d59-127">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34d59-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34d59-128">E_FAIL</span></span>|<span data-ttu-id="34d59-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34d59-130">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34d59-131">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34d59-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34d59-132">Requirements</span></span>  

 <span data-ttu-id="34d59-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34d59-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34d59-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="34d59-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34d59-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d59-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34d59-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34d59-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d59-137">참조</span><span class="sxs-lookup"><span data-stu-id="34d59-137">See also</span></span>

- [<span data-ttu-id="34d59-138">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34d59-138">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="34d59-139">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34d59-139">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
