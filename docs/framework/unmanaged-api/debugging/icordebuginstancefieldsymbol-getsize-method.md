---
title: ICorDebugInstanceFieldSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081452"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="efa97-102">ICorDebugInstanceFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="efa97-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="efa97-103">인스턴스 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="efa97-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa97-104">구문</span><span class="sxs-lookup"><span data-stu-id="efa97-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efa97-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efa97-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="efa97-106">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="efa97-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efa97-107">설명</span><span class="sxs-lookup"><span data-stu-id="efa97-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efa97-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa97-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa97-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efa97-109">Requirements</span></span>  
 <span data-ttu-id="efa97-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="efa97-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa97-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efa97-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efa97-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efa97-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="efa97-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="efa97-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efa97-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="efa97-114">See also</span></span>

- [<span data-ttu-id="efa97-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efa97-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="efa97-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efa97-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
