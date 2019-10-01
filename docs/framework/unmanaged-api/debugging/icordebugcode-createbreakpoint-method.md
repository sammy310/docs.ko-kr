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
ms.openlocfilehash: 1ec7d615b99ac301948d7ea25318115713ce06ea
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700850"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="84798-102">ICorDebugCode::CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="84798-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="84798-103">이 코드 세그먼트에서 지정 된 오프셋에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84798-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84798-104">구문</span><span class="sxs-lookup"><span data-stu-id="84798-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84798-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84798-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="84798-106">진행 중단점을 만들 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="84798-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="84798-107">제한이 중단점을 나타내는 "ICorDebugFunctionBreakpoint" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="84798-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84798-108">설명</span><span class="sxs-lookup"><span data-stu-id="84798-108">Remarks</span></span>  
 <span data-ttu-id="84798-109">중단점이 활성화 되기 전에 프로세스 개체에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84798-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="84798-110">이 코드가 MSIL (Microsoft 중간 언어) 코드이 고 JIT (just-in-time) 컴파일된 네이티브 버전의 코드가 있는 경우, 중단점이 JIT 컴파일된 코드에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84798-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="84798-111">코드는 나중에 JIT로 컴파일되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="84798-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84798-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84798-112">Requirements</span></span>  
 <span data-ttu-id="84798-113">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="84798-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84798-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84798-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84798-115">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84798-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84798-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84798-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
