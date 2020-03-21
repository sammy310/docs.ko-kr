---
title: ICorDebugILFrame4::GetLocalVariableEx 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: ee263e8c49cd6da7278bd2299557336629720d2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178773"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="55d3d-102">ICorDebugILFrame4::GetLocalVariableEx 메서드</span><span class="sxs-lookup"><span data-stu-id="55d3d-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="55d3d-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="55d3d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="55d3d-104">이 IL(중간 언어) 스택 프레임에 지정된 로컬 변수의 값을 가져오고 필요에 따라 프로파일러 ReJIT 계측에 추가된 변수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55d3d-105">구문</span><span class="sxs-lookup"><span data-stu-id="55d3d-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55d3d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55d3d-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="55d3d-107">【인】 프로파일러 ReJIT 계측에 추가된 변수가 프레임에 포함되는지 여부를 지정하는 [ILCodeKind](ilcodekind-enumeration.md) 열거 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="55d3d-108">[in] IL 스택 프레임의 로컬 변수 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="55d3d-109">【아웃】 검색된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55d3d-110">설명</span><span class="sxs-lookup"><span data-stu-id="55d3d-110">Remarks</span></span>  
 <span data-ttu-id="55d3d-111">이 메서드는 프로파일러 ReJIT 계측에 추가된 변수에 선택적으로 액세스한다는 점을 제외하면 [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) 메서드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-111">This method is similar to the [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="55d3d-112">값으로이 메서드를 `flags` `ILCODE_ORIGINAL_IL` 호출 하는 [것은 GetLocalVariable](icordebugilframe-getlocalvariable-method.md)를 호출 하는 것과 같습니다. 메서드가 추가 로컬 변수로 계측되면 해당 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="55d3d-113">`ILCODE_REJIT_IL`을 사용하는 경우 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="55d3d-114">IL이 계측되지 않는 경우 메서드는 `E_INVALIDARG`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="55d3d-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55d3d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55d3d-115">Requirements</span></span>  
 <span data-ttu-id="55d3d-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55d3d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55d3d-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55d3d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55d3d-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55d3d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55d3d-119">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55d3d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d3d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55d3d-120">See also</span></span>

- [<span data-ttu-id="55d3d-121">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55d3d-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="55d3d-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55d3d-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="55d3d-123">ReJIT: 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="55d3d-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
