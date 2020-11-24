---
title: ICorDebugStaticFieldSymbol::GetAddress 메서드
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: e9404b429ad4507acb5132a86af5f287dbcf07b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677286"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="2213f-102">ICorDebugStaticFieldSymbol::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="2213f-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>

<span data-ttu-id="2213f-103">정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2213f-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2213f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2213f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2213f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2213f-105">Parameters</span></span>  

 <span data-ttu-id="2213f-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="2213f-106">pRVA</span></span>  
 <span data-ttu-id="2213f-107">[out] 정적 필드의 RVA(상대 가상 주소)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2213f-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2213f-108">설명</span><span class="sxs-lookup"><span data-stu-id="2213f-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2213f-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2213f-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2213f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2213f-110">Requirements</span></span>  

 <span data-ttu-id="2213f-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2213f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2213f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2213f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2213f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2213f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2213f-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2213f-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2213f-115">참조</span><span class="sxs-lookup"><span data-stu-id="2213f-115">See also</span></span>

- [<span data-ttu-id="2213f-116">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2213f-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="2213f-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2213f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
