---
description: '자세히 알아보기: ICorDebugVariableSymbol:: GetSize 메서드'
title: ICorDebugVariableSymbol::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: f4098bf5e053ab66dd7966d4b665cfad4dee01d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790583"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="70a3c-103">ICorDebugVariableSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="70a3c-103">ICorDebugVariableSymbol::GetSize Method</span></span>

<span data-ttu-id="70a3c-104">변수의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70a3c-104">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70a3c-105">구문</span><span class="sxs-lookup"><span data-stu-id="70a3c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70a3c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70a3c-106">Parameters</span></span>  

 `pcbValue`  
 <span data-ttu-id="70a3c-107">변수의 크기를 포함하는 32비트 부호 없는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70a3c-107">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70a3c-108">설명</span><span class="sxs-lookup"><span data-stu-id="70a3c-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70a3c-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70a3c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70a3c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70a3c-110">Requirements</span></span>  

 <span data-ttu-id="70a3c-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70a3c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70a3c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70a3c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70a3c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70a3c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70a3c-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70a3c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a3c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70a3c-115">See also</span></span>

- [<span data-ttu-id="70a3c-116">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70a3c-116">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="70a3c-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70a3c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
