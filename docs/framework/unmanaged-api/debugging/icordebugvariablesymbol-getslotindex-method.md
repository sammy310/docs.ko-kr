---
description: '자세히 알아보기: ICorDebugVariableSymbol:: GetSlotIndex 메서드'
title: ICorDebugVariableSymbol::GetSlotIndex 메서드
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3b5cba06a5e80ffa323d2e6521e9ec4666f6f5f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790557"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="9db4e-103">ICorDebugVariableSymbol::GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="9db4e-103">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>

<span data-ttu-id="9db4e-104">지역 변수의 관리되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9db4e-104">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db4e-105">구문</span><span class="sxs-lookup"><span data-stu-id="9db4e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9db4e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9db4e-106">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="9db4e-107">[out] 지역 변수의 슬롯 인덱스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9db4e-107">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9db4e-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="9db4e-108">Return Value</span></span>  

 <span data-ttu-id="9db4e-109">성공하는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="9db4e-109">`S_OK` if successful.</span></span> <span data-ttu-id="9db4e-110">변수가 함수 인수인 경우 `E_FAIL`입니다.</span><span class="sxs-lookup"><span data-stu-id="9db4e-110">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9db4e-111">설명</span><span class="sxs-lookup"><span data-stu-id="9db4e-111">Remarks</span></span>  

 <span data-ttu-id="9db4e-112">지역 변수의 관리되는 슬롯 인덱스를 사용하여 변수의 메타데이터 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db4e-112">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9db4e-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db4e-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9db4e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9db4e-114">Requirements</span></span>  

 <span data-ttu-id="9db4e-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9db4e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9db4e-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9db4e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9db4e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9db4e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9db4e-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9db4e-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db4e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9db4e-119">See also</span></span>

- [<span data-ttu-id="9db4e-120">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9db4e-120">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="9db4e-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9db4e-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
