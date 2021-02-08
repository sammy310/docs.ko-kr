---
description: '자세히 알아보기: CorDebugEHClause Structure'
title: CorDebugEHClause 구조
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: ecb00e2a110719ab82de32fb1f1c861e2033a528
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801672"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="eef8f-103">CorDebugEHClause 구조</span><span class="sxs-lookup"><span data-stu-id="eef8f-103">CorDebugEHClause Structure</span></span>

<span data-ttu-id="eef8f-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="eef8f-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="eef8f-105">지정된 IL(중간 언어) 코드 부분에 대한 EH(예외 처리) 절을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-105">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef8f-106">구문</span><span class="sxs-lookup"><span data-stu-id="eef8f-106">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="eef8f-107">구성원</span><span class="sxs-lookup"><span data-stu-id="eef8f-107">Members</span></span>  
  
|<span data-ttu-id="eef8f-108">멤버</span><span class="sxs-lookup"><span data-stu-id="eef8f-108">Member</span></span>|<span data-ttu-id="eef8f-109">설명</span><span class="sxs-lookup"><span data-stu-id="eef8f-109">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="eef8f-110">EH 절의 예외 정보를 설명하는 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-110">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="eef8f-111">자세한 내용은 주의 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eef8f-111">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="eef8f-112">메서드 본문 시작 지점부터 `try` 블록의 오프셋(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-112">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="eef8f-113">`try` 블록의 길이(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-113">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="eef8f-114">이 `try` 블록의 처리기 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-114">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="eef8f-115">처리기 코드의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-115">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="eef8f-116">형식 기반 예외 처리기의 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-116">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="eef8f-117">필터 기반 예외 처리기에 대한 메서드 본문 시작 지점부터의 오프셋(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-117">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eef8f-118">설명</span><span class="sxs-lookup"><span data-stu-id="eef8f-118">Remarks</span></span>  

 <span data-ttu-id="eef8f-119">`CoreDebugEHClause` [GetEHClauses](icordebugilcode-getehclauses-method.md) 메서드에서 값의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-119">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="eef8f-120">EH 절 정보는 CLI 사양을 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-120">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="eef8f-121">자세한 내용은 [표준 ECMA-355: Common Language Infrastructure (CLI), 6 번째 버전](https://www.ecma-international.org/publications/standards/Ecma-335.htm)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eef8f-121">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="eef8f-122">`flags` 필드는 다음 플래그를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-122">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="eef8f-123">이러한 플래그는 CorDebug.idl 또는 CorDebug.h에서 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-123">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="eef8f-124">플래그</span><span class="sxs-lookup"><span data-stu-id="eef8f-124">Flag</span></span>|<span data-ttu-id="eef8f-125">값</span><span class="sxs-lookup"><span data-stu-id="eef8f-125">Value</span></span>|<span data-ttu-id="eef8f-126">설명</span><span class="sxs-lookup"><span data-stu-id="eef8f-126">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="eef8f-127">0x00000000</span><span class="sxs-lookup"><span data-stu-id="eef8f-127">0x00000000</span></span>|<span data-ttu-id="eef8f-128">형식이 지정된 예외 절입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-128">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="eef8f-129">0x00000001</span><span class="sxs-lookup"><span data-stu-id="eef8f-129">0x00000001</span></span>|<span data-ttu-id="eef8f-130">예외 필터 및 처리기 절입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-130">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="eef8f-131">0x00000002</span><span class="sxs-lookup"><span data-stu-id="eef8f-131">0x00000002</span></span>|<span data-ttu-id="eef8f-132">`finally` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-132">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="eef8f-133">0x00000004</span><span class="sxs-lookup"><span data-stu-id="eef8f-133">0x00000004</span></span>|<span data-ttu-id="eef8f-134">fault 절, 즉 예외가 throw될 때만 호출되는 `finally` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="eef8f-134">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eef8f-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eef8f-135">Requirements</span></span>  

 <span data-ttu-id="eef8f-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eef8f-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eef8f-137">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eef8f-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eef8f-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eef8f-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eef8f-139">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eef8f-139">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef8f-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eef8f-140">See also</span></span>

- [<span data-ttu-id="eef8f-141">GetEHClauses 메서드</span><span class="sxs-lookup"><span data-stu-id="eef8f-141">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="eef8f-142">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="eef8f-142">Debugging Structures</span></span>](debugging-structures.md)
