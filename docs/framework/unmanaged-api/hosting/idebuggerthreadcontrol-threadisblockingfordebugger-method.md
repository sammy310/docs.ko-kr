---
description: '자세히 알아보기: IDebuggerThreadControl:: ThreadIsBlockingForDebugger 메서드'
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: 0fa96b2e36ea6653e1698dd32fa1e73d223afb94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789517"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="bd334-103">IDebuggerThreadControl::ThreadIsBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="bd334-103">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>

<span data-ttu-id="bd334-104">이 콜백을 보내는 스레드가 디버깅 서비스 내에서 차단 됨을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bd334-104">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd334-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd334-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="bd334-106">설명</span><span class="sxs-lookup"><span data-stu-id="bd334-106">Remarks</span></span>  

 <span data-ttu-id="bd334-107">`ThreadIsBlockingForDebugger`메서드는 항상 런타임 스레드에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd334-107">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="bd334-108">`ThreadIsBlockingForDebugger`메서드는 스레드를 차단 하는 동안 호스트에 다른 작업을 수행할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd334-108">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd334-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd334-109">Requirements</span></span>  

 <span data-ttu-id="bd334-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd334-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd334-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bd334-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd334-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd334-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd334-113">**.Net Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd334-113">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd334-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd334-114">See also</span></span>

- [<span data-ttu-id="bd334-115">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd334-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
