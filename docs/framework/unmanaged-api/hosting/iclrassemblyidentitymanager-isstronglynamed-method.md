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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1c1b2d8274baf5fd43991979bc65cd2c2299b46
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484695"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="b3125-102">ICLRAssemblyIdentityManager::IsStronglyNamed 메서드</span><span class="sxs-lookup"><span data-stu-id="b3125-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="b3125-103">지정된 된 어셈블리에 강력한 이름을 지정 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3125-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3125-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3125-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3125-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="b3125-106">[in] 불투명 정식 어셈블리 identity 데이터 계산할 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="b3125-107">[out] `true`어셈블리에서 참조 하는 경우는 `pwzAssemblyIdentity` 강력한 고, 그렇지 않으면 명명 된 매개 변수는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3125-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3125-108">Return Value</span></span>  
  
|<span data-ttu-id="b3125-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3125-109">HRESULT</span></span>|<span data-ttu-id="b3125-110">설명</span><span class="sxs-lookup"><span data-stu-id="b3125-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3125-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3125-111">S_OK</span></span>|<span data-ttu-id="b3125-112">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="b3125-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3125-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3125-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3125-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3125-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3125-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-116">The call timed out.</span></span>|  
|<span data-ttu-id="b3125-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3125-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3125-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3125-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3125-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3125-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3125-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3125-121">E_FAIL</span></span>|<span data-ttu-id="b3125-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3125-123">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3125-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3125-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3125-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3125-125">Requirements</span></span>  
 <span data-ttu-id="b3125-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3125-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3125-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3125-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3125-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b3125-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3125-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3125-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3125-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3125-130">See also</span></span>
- [<span data-ttu-id="b3125-131">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3125-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
