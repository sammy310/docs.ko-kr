---
title: ICorDebugInstanceFieldSymbol::GetOffset 메서드
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 2d73de46bbb1023f20dd9023076630611c74be5d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724925"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="03048-102">ICorDebugInstanceFieldSymbol::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="03048-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>

<span data-ttu-id="03048-103">부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03048-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03048-104">구문</span><span class="sxs-lookup"><span data-stu-id="03048-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03048-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03048-105">Parameters</span></span>  

 `pcbOffset`  
 <span data-ttu-id="03048-106">부모 클래스에서 이 인스턴스 필드가 오프셋되는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03048-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03048-107">설명</span><span class="sxs-lookup"><span data-stu-id="03048-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03048-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03048-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03048-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03048-109">Requirements</span></span>  

 <span data-ttu-id="03048-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03048-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03048-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03048-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03048-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03048-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03048-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03048-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03048-114">참조</span><span class="sxs-lookup"><span data-stu-id="03048-114">See also</span></span>

- [<span data-ttu-id="03048-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03048-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="03048-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03048-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
