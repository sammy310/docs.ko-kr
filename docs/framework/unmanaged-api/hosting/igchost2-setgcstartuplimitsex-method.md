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
ms.openlocfilehash: da5e90055a08227ea7cb7fa1b459fe6f5f3a81fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127337"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="1acbb-102">IGCHost2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="1acbb-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="1acbb-103">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1acbb-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1acbb-104">구문</span><span class="sxs-lookup"><span data-stu-id="1acbb-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1acbb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1acbb-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="1acbb-106">[in] 가비지 컬렉션 시스템에서 사용 하는 세그먼트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1acbb-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="1acbb-107">[in] 0 세대에 대 한 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1acbb-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1acbb-108">설명</span><span class="sxs-lookup"><span data-stu-id="1acbb-108">Remarks</span></span>  
 <span data-ttu-id="1acbb-109">값을 `SetGCStartupLimitsEx` 집합 호스트 시작 되기 전에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1acbb-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="1acbb-110">이러한 값은 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1acbb-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1acbb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1acbb-111">Requirements</span></span>  
 <span data-ttu-id="1acbb-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1acbb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1acbb-113">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="1acbb-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="1acbb-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1acbb-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1acbb-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1acbb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1acbb-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="1acbb-116">See also</span></span>

- [<span data-ttu-id="1acbb-117">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1acbb-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
