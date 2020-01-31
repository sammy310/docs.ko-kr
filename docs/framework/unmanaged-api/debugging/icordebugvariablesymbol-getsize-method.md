---
title: ICorDebugVariableSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 6d60dbdefd09770fd5a18653c5118469323581e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790905"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="9af5d-102">ICorDebugVariableSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="9af5d-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="9af5d-103">변수의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9af5d-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9af5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9af5d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9af5d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9af5d-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="9af5d-106">변수의 크기를 포함하는 32비트 부호 없는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9af5d-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9af5d-107">주의</span><span class="sxs-lookup"><span data-stu-id="9af5d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9af5d-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af5d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9af5d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9af5d-109">Requirements</span></span>  
 <span data-ttu-id="9af5d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9af5d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9af5d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9af5d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9af5d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9af5d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9af5d-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9af5d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af5d-114">참조</span><span class="sxs-lookup"><span data-stu-id="9af5d-114">See also</span></span>

- [<span data-ttu-id="9af5d-115">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9af5d-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="9af5d-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9af5d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
