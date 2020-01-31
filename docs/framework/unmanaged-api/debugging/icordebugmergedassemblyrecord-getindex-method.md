---
title: ICorDebugMergedAssemblyRecord::GetIndex 메서드
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: c8fb5ace27fbf7fbebdaca5822af99cd6673e8cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793134"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="d2e6a-102">ICorDebugMergedAssemblyRecord::GetIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="d2e6a-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="d2e6a-103">어셈블리의 접두사 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2e6a-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2e6a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2e6a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2e6a-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="d2e6a-106">[out] 접두사 인덱스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2e6a-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2e6a-107">주의</span><span class="sxs-lookup"><span data-stu-id="d2e6a-107">Remarks</span></span>  
 <span data-ttu-id="d2e6a-108">접두사 인덱스는 병합된 메타데이터 형식 이름에서 이름 충돌을 방지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2e6a-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2e6a-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2e6a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2e6a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2e6a-110">Requirements</span></span>  
 <span data-ttu-id="d2e6a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2e6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2e6a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2e6a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2e6a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2e6a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2e6a-114">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2e6a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e6a-115">참조</span><span class="sxs-lookup"><span data-stu-id="d2e6a-115">See also</span></span>

- [<span data-ttu-id="d2e6a-116">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2e6a-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="d2e6a-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2e6a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
