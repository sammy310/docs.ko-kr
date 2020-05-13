---
title: ICorDebugInstanceFieldSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 3d3c6881ecd54fc48be92e5ea0dc74a5cfdabd8f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209955"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="7921e-102">ICorDebugInstanceFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="7921e-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="7921e-103">인스턴스 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7921e-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7921e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7921e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7921e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7921e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="7921e-106">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7921e-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7921e-107">설명</span><span class="sxs-lookup"><span data-stu-id="7921e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7921e-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7921e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7921e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7921e-109">Requirements</span></span>  
 <span data-ttu-id="7921e-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7921e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7921e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7921e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7921e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7921e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7921e-113">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7921e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7921e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7921e-114">See also</span></span>

- [<span data-ttu-id="7921e-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7921e-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="7921e-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7921e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
