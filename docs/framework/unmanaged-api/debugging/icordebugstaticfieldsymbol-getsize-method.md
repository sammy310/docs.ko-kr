---
description: '자세히 알아보기: ICorDebugStaticFieldSymbol:: GetSize 메서드'
title: ICorDebugStaticFieldSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: f6fd2fe60d7cb8a77dcff5ca259d05ae1ef195ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794691"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="57f5a-103">ICorDebugStaticFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="57f5a-103">ICorDebugStaticFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="57f5a-104">정적 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57f5a-104">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f5a-105">구문</span><span class="sxs-lookup"><span data-stu-id="57f5a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57f5a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57f5a-106">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="57f5a-107">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="57f5a-107">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57f5a-108">설명</span><span class="sxs-lookup"><span data-stu-id="57f5a-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57f5a-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f5a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57f5a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57f5a-110">Requirements</span></span>  

 <span data-ttu-id="57f5a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57f5a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57f5a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57f5a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57f5a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57f5a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57f5a-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57f5a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f5a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57f5a-115">See also</span></span>

- [<span data-ttu-id="57f5a-116">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57f5a-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="57f5a-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57f5a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
