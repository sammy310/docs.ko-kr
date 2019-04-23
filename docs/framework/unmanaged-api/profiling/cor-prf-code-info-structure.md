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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56734a9971759b78a835917c4914cf55edaa47a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103287"
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="15378-102">COR_PRF_CODE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="15378-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="15378-103">메모리 내에 저장된 연속하는 네이티브 코드 블록 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15378-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15378-104">구문</span><span class="sxs-lookup"><span data-stu-id="15378-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="15378-105">멤버</span><span class="sxs-lookup"><span data-stu-id="15378-105">Members</span></span>  
  
|<span data-ttu-id="15378-106">멤버</span><span class="sxs-lookup"><span data-stu-id="15378-106">Member</span></span>|<span data-ttu-id="15378-107">설명</span><span class="sxs-lookup"><span data-stu-id="15378-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="15378-108">연속 코드 블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="15378-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="15378-109">블록의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="15378-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15378-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15378-110">Requirements</span></span>  
 <span data-ttu-id="15378-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15378-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15378-112">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="15378-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="15378-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15378-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15378-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15378-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15378-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="15378-115">See also</span></span>

- [<span data-ttu-id="15378-116">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="15378-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
