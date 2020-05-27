---
title: IHostTask::Start 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: a4e8211f091b2a3a4f24d8350f6d7dbe7d7920af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842389"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="e1c6b-102">IHostTask::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="e1c6b-102">IHostTask::Start Method</span></span>
<span data-ttu-id="e1c6b-103">호스트가 현재 [IHostTask](ihosttask-interface.md) 인스턴스로 표시 된 작업을 일시 중단에서 라이브 상태로 이동 하 여 코드를 실행할 수 있도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c6b-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1c6b-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e1c6b-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="e1c6b-105">Return Value</span></span>  
  
|<span data-ttu-id="e1c6b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1c6b-106">HRESULT</span></span>|<span data-ttu-id="e1c6b-107">Description</span><span class="sxs-lookup"><span data-stu-id="e1c6b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1c6b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1c6b-108">S_OK</span></span>|<span data-ttu-id="e1c6b-109">시작이 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="e1c6b-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1c6b-110">E_FAIL</span></span>|<span data-ttu-id="e1c6b-111">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1c6b-112">메서드가 E_FAIL 반환 하는 경우 프로세스 내에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="e1c6b-113">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1c6b-114">설명</span><span class="sxs-lookup"><span data-stu-id="e1c6b-114">Remarks</span></span>  
 <span data-ttu-id="e1c6b-115">`Start`는 치명적인 오류가 발생 한 경우를 제외 하 고는 항상 S_OK HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1c6b-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1c6b-116">Requirements</span></span>  
 <span data-ttu-id="e1c6b-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1c6b-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1c6b-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1c6b-119">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1c6b-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1c6b-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c6b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c6b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1c6b-121">See also</span></span>

- [<span data-ttu-id="e1c6b-122">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1c6b-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e1c6b-123">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1c6b-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e1c6b-124">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1c6b-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e1c6b-125">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1c6b-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
