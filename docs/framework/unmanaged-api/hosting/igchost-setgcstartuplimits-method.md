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
ms.openlocfilehash: 0eea9dba57886edfef13c31948a9cff94c6c1bfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687888"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="21d39-102">IGCHost::SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="21d39-102">IGCHost::SetGCStartupLimits Method</span></span>

<span data-ttu-id="21d39-103">0 세대의 세그먼트 크기와 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d39-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="21d39-104">.NET Framework 4.5 부터는 `DWORD` [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) 메서드를 사용 하 여 세그먼트 크기와 최대 0 세대 크기를 보다 큰 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d39-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d39-105">구문</span><span class="sxs-lookup"><span data-stu-id="21d39-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21d39-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21d39-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="21d39-107">진행 가비지 수집 시스템에서 사용 하는 세그먼트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="21d39-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="21d39-108">진행 0 세대의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="21d39-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21d39-109">설명</span><span class="sxs-lookup"><span data-stu-id="21d39-109">Remarks</span></span>  

 <span data-ttu-id="21d39-110">`SetGCStartupLimits`메서드는 한 번만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d39-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="21d39-111">이러한 값은 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21d39-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21d39-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21d39-112">Requirements</span></span>  

 <span data-ttu-id="21d39-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21d39-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21d39-114">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="21d39-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="21d39-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d39-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21d39-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21d39-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d39-117">참조</span><span class="sxs-lookup"><span data-stu-id="21d39-117">See also</span></span>

- [<span data-ttu-id="21d39-118">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21d39-118">IGCHost Interface</span></span>](igchost-interface.md)
