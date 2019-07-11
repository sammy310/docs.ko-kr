---
title: IGCHost2::SetGCStartupLimitsEx 메서드
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e834042c5e00709fcb2198c1496a8a630841d069
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779536"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="ba623-102">IGCHost2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="ba623-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="ba623-103">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba623-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba623-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba623-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba623-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba623-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="ba623-106">[in] 가비지 컬렉션 시스템에서 사용 하는 세그먼트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ba623-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="ba623-107">[in] 0 세대에 대 한 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ba623-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba623-108">설명</span><span class="sxs-lookup"><span data-stu-id="ba623-108">Remarks</span></span>  
 <span data-ttu-id="ba623-109">값을 `SetGCStartupLimitsEx` 집합 호스트 시작 되기 전에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba623-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="ba623-110">이러한 값은 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba623-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba623-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba623-111">Requirements</span></span>  
 <span data-ttu-id="ba623-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba623-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba623-113">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="ba623-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ba623-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ba623-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba623-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba623-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba623-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba623-116">See also</span></span>

- [<span data-ttu-id="ba623-117">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba623-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
