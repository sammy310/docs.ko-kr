---
description: ICorDebug::D ebugActiveProcess 메서드에 대해 자세히 알아보세요.
title: ICorDebug::DebugActiveProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 9c3a212adf962f96fd2c7345fe8b580b6af3b544
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801321"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="f3e8e-103">ICorDebug::DebugActiveProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="f3e8e-103">ICorDebug::DebugActiveProcess Method</span></span>

<span data-ttu-id="f3e8e-104">디버거를 기존 프로세스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e8e-104">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3e8e-105">구문</span><span class="sxs-lookup"><span data-stu-id="f3e8e-105">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3e8e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3e8e-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="f3e8e-107">진행 디버거를 연결할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e8e-107">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="f3e8e-108">진행 `true` 디버거가 프로세스에 대 한 Win32 디버거로 동작 하 고 관리 되지 않는 콜백을 디스패치할 경우로 설정 된 부울 값이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e8e-108">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="f3e8e-109">제한이 디버거가 연결 된 프로세스를 나타내는 "ICorDebugProcess" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e8e-109">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3e8e-110">설명</span><span class="sxs-lookup"><span data-stu-id="f3e8e-110">Remarks</span></span>  

 <span data-ttu-id="f3e8e-111">IA-64 기반 및 AMD64 기반 플랫폼과 같은 Win9x 및 비 x86 플랫폼에서는 Interop 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e8e-111">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3e8e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3e8e-112">Requirements</span></span>  

 <span data-ttu-id="f3e8e-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e8e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3e8e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3e8e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3e8e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3e8e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3e8e-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3e8e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e8e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3e8e-117">See also</span></span>

- [<span data-ttu-id="f3e8e-118">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3e8e-118">ICorDebug Interface</span></span>](icordebug-interface.md)
