---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: 341a86f4c1c8367f979e193a6284bf89f1b03ca0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178797"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="e054a-102">ICorDebugILFrame4::EnumerateLocalVariablesEx 메서드</span><span class="sxs-lookup"><span data-stu-id="e054a-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="e054a-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="e054a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e054a-104">프레임의 로컬 변수에 대한 열거자를 가져오고 필요에 따라 프로파일러 ReJIT 계측에 추가된 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e054a-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e054a-105">구문</span><span class="sxs-lookup"><span data-stu-id="e054a-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e054a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e054a-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="e054a-107">【인】 프로파일러 ReJIT 계측에 추가된 변수가 프레임에 포함되는지 여부를 지정하는 [ILCodeKind](ilcodekind-enumeration.md) 열거 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="e054a-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="e054a-108">【아웃】 이 프레임의 로컬 변수에 대한 열거자인 "ICorDebugValueEnum" 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e054a-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e054a-109">설명</span><span class="sxs-lookup"><span data-stu-id="e054a-109">Remarks</span></span>  
 <span data-ttu-id="e054a-110">이 메서드는 프로파일러 ReJIT 계측에 추가된 변수에 선택적으로 액세스한다는 점을 제외하면 [열거지역LocalVariables](icordebugilframe-enumeratelocalvariables-method.md) 메서드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="e054a-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="e054a-111">설정은 `flags` [ICorDebugILFrame::열거로컬 변수를 호출하는 것과](icordebugilframe-enumeratelocalvariables-method.md)같습니다. `ILCODE_ORIGINAL_IL`</span><span class="sxs-lookup"><span data-stu-id="e054a-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="e054a-112">`flags`을 `ILCODE_REJIT_IL`로 설정하면 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e054a-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="e054a-113">IL(중간 언어)이 계측되지 않는 경우 열거형은 비어 있으며 메서드는 `S_OK`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e054a-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="e054a-114">열거자는 실행 중인 메서드의 모든 로컬 변수를 포함하지 않을 수 있습니다. 이러한 변수 중 일부는 활성 상태가 아닐 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e054a-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e054a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e054a-115">Requirements</span></span>  
 <span data-ttu-id="e054a-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e054a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e054a-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e054a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e054a-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e054a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e054a-119">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e054a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e054a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e054a-120">See also</span></span>

- [<span data-ttu-id="e054a-121">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e054a-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="e054a-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e054a-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e054a-123">ReJIT: 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="e054a-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
