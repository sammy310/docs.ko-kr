---
title: CorSaveSize 열거형
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1e7bbac17d9a9ae191a5ad6d69b52a806383562
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781610"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="02d30-102">CorSaveSize 열거형</span><span class="sxs-lookup"><span data-stu-id="02d30-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="02d30-103">저장 작업의 크기를 쿼리할 때 필요한 전체 자릿수 수준을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="02d30-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d30-104">구문</span><span class="sxs-lookup"><span data-stu-id="02d30-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="02d30-105">멤버</span><span class="sxs-lookup"><span data-stu-id="02d30-105">Members</span></span>  
  
|<span data-ttu-id="02d30-106">멤버</span><span class="sxs-lookup"><span data-stu-id="02d30-106">Member</span></span>|<span data-ttu-id="02d30-107">설명</span><span class="sxs-lookup"><span data-stu-id="02d30-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="02d30-108">반환 값을 정확 하 게 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d30-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="02d30-109">반환 값을 예상 해야를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d30-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="02d30-110">삭제 가능한 형식 제거 해야 한다는 것을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d30-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02d30-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02d30-111">Requirements</span></span>  
 <span data-ttu-id="02d30-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="02d30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d30-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="02d30-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="02d30-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="02d30-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02d30-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d30-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="02d30-116">See also</span></span>

- [<span data-ttu-id="02d30-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="02d30-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
