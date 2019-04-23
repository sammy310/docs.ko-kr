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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6594bb72ce9cd2fbfa9cdafebc152a90618b810
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193085"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="4d68a-102">ICorDebugILFrame4::GetLocalVariableEx 메서드</span><span class="sxs-lookup"><span data-stu-id="4d68a-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="4d68a-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="4d68a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4d68a-104">이 IL(중간 언어) 스택 프레임에 지정된 로컬 변수의 값을 가져오고 필요에 따라 프로파일러 ReJIT 계측에 추가된 변수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d68a-105">구문</span><span class="sxs-lookup"><span data-stu-id="4d68a-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d68a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d68a-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="4d68a-107">[in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) 프로파일러 ReJIT 계측에에서 추가 된 변수에 프레임에 포함 되는지 여부를 지정 하는 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="4d68a-108">[in] IL 스택 프레임의 로컬 변수 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4d68a-109">[out] 검색된 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d68a-110">설명</span><span class="sxs-lookup"><span data-stu-id="4d68a-110">Remarks</span></span>  
 <span data-ttu-id="4d68a-111">이 메서드는 비슷합니다는 [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) 메서드와 해당 it는 필요에 따라 프로파일러 ReJIT 계측에에서 추가 된 변수에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-111">This method is similar to the [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="4d68a-112">이 메서드를 호출을 `flags` 의 값 `ILCODE_ORIGINAL_IL` 호출 하는 것과 같습니다 [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)메서드가 추가 로컬 변수를 사용 하 여 계측 되는 경우 해당 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="4d68a-113">`ILCODE_REJIT_IL`을 사용하는 경우 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="4d68a-114">IL이 계측되지 않는 경우 메서드는 `E_INVALIDARG`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4d68a-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d68a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d68a-115">Requirements</span></span>  
 <span data-ttu-id="4d68a-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d68a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d68a-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d68a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d68a-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d68a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d68a-119">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d68a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d68a-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="4d68a-120">See also</span></span>

- [<span data-ttu-id="4d68a-121">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d68a-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="4d68a-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d68a-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4d68a-123">ReJIT: 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="4d68a-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
