---
title: ICorDebugController::Terminate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: eade3fd5d946c44ae4a77c571f762709de3cef40
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976566"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="d0875-102">ICorDebugController::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="d0875-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="d0875-103">지정 된 종료 코드를 사용 하 여 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0875-104">이 메서드는 Win32 `TerminateProcess` 함수에 대 한 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="d0875-105">따라서는 `Terminate` Win32 `TerminateProcess` 함수에서 사용 하는 것과 동일한 방식으로 종료 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0875-106">구문</span><span class="sxs-lookup"><span data-stu-id="d0875-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0875-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0875-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="d0875-108">진행 종료 코드 인 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="d0875-109">유효한 숫자 값은 Winbase. h에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0875-110">설명</span><span class="sxs-lookup"><span data-stu-id="d0875-110">Remarks</span></span>  
 <span data-ttu-id="d0875-111">가 호출 될 때 `Terminate` 프로세스가 중지 되 면 디버거가 [ICorDebugManagedCallback:: Exitprocess](icordebugmanagedcallback-exitprocess-method.md) 또는 [ICorDebugManagedCallback:: exitprocess](icordebugmanagedcallback-exitappdomain-method.md) 콜백을 통해 종료 확인을 받도록 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 메서드를 사용 하 여 프로세스를 계속 진행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0875-112">이 메서드는 응용 프로그램 도메인에서 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="d0875-113">즉, <xref:System.AppDomain> 수준에서 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0875-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0875-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0875-114">Requirements</span></span>  
 <span data-ttu-id="d0875-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0875-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0875-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0875-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0875-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0875-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0875-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0875-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0875-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0875-119">See also</span></span>
