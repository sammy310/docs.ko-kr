---
title: ICorDebugStaticFieldSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: e36c94bf411e75f915cca86aee74cdf161674d25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379407"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="b04e7-102">ICorDebugStaticFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b04e7-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="b04e7-103">정적 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b04e7-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="b04e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b04e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b04e7-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="b04e7-106">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b04e7-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b04e7-107">설명</span><span class="sxs-lookup"><span data-stu-id="b04e7-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b04e7-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04e7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b04e7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b04e7-109">Requirements</span></span>  
 <span data-ttu-id="b04e7-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b04e7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b04e7-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b04e7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b04e7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b04e7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b04e7-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b04e7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04e7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b04e7-114">See also</span></span>

- [<span data-ttu-id="b04e7-115">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b04e7-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="b04e7-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b04e7-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
