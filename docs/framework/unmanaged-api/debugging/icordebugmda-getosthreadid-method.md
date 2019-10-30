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
ms.openlocfilehash: e9846234f8217b822860c2400a54a91a651a0a56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129823"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="5586b-102">ICorDebugMDA::GetOSThreadId 메서드</span><span class="sxs-lookup"><span data-stu-id="5586b-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="5586b-103">[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) 가 나타내는 MDA (관리 디버깅 도우미)가 실행 중인 os (운영 체제) 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5586b-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5586b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5586b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5586b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5586b-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="5586b-106">제한이 OS 스레드 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5586b-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5586b-107">주의</span><span class="sxs-lookup"><span data-stu-id="5586b-107">Remarks</span></span>  
 <span data-ttu-id="5586b-108">ICorDebugThread 대신 OS 스레드를 사용 하 여 네이티브 스레드나 관리 코드를 아직 입력 하지 않은 관리 되는 스레드에서 MDA가 발생 하는 상황을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5586b-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5586b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5586b-109">Requirements</span></span>  
 <span data-ttu-id="5586b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5586b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5586b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5586b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5586b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5586b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5586b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5586b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5586b-114">참조</span><span class="sxs-lookup"><span data-stu-id="5586b-114">See also</span></span>

- [<span data-ttu-id="5586b-115">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5586b-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="5586b-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="5586b-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
