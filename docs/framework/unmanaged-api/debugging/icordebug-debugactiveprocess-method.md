---
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
ms.openlocfilehash: 2d71cebb77ed3ca586e857710667c0077f4f76ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793582"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="4d093-102">ICorDebug::DebugActiveProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="4d093-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="4d093-103">디버거를 기존 프로세스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d093-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d093-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d093-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d093-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d093-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="4d093-106">진행 디버거를 연결할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4d093-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="4d093-107">진행 디버거가 프로세스에 대 한 Win32 디버거로 동작 하 고 관리 되지 않는 콜백을 디스패치할 경우 `true`로 설정 되는 부울 값입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d093-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="4d093-108">제한이 디버거가 연결 된 프로세스를 나타내는 "ICorDebugProcess" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d093-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d093-109">주의</span><span class="sxs-lookup"><span data-stu-id="4d093-109">Remarks</span></span>  
 <span data-ttu-id="4d093-110">IA-64 기반 및 AMD64 기반 플랫폼과 같은 Win9x 및 비 x86 플랫폼에서는 Interop 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d093-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d093-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d093-111">Requirements</span></span>  
 <span data-ttu-id="4d093-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d093-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d093-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d093-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d093-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d093-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d093-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d093-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d093-116">참조</span><span class="sxs-lookup"><span data-stu-id="4d093-116">See also</span></span>

- [<span data-ttu-id="4d093-117">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d093-117">ICorDebug Interface</span></span>](icordebug-interface.md)
