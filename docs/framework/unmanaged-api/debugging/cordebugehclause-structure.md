---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 839e698c8921f916fad174bae4f4cc8bb4d02994
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609076"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="63aaf-102">CorDebugEHClause 구조</span><span class="sxs-lookup"><span data-stu-id="63aaf-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="63aaf-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="63aaf-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="63aaf-104">지정된 IL(중간 언어) 코드 부분에 대한 EH(예외 처리) 절을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63aaf-105">구문</span><span class="sxs-lookup"><span data-stu-id="63aaf-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="63aaf-106">멤버</span><span class="sxs-lookup"><span data-stu-id="63aaf-106">Members</span></span>  
  
|<span data-ttu-id="63aaf-107">멤버</span><span class="sxs-lookup"><span data-stu-id="63aaf-107">Member</span></span>|<span data-ttu-id="63aaf-108">설명</span><span class="sxs-lookup"><span data-stu-id="63aaf-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="63aaf-109">EH 절의 예외 정보를 설명하는 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="63aaf-110">자세한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63aaf-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="63aaf-111">메서드 본문 시작 지점부터 `try` 블록의 오프셋(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="63aaf-112">`try` 블록의 길이(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="63aaf-113">이 `try` 블록의 처리기 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="63aaf-114">처리기 코드의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="63aaf-115">형식 기반 예외 처리기의 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="63aaf-116">필터 기반 예외 처리기에 대한 메서드 본문 시작 지점부터의 오프셋(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63aaf-117">설명</span><span class="sxs-lookup"><span data-stu-id="63aaf-117">Remarks</span></span>  
 <span data-ttu-id="63aaf-118">배열을 `CoreDebugEHClause` 에서 반환 하는 값을 [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="63aaf-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="63aaf-119">EH 절 정보는 CLI 사양을 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="63aaf-120">자세한 내용은 참조 하세요. [표준 ECMA-355: Common Language Infrastructure (CLI), 여섯 번째 Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm)합니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="63aaf-121">`flags` 필드는 다음 플래그를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="63aaf-122">이러한 플래그는 CorDebug.idl 또는 CorDebug.h에서 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="63aaf-123">플래그</span><span class="sxs-lookup"><span data-stu-id="63aaf-123">Flag</span></span>|<span data-ttu-id="63aaf-124">값</span><span class="sxs-lookup"><span data-stu-id="63aaf-124">Value</span></span>|<span data-ttu-id="63aaf-125">설명</span><span class="sxs-lookup"><span data-stu-id="63aaf-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="63aaf-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="63aaf-126">0x00000000</span></span>|<span data-ttu-id="63aaf-127">형식이 지정된 예외 절입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="63aaf-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="63aaf-128">0x00000001</span></span>|<span data-ttu-id="63aaf-129">예외 필터 및 처리기 절입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="63aaf-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="63aaf-130">0x00000002</span></span>|<span data-ttu-id="63aaf-131">`finally` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="63aaf-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="63aaf-132">0x00000004</span></span>|<span data-ttu-id="63aaf-133">fault 절, 즉 예외가 throw될 때만 호출되는 `finally` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="63aaf-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63aaf-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63aaf-134">Requirements</span></span>  
 <span data-ttu-id="63aaf-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="63aaf-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63aaf-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63aaf-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63aaf-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63aaf-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63aaf-138">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63aaf-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63aaf-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="63aaf-139">See also</span></span>

- [<span data-ttu-id="63aaf-140">GetEHClauses 메서드</span><span class="sxs-lookup"><span data-stu-id="63aaf-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="63aaf-141">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="63aaf-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
