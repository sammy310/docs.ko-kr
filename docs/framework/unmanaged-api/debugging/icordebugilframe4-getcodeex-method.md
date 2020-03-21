---
title: ICorDebugILFrame4::GetCodeEx 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178787"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="96d3a-102">ICorDebugILFrame4::GetCodeEx 메서드</span><span class="sxs-lookup"><span data-stu-id="96d3a-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="96d3a-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="96d3a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="96d3a-104">이 스택 프레임에서 실행 중인 코드에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="96d3a-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d3a-105">구문</span><span class="sxs-lookup"><span data-stu-id="96d3a-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96d3a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96d3a-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="96d3a-107">【인】 프로파일러의 ReJIT 요청에 의해 정의된 중간 언어(IL)가 프레임에 포함되는지 여부를 지정하는 [ILCodeKind](ilcodekind-enumeration.md) 열거 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="96d3a-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="96d3a-108">【아웃】 이 스택 프레임이 실행되는 코드를 나타내는 "ICorDebugCode" 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96d3a-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96d3a-109">설명</span><span class="sxs-lookup"><span data-stu-id="96d3a-109">Remarks</span></span>  
 <span data-ttu-id="96d3a-110">이 메서드는 프로파일러의 ReJIT 요청에 의해 정의된 코드에 선택적으로 액세스한다는 점을 제외하면 [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) 메서드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="96d3a-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="96d3a-111">값으로이 메서드를 `flags` `ILCODE_ORIGINAL_IL` 호출 하는 [것은 GetCode를](icordebugframe-getcode-method.md)호출 하는 것과 같습니다. 메서드가 계측되면 IL에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96d3a-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="96d3a-112">`ILCODE_REJIT_IL`을 사용하는 경우 디버거가 프로파일러 ReJIT 요청에 의해 정의된 IL에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96d3a-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="96d3a-113">IL이 계측되지 `ppCode` 않은 경우 **null이며**메서드가 반환됩니다. `S_OK`</span><span class="sxs-lookup"><span data-stu-id="96d3a-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d3a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96d3a-114">Requirements</span></span>  
 <span data-ttu-id="96d3a-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96d3a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d3a-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96d3a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96d3a-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96d3a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96d3a-118">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d3a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d3a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96d3a-119">See also</span></span>

- [<span data-ttu-id="96d3a-120">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96d3a-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="96d3a-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96d3a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="96d3a-122">ReJIT: 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="96d3a-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
