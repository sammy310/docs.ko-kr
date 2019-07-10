---
title: ICorDebugCode::CreateBreakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f8be1a1831bc00eea3cfb659b46b67b6a78711
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747727"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="b6f48-102">ICorDebugCode::CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="b6f48-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="b6f48-103">이 코드 세그먼트의 지정 된 오프셋 위치에서 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6f48-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6f48-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6f48-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6f48-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6f48-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="b6f48-106">[in] 중단점을 만들려는 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f48-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="b6f48-107">[out] 중단점을 나타내는 "ICorDebugFunctionBreakpoint" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f48-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6f48-108">설명</span><span class="sxs-lookup"><span data-stu-id="b6f48-108">Remarks</span></span>  
 <span data-ttu-id="b6f48-109">중단점 활성화 되려면 프로세스 개체에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f48-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="b6f48-110">이 코드는 Microsoft intermediate language (MSIL) 코드 했으며 경우는-just-in-time (JIT)-네이티브 컴파일된 버전의 코드에서 중단점 JIT 컴파일 코드 에서도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f48-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="b6f48-111">(마찬가지 코드가 있는 경우 JIT 컴파일된 나중.)</span><span class="sxs-lookup"><span data-stu-id="b6f48-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6f48-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6f48-112">Requirements</span></span>  
 <span data-ttu-id="b6f48-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6f48-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6f48-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6f48-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6f48-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6f48-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6f48-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6f48-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6f48-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6f48-117">See also</span></span>
