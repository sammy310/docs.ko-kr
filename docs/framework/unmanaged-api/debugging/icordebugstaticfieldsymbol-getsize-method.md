---
title: ICorDebugStaticFieldSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: 34567247935588363d96b141717d7ec07bb76546
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677212"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="7be88-102">ICorDebugStaticFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="7be88-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="7be88-103">정적 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7be88-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be88-104">구문</span><span class="sxs-lookup"><span data-stu-id="7be88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be88-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7be88-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="7be88-106">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7be88-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be88-107">설명</span><span class="sxs-lookup"><span data-stu-id="7be88-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7be88-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be88-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be88-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7be88-109">Requirements</span></span>  

 <span data-ttu-id="7be88-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7be88-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be88-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7be88-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7be88-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be88-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be88-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be88-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be88-114">참조</span><span class="sxs-lookup"><span data-stu-id="7be88-114">See also</span></span>

- [<span data-ttu-id="7be88-115">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7be88-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="7be88-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7be88-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
