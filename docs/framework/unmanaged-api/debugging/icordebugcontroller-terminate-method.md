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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65a374f942697ee670507987c4a97a7977970b69
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481095"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="6a951-102">ICorDebugController::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="6a951-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="6a951-103">지정된 된 종료 코드를 사용 하 여 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a951-104">이 메서드는 Win32에 대 한 래퍼 `TerminateProcess` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="6a951-105">따라서 `Terminate` 종료 코드를 사용 하 여 동일한 방식으로 Win32 `TerminateProcess` 함수 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a951-106">구문</span><span class="sxs-lookup"><span data-stu-id="6a951-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a951-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a951-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="6a951-108">[in] 종료 코드는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="6a951-109">유효한 숫자 값 Winbase.h에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a951-110">설명</span><span class="sxs-lookup"><span data-stu-id="6a951-110">Remarks</span></span>  
 <span data-ttu-id="6a951-111">프로세스를 중지 될 때 `Terminate` 는 호출 프로세스는 계속 사용 하 여는 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드 디버거를 통해 종료에 대 한 확인을 받을 수 있도록는 [ Icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 나 [icordebugmanagedcallback:: Exitappdomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a951-112">이 메서드는 응용 프로그램 도메인 별로 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="6a951-113">즉,에서 구현 되지 않습니다는 <xref:System.AppDomain> 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="6a951-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a951-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a951-114">Requirements</span></span>  
 <span data-ttu-id="6a951-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a951-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a951-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a951-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a951-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a951-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a951-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a951-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a951-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a951-119">See also</span></span>

