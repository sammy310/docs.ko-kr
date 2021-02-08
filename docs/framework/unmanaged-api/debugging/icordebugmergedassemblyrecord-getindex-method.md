---
description: '자세히 알아보기: ICorDebugMergedAssemblyRecord:: GetIndex 메서드'
title: ICorDebugMergedAssemblyRecord::GetIndex 메서드
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: f3a51c5ed5edacc9678c965ac385d0969e2ee8a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801113"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="7c1dc-103">ICorDebugMergedAssemblyRecord::GetIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="7c1dc-103">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>

<span data-ttu-id="7c1dc-104">어셈블리의 접두사 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c1dc-104">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1dc-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c1dc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c1dc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c1dc-106">Parameters</span></span>  

 `pIndex`  
 <span data-ttu-id="7c1dc-107">[out] 접두사 인덱스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1dc-107">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c1dc-108">설명</span><span class="sxs-lookup"><span data-stu-id="7c1dc-108">Remarks</span></span>  

 <span data-ttu-id="7c1dc-109">접두사 인덱스는 병합된 메타데이터 형식 이름에서 이름 충돌을 방지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1dc-109">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c1dc-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1dc-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c1dc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c1dc-111">Requirements</span></span>  

 <span data-ttu-id="7c1dc-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c1dc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c1dc-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c1dc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c1dc-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c1dc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c1dc-115">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c1dc-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1dc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c1dc-116">See also</span></span>

- [<span data-ttu-id="7c1dc-117">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c1dc-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="7c1dc-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c1dc-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
