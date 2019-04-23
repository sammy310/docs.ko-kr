---
title: IGCHost::SetGCStartupLimits 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 365261883f0b81884bb7cf70614628c05f9067c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221009"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="38f7d-102">IGCHost::SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="38f7d-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="38f7d-103">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="38f7d-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38f7d-104">로 시작 합니다 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], 세그먼트 크기를 설정할 수 있습니다 및 0 세대의 최대 크기 보다 큰 값 `DWORD` 사용 하 여를 [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="38f7d-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f7d-105">구문</span><span class="sxs-lookup"><span data-stu-id="38f7d-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38f7d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38f7d-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="38f7d-107">[in] 가비지 컬렉션 시스템에서 사용 하는 세그먼트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="38f7d-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="38f7d-108">[in] 0 세대에 대 한 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="38f7d-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38f7d-109">설명</span><span class="sxs-lookup"><span data-stu-id="38f7d-109">Remarks</span></span>  
 <span data-ttu-id="38f7d-110">`SetGCStartupLimits` 메서드를 한 번만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38f7d-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="38f7d-111">이러한 값은 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38f7d-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38f7d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38f7d-112">Requirements</span></span>  
 <span data-ttu-id="38f7d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="38f7d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38f7d-114">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="38f7d-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="38f7d-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="38f7d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38f7d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38f7d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f7d-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="38f7d-117">See also</span></span>

- [<span data-ttu-id="38f7d-118">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38f7d-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
