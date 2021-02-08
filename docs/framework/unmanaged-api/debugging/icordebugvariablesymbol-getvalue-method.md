---
description: '자세히 알아보기: ICorDebugVariableSymbol:: GetValue 메서드'
title: ICorDebugVariableSymbol::GetValue 메서드
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: ccd7eae5cc4740e83d0210a903ba0e7778aa8896
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790570"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="5ef35-103">ICorDebugVariableSymbol::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="5ef35-103">ICorDebugVariableSymbol::GetValue Method</span></span>

<span data-ttu-id="5ef35-104">변수의 값을 바이트 배열로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-104">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef35-105">구문</span><span class="sxs-lookup"><span data-stu-id="5ef35-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ef35-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ef35-106">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="5ef35-107">[in] 값을 읽을 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-107">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="5ef35-108">이 매개 변수는 개체의 멤버 필드를 읽을 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-108">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="5ef35-109">[in] `context` 인수의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-109">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="5ef35-110">[in] 값을 읽는 데 사용되는 스레드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-110">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="5ef35-111">[in] `pValue` 버퍼의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="5ef35-112">[out] 실제로 `pValue` 버퍼에 기록되는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-112">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5ef35-113">[out] 변수의 값을 포함하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-113">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ef35-114">설명</span><span class="sxs-lookup"><span data-stu-id="5ef35-114">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ef35-115">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ef35-115">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef35-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ef35-116">Requirements</span></span>  

 <span data-ttu-id="5ef35-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ef35-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ef35-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ef35-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ef35-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ef35-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ef35-120">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ef35-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef35-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ef35-121">See also</span></span>

- [<span data-ttu-id="5ef35-122">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ef35-122">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="5ef35-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ef35-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
