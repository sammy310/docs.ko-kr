---
description: '자세히 알아보기: ICorDebugInstanceFieldSymbol:: GetOffset 메서드'
title: ICorDebugInstanceFieldSymbol::GetOffset 메서드
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 4a877b2f78adfac5c54694ab306fd7db60f266f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791168"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="f10b6-103">ICorDebugInstanceFieldSymbol::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="f10b6-103">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>

<span data-ttu-id="f10b6-104">부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f10b6-104">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10b6-105">구문</span><span class="sxs-lookup"><span data-stu-id="f10b6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f10b6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f10b6-106">Parameters</span></span>  

 `pcbOffset`  
 <span data-ttu-id="f10b6-107">부모 클래스에서 이 인스턴스 필드가 오프셋되는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f10b6-107">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f10b6-108">설명</span><span class="sxs-lookup"><span data-stu-id="f10b6-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f10b6-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10b6-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f10b6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f10b6-110">Requirements</span></span>  

 <span data-ttu-id="f10b6-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f10b6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f10b6-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f10b6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f10b6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f10b6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f10b6-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f10b6-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10b6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f10b6-115">See also</span></span>

- [<span data-ttu-id="f10b6-116">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f10b6-116">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="f10b6-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f10b6-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
