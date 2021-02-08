---
description: '자세히 알아보기: ICorDebugILFrame4:: EnumerateLocalVariablesEx 메서드'
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
ms.openlocfilehash: 8808b1ac337304ab37a35f7733b317dad274d48e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791246"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="aa5e1-103">ICorDebugILFrame4::EnumerateLocalVariablesEx 메서드</span><span class="sxs-lookup"><span data-stu-id="aa5e1-103">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>

<span data-ttu-id="aa5e1-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="aa5e1-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="aa5e1-105">프레임의 로컬 변수에 대한 열거자를 가져오고 필요에 따라 프로파일러 ReJIT 계측에 추가된 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-105">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa5e1-106">구문</span><span class="sxs-lookup"><span data-stu-id="aa5e1-106">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa5e1-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa5e1-107">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="aa5e1-108">진행 프로파일러 ReJIT 계측에 추가 된 변수가 프레임에 포함 되는지 여부를 지정 하는 [Ilcodekind](ilcodekind-enumeration.md) 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-108">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="aa5e1-109">제한이 이 프레임에 있는 지역 변수의 열거자 인 "ICorDebugValueEnum" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-109">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa5e1-110">설명</span><span class="sxs-lookup"><span data-stu-id="aa5e1-110">Remarks</span></span>  

 <span data-ttu-id="aa5e1-111">이 메서드는 선택적으로 profiler ReJIT 계측에 추가 된 변수에 액세스 한다는 점을 제외 하 고 [Enumeratelocalvariables](icordebugilframe-enumeratelocalvariables-method.md) 메서드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-111">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="aa5e1-112">로 설정 하 `flags` `ILCODE_ORIGINAL_IL` 는 것은 [ICorDebugILFrame:: EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)를 호출 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-112">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="aa5e1-113">`flags`을 `ILCODE_REJIT_IL`로 설정하면 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-113">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="aa5e1-114">IL(중간 언어)이 계측되지 않는 경우 열거형은 비어 있으며 메서드는 `S_OK`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-114">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="aa5e1-115">열거자는 실행 중인 메서드의 모든 로컬 변수를 포함하지 않을 수 있습니다. 이러한 변수 중 일부는 활성 상태가 아닐 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-115">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa5e1-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa5e1-116">Requirements</span></span>  

 <span data-ttu-id="aa5e1-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa5e1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa5e1-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa5e1-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa5e1-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa5e1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa5e1-120">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa5e1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa5e1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa5e1-121">See also</span></span>

- [<span data-ttu-id="aa5e1-122">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa5e1-122">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="aa5e1-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa5e1-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="aa5e1-124">ReJIT: How-To 가이드</span><span class="sxs-lookup"><span data-stu-id="aa5e1-124">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
