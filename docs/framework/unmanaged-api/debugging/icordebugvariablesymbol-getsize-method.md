---
title: ICorDebugVariableSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 1079351e75ec9c48a9657f514ee56e2e6a4b0920
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731373"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="d8f6b-102">ICorDebugVariableSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="d8f6b-102">ICorDebugVariableSymbol::GetSize Method</span></span>

<span data-ttu-id="d8f6b-103">변수의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6b-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f6b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8f6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8f6b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8f6b-105">Parameters</span></span>  

 `pcbValue`  
 <span data-ttu-id="d8f6b-106">변수의 크기를 포함하는 32비트 부호 없는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6b-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8f6b-107">설명</span><span class="sxs-lookup"><span data-stu-id="d8f6b-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8f6b-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f6b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8f6b-109">Requirements</span></span>  

 <span data-ttu-id="d8f6b-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f6b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f6b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8f6b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8f6b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8f6b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8f6b-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f6b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f6b-114">참조</span><span class="sxs-lookup"><span data-stu-id="d8f6b-114">See also</span></span>

- [<span data-ttu-id="d8f6b-115">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8f6b-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="d8f6b-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8f6b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
