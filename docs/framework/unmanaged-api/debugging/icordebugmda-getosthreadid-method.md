---
title: ICorDebugMDA::GetOSThreadId 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: 80248bba6d11b8af07aa0517cb41c8a4f783b5e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710898"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="bd860-102">ICorDebugMDA::GetOSThreadId 메서드</span><span class="sxs-lookup"><span data-stu-id="bd860-102">ICorDebugMDA::GetOSThreadId Method</span></span>

<span data-ttu-id="bd860-103">[ICorDebugMDA](icordebugmda-interface.md) 가 나타내는 MDA (관리 디버깅 도우미)가 실행 중인 os (운영 체제) 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd860-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd860-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd860-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd860-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd860-105">Parameters</span></span>  

 `pOsTid`  
 <span data-ttu-id="bd860-106">제한이 OS 스레드 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd860-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd860-107">설명</span><span class="sxs-lookup"><span data-stu-id="bd860-107">Remarks</span></span>  

 <span data-ttu-id="bd860-108">ICorDebugThread 대신 OS 스레드를 사용 하 여 네이티브 스레드나 관리 코드를 아직 입력 하지 않은 관리 되는 스레드에서 MDA가 발생 하는 상황을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd860-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd860-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd860-109">Requirements</span></span>  

 <span data-ttu-id="bd860-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd860-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd860-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd860-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd860-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd860-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd860-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd860-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd860-114">참조</span><span class="sxs-lookup"><span data-stu-id="bd860-114">See also</span></span>

- [<span data-ttu-id="bd860-115">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd860-115">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="bd860-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="bd860-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
