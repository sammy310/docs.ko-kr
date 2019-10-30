---
title: CodeChunkInfo 구조체
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132394"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="ad60f-102">CodeChunkInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="ad60f-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="ad60f-103">메모리 내의 단일 코드 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad60f-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad60f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad60f-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="ad60f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ad60f-105">Members</span></span>  
  
|<span data-ttu-id="ad60f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ad60f-106">Member</span></span>|<span data-ttu-id="ad60f-107">설명</span><span class="sxs-lookup"><span data-stu-id="ad60f-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="ad60f-108">청크의 시작 주소를 지정 하는 `CORDB_ADDRESS` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad60f-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="ad60f-109">청크의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ad60f-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad60f-110">주의</span><span class="sxs-lookup"><span data-stu-id="ad60f-110">Remarks</span></span>  
 <span data-ttu-id="ad60f-111">코드의 단일 청크는 함수와 같은 코드 개체의 일부인 네이티브 코드의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="ad60f-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad60f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad60f-112">Requirements</span></span>  
 <span data-ttu-id="ad60f-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad60f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad60f-114">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="ad60f-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="ad60f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad60f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad60f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad60f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad60f-117">참조</span><span class="sxs-lookup"><span data-stu-id="ad60f-117">See also</span></span>

- [<span data-ttu-id="ad60f-118">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="ad60f-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="ad60f-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="ad60f-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ad60f-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="ad60f-120">Debugging</span></span>](index.md)
