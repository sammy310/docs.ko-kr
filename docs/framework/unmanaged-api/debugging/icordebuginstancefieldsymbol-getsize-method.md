---
title: ICorDebugInstanceFieldSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: c4b193b45e30b0eba3367f18cb1e4c2b4e108fa8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724912"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="55e12-102">ICorDebugInstanceFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="55e12-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="55e12-103">인스턴스 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="55e12-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e12-104">구문</span><span class="sxs-lookup"><span data-stu-id="55e12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e12-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55e12-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="55e12-106">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="55e12-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55e12-107">설명</span><span class="sxs-lookup"><span data-stu-id="55e12-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55e12-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55e12-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e12-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55e12-109">Requirements</span></span>  

 <span data-ttu-id="55e12-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55e12-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e12-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55e12-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55e12-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55e12-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55e12-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e12-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e12-114">참조</span><span class="sxs-lookup"><span data-stu-id="55e12-114">See also</span></span>

- [<span data-ttu-id="55e12-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55e12-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="55e12-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55e12-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
