---
description: '자세히 알아보기: ICLRHostProtectionManager:: SetEagerSerializeGrantSets 메서드'
title: ICLRHostProtectionManager::SetEagerSerializeGrantSets 메서드
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
ms.openlocfilehash: 04eb00b1422523e8057c3a0fc27dfe7e49f98f08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789916"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="09eac-103">ICLRHostProtectionManager::SetEagerSerializeGrantSets 메서드</span><span class="sxs-lookup"><span data-stu-id="09eac-103">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>

<span data-ttu-id="09eac-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09eac-105">구문</span><span class="sxs-lookup"><span data-stu-id="09eac-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="09eac-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="09eac-106">Return Value</span></span>  
  
|<span data-ttu-id="09eac-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09eac-107">HRESULT</span></span>|<span data-ttu-id="09eac-108">설명</span><span class="sxs-lookup"><span data-stu-id="09eac-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09eac-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="09eac-109">S_OK</span></span>|<span data-ttu-id="09eac-110">`SetEagerSerializeGrantSets` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-110">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="09eac-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09eac-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09eac-112">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09eac-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09eac-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09eac-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-114">The call timed out.</span></span>|  
|<span data-ttu-id="09eac-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09eac-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09eac-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09eac-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09eac-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09eac-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09eac-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09eac-119">E_FAIL</span></span>|<span data-ttu-id="09eac-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09eac-121">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-121">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09eac-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09eac-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09eac-123">Requirements</span></span>  

 <span data-ttu-id="09eac-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09eac-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09eac-125">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="09eac-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09eac-126">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09eac-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09eac-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09eac-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09eac-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09eac-128">See also</span></span>

- [<span data-ttu-id="09eac-129">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eac-129">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="09eac-130">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eac-130">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
