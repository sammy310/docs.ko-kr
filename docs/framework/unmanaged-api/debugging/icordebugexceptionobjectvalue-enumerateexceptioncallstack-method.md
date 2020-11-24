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
ms.openlocfilehash: 101151469e2eece20afe289c9d95387ce6dc7c6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672125"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="642d9-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="642d9-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>

<span data-ttu-id="642d9-103">예외 개체에 포함 된 호출 스택에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="642d9-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="642d9-104">구문</span><span class="sxs-lookup"><span data-stu-id="642d9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="642d9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="642d9-105">Parameters</span></span>  

 <span data-ttu-id="642d9-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="642d9-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="642d9-107">제한이 관리 되는 예외 개체에 대 한 스택 추적 열거자 인 [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="642d9-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="642d9-108">설명</span><span class="sxs-lookup"><span data-stu-id="642d9-108">Remarks</span></span>  

 <span data-ttu-id="642d9-109">호출 스택 정보를 사용할 수 없는 경우 메서드는을 반환 하 `S_OK` 고 [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) 는 길이가 0 인 유효한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="642d9-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="642d9-110">메서드가 스택 추적 정보를 검색할 수 없는 경우 반환 값은이 `E_FAIL` 고 열거자가 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="642d9-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="642d9-111">[ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) 개체는 `_stackTrace` exception 개체의 필드에서 스택 추적 데이터를 디코딩하는 역할을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="642d9-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="642d9-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="642d9-112">Requirements</span></span>  

 <span data-ttu-id="642d9-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="642d9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="642d9-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="642d9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="642d9-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="642d9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="642d9-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="642d9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642d9-117">참조</span><span class="sxs-lookup"><span data-stu-id="642d9-117">See also</span></span>

- [<span data-ttu-id="642d9-118">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="642d9-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="642d9-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="642d9-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
