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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d61981d26d21ec1e5e24093817586ebf45b129e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162334"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="88196-102">ICorDebugILFrame4::GetCodeEx 메서드</span><span class="sxs-lookup"><span data-stu-id="88196-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="88196-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="88196-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="88196-104">이 스택 프레임에서 실행 중인 코드에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88196-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88196-105">구문</span><span class="sxs-lookup"><span data-stu-id="88196-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88196-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88196-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="88196-107">[in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) 프로파일러 ReJIT 요청에 의해 정의 된 중간 언어 (IL) 프레임에 포함 되는지 여부를 지정 하는 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="88196-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="88196-108">[out] 이 스택 프레임이 실행 되는 코드를 나타내는 "ICorDebugCode" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="88196-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88196-109">설명</span><span class="sxs-lookup"><span data-stu-id="88196-109">Remarks</span></span>  
 <span data-ttu-id="88196-110">이 메서드는 비슷합니다는 [icordebugframe:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) 메서드를 필요에 따라 프로파일러 ReJIT 요청에 의해 정의 된 코드를 액세스 한다는 점을 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88196-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="88196-111">이 메서드를 호출을 `flags` 변수의 `ILCODE_ORIGINAL_IL` 호출 하는 것과 같습니다 [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)메서드가 계측 되는 경우 해당 IL에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88196-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> `ILCODE_REJIT_IL` <span data-ttu-id="88196-112">디버거가 프로파일러 ReJIT 요청에 의해 정의 된 IL에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88196-112">allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="88196-113">IL이 계측 되지 않는, 하는 경우 `ppCode` 됩니다 **null**, 메서드가 반환 하 고 `S_OK`합니다.</span><span class="sxs-lookup"><span data-stu-id="88196-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88196-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88196-114">Requirements</span></span>  
 <span data-ttu-id="88196-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="88196-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88196-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88196-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88196-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88196-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="88196-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="88196-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88196-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="88196-119">See also</span></span>

- [<span data-ttu-id="88196-120">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88196-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="88196-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88196-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="88196-122">ReJIT: 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="88196-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
