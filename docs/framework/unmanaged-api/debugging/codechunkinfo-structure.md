---
description: '자세히 알아보기: CodeChunkInfo Structure'
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
ms.openlocfilehash: 017a9ee8c608d4efae98eb0a342a3371ef8ec310
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712352"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="54517-103">CodeChunkInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="54517-103">CodeChunkInfo Structure</span></span>

<span data-ttu-id="54517-104">메모리 내의 단일 코드 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54517-104">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54517-105">구문</span><span class="sxs-lookup"><span data-stu-id="54517-105">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="54517-106">구성원</span><span class="sxs-lookup"><span data-stu-id="54517-106">Members</span></span>  
  
|<span data-ttu-id="54517-107">멤버</span><span class="sxs-lookup"><span data-stu-id="54517-107">Member</span></span>|<span data-ttu-id="54517-108">설명</span><span class="sxs-lookup"><span data-stu-id="54517-108">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="54517-109">`CORDB_ADDRESS`청크의 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="54517-109">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="54517-110">청크의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="54517-110">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54517-111">설명</span><span class="sxs-lookup"><span data-stu-id="54517-111">Remarks</span></span>  

 <span data-ttu-id="54517-112">코드의 단일 청크는 함수와 같은 코드 개체의 일부인 네이티브 코드의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="54517-112">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54517-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54517-113">Requirements</span></span>  

 <span data-ttu-id="54517-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54517-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54517-115">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="54517-115">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="54517-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54517-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54517-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54517-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54517-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54517-118">See also</span></span>

- [<span data-ttu-id="54517-119">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="54517-119">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="54517-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="54517-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="54517-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="54517-121">Debugging</span></span>](index.md)
