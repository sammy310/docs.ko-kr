---
description: '자세히 알아보기: IGCThreadControl:: SuspensionEnding 메서드'
title: IGCThreadControl::SuspensionEnding 메서드
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 5ff889f45ea3664312060f373907e65c367276f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709271"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="7731d-103">IGCThreadControl::SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="7731d-103">IGCThreadControl::SuspensionEnding Method</span></span>

<span data-ttu-id="7731d-104">가비지 수집 또는 다른 일시 중단 후 런타임이 스레드를 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7731d-104">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7731d-105">구문</span><span class="sxs-lookup"><span data-stu-id="7731d-105">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7731d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7731d-106">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="7731d-107">진행 가비지 수집이 수행 된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="7731d-107">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7731d-108">설명</span><span class="sxs-lookup"><span data-stu-id="7731d-108">Remarks</span></span>  

 <span data-ttu-id="7731d-109">콜백 중에는 스레드를 다시 예약 하지 마십시오 `SuspensionEnding` .</span><span class="sxs-lookup"><span data-stu-id="7731d-109">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7731d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7731d-110">Requirements</span></span>  

 <span data-ttu-id="7731d-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7731d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7731d-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7731d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7731d-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7731d-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7731d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7731d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7731d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7731d-115">See also</span></span>

- [<span data-ttu-id="7731d-116">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7731d-116">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
