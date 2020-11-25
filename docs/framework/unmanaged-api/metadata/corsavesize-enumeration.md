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
ms.openlocfilehash: 81d47a3e4d72f991dc15924e7ff1ecc8df2e7322
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706059"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="52aad-102">CorSaveSize 열거형</span><span class="sxs-lookup"><span data-stu-id="52aad-102">CorSaveSize Enumeration</span></span>

<span data-ttu-id="52aad-103">저장 작업의 크기를 쿼리할 때 필요한 전체 자릿수 수준을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="52aad-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52aad-104">구문</span><span class="sxs-lookup"><span data-stu-id="52aad-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="52aad-105">멤버</span><span class="sxs-lookup"><span data-stu-id="52aad-105">Members</span></span>  
  
|<span data-ttu-id="52aad-106">멤버</span><span class="sxs-lookup"><span data-stu-id="52aad-106">Member</span></span>|<span data-ttu-id="52aad-107">설명</span><span class="sxs-lookup"><span data-stu-id="52aad-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="52aad-108">반환 값을 정확 하 게 지정 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52aad-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="52aad-109">반환 값을 예상 값으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52aad-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="52aad-110">삭제 가능한 형식을 제거 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52aad-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52aad-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52aad-111">Requirements</span></span>  

 <span data-ttu-id="52aad-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52aad-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52aad-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="52aad-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="52aad-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52aad-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52aad-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52aad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52aad-116">참조</span><span class="sxs-lookup"><span data-stu-id="52aad-116">See also</span></span>

- [<span data-ttu-id="52aad-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="52aad-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
