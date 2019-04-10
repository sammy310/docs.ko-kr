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
ms.openlocfilehash: d193f9aa4d051baa73944545d28a455495aeda40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185772"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="f71fa-102">ICorDebugCode::CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="f71fa-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="f71fa-103">이 코드 세그먼트의 지정 된 오프셋 위치에서 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f71fa-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71fa-104">구문</span><span class="sxs-lookup"><span data-stu-id="f71fa-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f71fa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f71fa-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="f71fa-106">[in] 중단점을 만들려는 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="f71fa-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="f71fa-107">[out] 중단점을 나타내는 "ICorDebugFunctionBreakpoint" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f71fa-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f71fa-108">설명</span><span class="sxs-lookup"><span data-stu-id="f71fa-108">Remarks</span></span>  
 <span data-ttu-id="f71fa-109">중단점 활성화 되려면 프로세스 개체에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f71fa-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="f71fa-110">이 코드는 Microsoft intermediate language (MSIL) 코드 했으며 경우는-just-in-time (JIT)-네이티브 컴파일된 버전의 코드에서 중단점 JIT 컴파일 코드 에서도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71fa-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="f71fa-111">(마찬가지 코드가 있는 경우 JIT 컴파일된 나중.)</span><span class="sxs-lookup"><span data-stu-id="f71fa-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f71fa-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f71fa-112">Requirements</span></span>  
 <span data-ttu-id="f71fa-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f71fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f71fa-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f71fa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f71fa-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f71fa-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f71fa-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f71fa-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f71fa-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f71fa-117">See also</span></span>
