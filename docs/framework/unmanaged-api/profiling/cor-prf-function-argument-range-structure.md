---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dffefedf14d5f219736e429be191021b2de7ddd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125595"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="16d4b-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="16d4b-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="16d4b-103">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16d4b-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d4b-104">구문</span><span class="sxs-lookup"><span data-stu-id="16d4b-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="16d4b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="16d4b-105">Members</span></span>  
  
|<span data-ttu-id="16d4b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="16d4b-106">Members</span></span>|<span data-ttu-id="16d4b-107">설명</span><span class="sxs-lookup"><span data-stu-id="16d4b-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="16d4b-108">블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="16d4b-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="16d4b-109">인접 한 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="16d4b-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16d4b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16d4b-110">Requirements</span></span>  
 <span data-ttu-id="16d4b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16d4b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d4b-112">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="16d4b-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="16d4b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16d4b-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="16d4b-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="16d4b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16d4b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="16d4b-115">See also</span></span>

- [<span data-ttu-id="16d4b-116">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="16d4b-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
