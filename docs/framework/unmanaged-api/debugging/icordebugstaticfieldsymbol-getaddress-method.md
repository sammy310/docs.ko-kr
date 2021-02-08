---
description: '자세히 알아보기: ICorDebugStaticFieldSymbol:: GetAddress 메서드'
title: ICorDebugStaticFieldSymbol::GetAddress 메서드
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 1944839ff6afc31dc3667111397cbb088b95b412
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801009"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="b1474-103">ICorDebugStaticFieldSymbol::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="b1474-103">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>

<span data-ttu-id="b1474-104">정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1474-104">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1474-105">구문</span><span class="sxs-lookup"><span data-stu-id="b1474-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1474-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1474-106">Parameters</span></span>  

 <span data-ttu-id="b1474-107">pRVA</span><span class="sxs-lookup"><span data-stu-id="b1474-107">pRVA</span></span>  
 <span data-ttu-id="b1474-108">[out] 정적 필드의 RVA(상대 가상 주소)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1474-108">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1474-109">설명</span><span class="sxs-lookup"><span data-stu-id="b1474-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1474-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1474-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1474-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1474-111">Requirements</span></span>  

 <span data-ttu-id="b1474-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1474-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1474-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1474-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1474-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1474-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1474-115">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1474-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1474-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1474-116">See also</span></span>

- [<span data-ttu-id="b1474-117">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1474-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="b1474-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1474-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
