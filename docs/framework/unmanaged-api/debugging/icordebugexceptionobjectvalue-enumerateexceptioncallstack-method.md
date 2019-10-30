---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 9f54fdfe16bc24394503ba6f5a9b906a32ec2c8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091096"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="d3378-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="d3378-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="d3378-103">예외 개체에 포함 된 호출 스택에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3378-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3378-104">구문</span><span class="sxs-lookup"><span data-stu-id="d3378-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3378-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3378-105">Parameters</span></span>  
 <span data-ttu-id="d3378-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="d3378-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="d3378-107">제한이 관리 되는 예외 개체에 대 한 스택 추적 열거자 인 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3378-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3378-108">주의</span><span class="sxs-lookup"><span data-stu-id="d3378-108">Remarks</span></span>  
 <span data-ttu-id="d3378-109">호출 스택 정보를 사용할 수 없는 경우 메서드는 `S_OK`을 반환 하 고 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) 는 길이가 0 인 유효한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="d3378-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="d3378-110">메서드가 스택 추적 정보를 검색할 수 없는 경우 반환 값은 `E_FAIL` 되며 열거자는 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3378-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="d3378-111">[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) 개체는 예외 개체의 `_stackTrace` 필드에서 스택 추적 데이터를 디코딩하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3378-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3378-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3378-112">Requirements</span></span>  
 <span data-ttu-id="d3378-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3378-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3378-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3378-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3378-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3378-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3378-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3378-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3378-117">참조</span><span class="sxs-lookup"><span data-stu-id="d3378-117">See also</span></span>

- [<span data-ttu-id="d3378-118">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3378-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="d3378-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3378-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
