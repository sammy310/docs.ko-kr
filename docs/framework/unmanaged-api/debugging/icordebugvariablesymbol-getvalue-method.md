---
title: ICorDebugVariableSymbol::GetValue 메서드
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: f217f7226d53a27363f66eb90a340fd3604a0217
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396512"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="b068b-102">ICorDebugVariableSymbol::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="b068b-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="b068b-103">변수의 값을 바이트 배열로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b068b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b068b-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b068b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b068b-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="b068b-106">[in] 값을 읽을 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="b068b-107">이 매개 변수는 개체의 멤버 필드를 읽을 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="b068b-108">[in] `context` 인수의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="b068b-109">[in] 값을 읽는 데 사용되는 스레드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="b068b-110">[in] `pValue` 버퍼의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="b068b-111">[out] 실제로 `pValue` 버퍼에 기록되는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="b068b-112">[out] 변수의 값을 포함하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b068b-113">설명</span><span class="sxs-lookup"><span data-stu-id="b068b-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b068b-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b068b-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b068b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b068b-115">Requirements</span></span>  
 <span data-ttu-id="b068b-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b068b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b068b-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b068b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b068b-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b068b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b068b-119">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b068b-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b068b-120">참조</span><span class="sxs-lookup"><span data-stu-id="b068b-120">See also</span></span>

- [<span data-ttu-id="b068b-121">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b068b-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="b068b-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b068b-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
