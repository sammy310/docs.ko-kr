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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58c9d4c66af0bb9f4e66d17b18ac78ef8271bc31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072664"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="8be98-102">CodeChunkInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="8be98-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="8be98-103">메모리 내의 단일 코드 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8be98-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be98-104">구문</span><span class="sxs-lookup"><span data-stu-id="8be98-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="8be98-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8be98-105">Members</span></span>  
  
|<span data-ttu-id="8be98-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8be98-106">Member</span></span>|<span data-ttu-id="8be98-107">설명</span><span class="sxs-lookup"><span data-stu-id="8be98-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="8be98-108">`CORDB_ADDRESS` 청크의 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8be98-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="8be98-109">청크의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8be98-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8be98-110">설명</span><span class="sxs-lookup"><span data-stu-id="8be98-110">Remarks</span></span>  
 <span data-ttu-id="8be98-111">코드의 단일 청크는 함수 같은 코드 개체의 포함 된 네이티브 코드의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="8be98-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be98-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8be98-112">Requirements</span></span>  
 <span data-ttu-id="8be98-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8be98-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be98-114">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="8be98-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="8be98-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8be98-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8be98-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be98-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be98-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="8be98-117">See also</span></span>

- [<span data-ttu-id="8be98-118">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="8be98-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="8be98-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="8be98-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="8be98-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="8be98-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
