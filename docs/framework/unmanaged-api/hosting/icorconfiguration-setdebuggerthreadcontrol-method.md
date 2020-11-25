---
title: ICorConfiguration::SetDebuggerThreadControl 메서드
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 05df50d80c6b8962b3bdfe2708d5f9d30c58aaea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723924"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="7b229-102">ICorConfiguration::SetDebuggerThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="7b229-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>

<span data-ttu-id="7b229-103">디버깅 서비스에서 CLR (공용 언어 런타임) 스레드가 차단 되 고 차단 해제 될 때 호출 되는 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b229-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b229-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b229-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b229-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b229-105">Parameters</span></span>  

 `pDebuggerThreadControl`  
 <span data-ttu-id="7b229-106">진행 디버깅 서비스에의 한 스레드 차단 및 차단 해제에 대해 호스트에 알리는 [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b229-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b229-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b229-107">Requirements</span></span>  

 <span data-ttu-id="7b229-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b229-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b229-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7b229-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b229-110">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b229-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b229-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b229-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b229-112">참조</span><span class="sxs-lookup"><span data-stu-id="7b229-112">See also</span></span>

- [<span data-ttu-id="7b229-113">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b229-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
