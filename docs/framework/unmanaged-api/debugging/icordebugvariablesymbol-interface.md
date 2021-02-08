---
description: '자세히 알아보기: ICorDebugVariableSymbol 인터페이스'
title: ICorDebugVariableSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: fa3fc1f318627e9175a3066c3bd3eac00929ea60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790544"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="945e8-103">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="945e8-103">ICorDebugVariableSymbol Interface</span></span>

<span data-ttu-id="945e8-104">변수에 대한 디버그 기호 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-104">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="945e8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="945e8-105">Methods</span></span>  
  
|<span data-ttu-id="945e8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="945e8-106">Method</span></span>|<span data-ttu-id="945e8-107">설명</span><span class="sxs-lookup"><span data-stu-id="945e8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="945e8-108">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="945e8-108">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="945e8-109">변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-109">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="945e8-110">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="945e8-110">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="945e8-111">변수의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-111">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="945e8-112">GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="945e8-112">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="945e8-113">지역 변수의 관리되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-113">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="945e8-114">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="945e8-114">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="945e8-115">변수의 값을 바이트 배열로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-115">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="945e8-116">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="945e8-116">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="945e8-117">바이트 배열의 값을 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-117">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="945e8-118">설명</span><span class="sxs-lookup"><span data-stu-id="945e8-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="945e8-119">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-119">This interface is available with .NET Native only.</span></span> <span data-ttu-id="945e8-120">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="945e8-120">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="945e8-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="945e8-121">Requirements</span></span>  

 <span data-ttu-id="945e8-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="945e8-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="945e8-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="945e8-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="945e8-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="945e8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="945e8-125">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="945e8-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945e8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="945e8-126">See also</span></span>

- [<span data-ttu-id="945e8-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="945e8-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="945e8-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="945e8-128">Debugging</span></span>](index.md)
