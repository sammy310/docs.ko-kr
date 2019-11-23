---
title: COR_PRF_CODE_INFO 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
ms.openlocfilehash: 643c9d7104c374d9141a604083f3fdcd540156c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428394"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="f0c90-102">COR_PRF_CODE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="f0c90-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="f0c90-103">메모리 내에 저장된 연속하는 네이티브 코드 블록 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0c90-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c90-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0c90-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="f0c90-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f0c90-105">Members</span></span>  
  
|<span data-ttu-id="f0c90-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f0c90-106">Member</span></span>|<span data-ttu-id="f0c90-107">설명</span><span class="sxs-lookup"><span data-stu-id="f0c90-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="f0c90-108">The starting address of the contiguous block of code.</span><span class="sxs-lookup"><span data-stu-id="f0c90-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="f0c90-109">The size of the block.</span><span class="sxs-lookup"><span data-stu-id="f0c90-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0c90-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0c90-110">Requirements</span></span>  
 <span data-ttu-id="f0c90-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c90-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c90-112">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f0c90-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f0c90-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0c90-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0c90-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c90-115">참조</span><span class="sxs-lookup"><span data-stu-id="f0c90-115">See also</span></span>

- [<span data-ttu-id="f0c90-116">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="f0c90-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
