---
title: IGCThreadControl::SuspensionStarting 메서드
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 9d39ee79f7734f7dd099a07640ecb06f4f8dcbb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721662"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="a55bd-102">IGCThreadControl::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="a55bd-102">IGCThreadControl::SuspensionStarting Method</span></span>

<span data-ttu-id="a55bd-103">런타임에서 가비지 수집 또는 기타 일시 중단에 대 한 스레드 일시 중단을 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a55bd-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a55bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="a55bd-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="a55bd-105">설명</span><span class="sxs-lookup"><span data-stu-id="a55bd-105">Remarks</span></span>  

 <span data-ttu-id="a55bd-106">콜백 중에는 스레드를 다시 예약 하지 마십시오 `SuspensionStarting` .</span><span class="sxs-lookup"><span data-stu-id="a55bd-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a55bd-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a55bd-107">Requirements</span></span>  

 <span data-ttu-id="a55bd-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a55bd-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a55bd-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a55bd-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a55bd-110">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a55bd-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a55bd-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a55bd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55bd-112">참조</span><span class="sxs-lookup"><span data-stu-id="a55bd-112">See also</span></span>

- [<span data-ttu-id="a55bd-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a55bd-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
