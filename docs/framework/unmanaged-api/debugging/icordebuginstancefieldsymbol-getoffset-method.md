---
title: ICorDebugInstanceFieldSymbol::GetOffset 메서드
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3073abb3b9a44cccba323f282859c97c96bdf91d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760100"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="24404-102">ICorDebugInstanceFieldSymbol::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="24404-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="24404-103">부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24404-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24404-104">구문</span><span class="sxs-lookup"><span data-stu-id="24404-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24404-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24404-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="24404-106">부모 클래스에서 이 인스턴스 필드가 오프셋되는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24404-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24404-107">설명</span><span class="sxs-lookup"><span data-stu-id="24404-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24404-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24404-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24404-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24404-109">Requirements</span></span>  
 <span data-ttu-id="24404-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="24404-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24404-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24404-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24404-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24404-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24404-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24404-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24404-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="24404-114">See also</span></span>

- [<span data-ttu-id="24404-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24404-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="24404-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24404-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
