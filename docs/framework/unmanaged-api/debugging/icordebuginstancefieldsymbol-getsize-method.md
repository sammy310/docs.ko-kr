---
description: '자세히 알아보기: ICorDebugInstanceFieldSymbol:: GetSize 메서드'
title: ICorDebugInstanceFieldSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: fa143620b57ec053ab26ff79b7ea2b2f386431e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791155"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="bdcf2-103">ICorDebugInstanceFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="bdcf2-103">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="bdcf2-104">인스턴스 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-104">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdcf2-105">구문</span><span class="sxs-lookup"><span data-stu-id="bdcf2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdcf2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bdcf2-106">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="bdcf2-107">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-107">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdcf2-108">설명</span><span class="sxs-lookup"><span data-stu-id="bdcf2-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bdcf2-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdcf2-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bdcf2-110">Requirements</span></span>  

 <span data-ttu-id="bdcf2-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdcf2-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdcf2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdcf2-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdcf2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdcf2-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdcf2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdcf2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdcf2-115">See also</span></span>

- [<span data-ttu-id="bdcf2-116">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdcf2-116">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="bdcf2-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdcf2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
