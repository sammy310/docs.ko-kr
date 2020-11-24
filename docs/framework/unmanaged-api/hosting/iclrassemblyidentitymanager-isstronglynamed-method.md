---
title: ICLRAssemblyIdentityManager::IsStronglyNamed 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
ms.openlocfilehash: 9ac3b2ae349a696ba0cea1bad3e3484bb1c113fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679249"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="6d24e-102">ICLRAssemblyIdentityManager::IsStronglyNamed 메서드</span><span class="sxs-lookup"><span data-stu-id="6d24e-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>

<span data-ttu-id="6d24e-103">지정 된 어셈블리에 강력한 이름이 지정 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d24e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d24e-104">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d24e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d24e-105">Parameters</span></span>  

 `pwzAssemblyIdentity`  
 <span data-ttu-id="6d24e-106">진행 평가할 어셈블리의 불투명 정식 어셈블리 id 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="6d24e-107">[out] `true` 매개 변수에서 참조 하는 어셈블리의 `pwzAssemblyIdentity` 이름이 강력한 이름이 면이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d24e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6d24e-108">Return Value</span></span>  
  
|<span data-ttu-id="6d24e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d24e-109">HRESULT</span></span>|<span data-ttu-id="6d24e-110">설명</span><span class="sxs-lookup"><span data-stu-id="6d24e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d24e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d24e-111">S_OK</span></span>|<span data-ttu-id="6d24e-112">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="6d24e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d24e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d24e-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d24e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d24e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d24e-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-116">The call timed out.</span></span>|  
|<span data-ttu-id="6d24e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d24e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d24e-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d24e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d24e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d24e-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d24e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d24e-121">E_FAIL</span></span>|<span data-ttu-id="6d24e-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d24e-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d24e-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d24e-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d24e-125">Requirements</span></span>  

 <span data-ttu-id="6d24e-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d24e-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d24e-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6d24e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d24e-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d24e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d24e-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d24e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d24e-130">참조</span><span class="sxs-lookup"><span data-stu-id="6d24e-130">See also</span></span>

- [<span data-ttu-id="6d24e-131">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d24e-131">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
