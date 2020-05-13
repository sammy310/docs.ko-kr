---
title: ICorDebugILCode::GetEHClauses 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: e1fd68cd079b381d941d416831133c54e49ac48a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210386"
---
# <a name="icordebugilcodegetehclauses-method"></a><span data-ttu-id="51d2e-102">ICorDebugILCode::GetEHClauses 메서드</span><span class="sxs-lookup"><span data-stu-id="51d2e-102">ICorDebugILCode::GetEHClauses Method</span></span>
<span data-ttu-id="51d2e-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="51d2e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="51d2e-104">이 IL(중간 언어)에 대해 정의된 EH(예외 처리) 절 목록에 대한 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="51d2e-104">Returns a pointer to a list of exception handling (EH) clauses that are defined for this intermediate language (IL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51d2e-105">구문</span><span class="sxs-lookup"><span data-stu-id="51d2e-105">Syntax</span></span>  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51d2e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51d2e-106">Parameters</span></span>  
 `cClauses`  
 <span data-ttu-id="51d2e-107">[in] `clauses` 배열의 스토리지 용량입니다.</span><span class="sxs-lookup"><span data-stu-id="51d2e-107">[in] The storage capacity of the `clauses` array.</span></span> <span data-ttu-id="51d2e-108">자세한 내용은 주의 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51d2e-108">See the Remarks section for more information.</span></span>  
  
 `pcClauses`  
 <span data-ttu-id="51d2e-109">[out] `clauses` 배열에 관련 정보가 기록되는 절의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="51d2e-109">[out] The number of clauses about which information is written to the `clauses` array.</span></span>  
  
 <span data-ttu-id="51d2e-110">절</span><span class="sxs-lookup"><span data-stu-id="51d2e-110">clauses</span></span>  
 <span data-ttu-id="51d2e-111">제한이 이 IL에 대해 정의 된 예외 처리 절에 대 한 정보를 포함 하는 [CorDebugEHClause](cordebugehclause-structure.md) 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="51d2e-111">[out] An array of [CorDebugEHClause](cordebugehclause-structure.md) objects that contain information on exception handling clauses defined for this IL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51d2e-112">설명</span><span class="sxs-lookup"><span data-stu-id="51d2e-112">Remarks</span></span>  
 <span data-ttu-id="51d2e-113">`cClauses`가 0이 고 `pcClauses` 가**null**이 아닌 경우 `pcClauses` 는 사용 가능한 예외 처리 절 수로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51d2e-113">If `cClauses` is 0 and `pcClauses` is non-**null**, `pcClauses` is set to the number of available exception handling clauses.</span></span> <span data-ttu-id="51d2e-114">`cClauses`은 값이 0이 아닌 경우 `clauses` 배열의 스토리지 용량을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51d2e-114">If `cClauses` is non-zero, it represents the storage capacity of the `clauses` array.</span></span> <span data-ttu-id="51d2e-115">메서드가 반환될 때 `clauses`는 `cClauses` 항목의 최대값을 포함하며 `pcClauses`는 `clauses` 배열에 실제로 기록된 절의 수로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51d2e-115">When the method returns, `clauses` contains a maximum of `cClauses` items, and `pcClauses` is set to the number of clauses actually written to the `clauses` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51d2e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51d2e-116">Requirements</span></span>  
 <span data-ttu-id="51d2e-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51d2e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51d2e-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51d2e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51d2e-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51d2e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51d2e-120">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51d2e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d2e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51d2e-121">See also</span></span>

- [<span data-ttu-id="51d2e-122">ICorDebugILCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51d2e-122">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="51d2e-123">CorDebugEHClause 구조</span><span class="sxs-lookup"><span data-stu-id="51d2e-123">CorDebugEHClause Structure</span></span>](cordebugehclause-structure.md)
- [<span data-ttu-id="51d2e-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51d2e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
