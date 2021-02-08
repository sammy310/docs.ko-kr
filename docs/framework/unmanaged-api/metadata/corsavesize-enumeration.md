---
description: '자세히 알아보기: CorSaveSize 열거형'
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
ms.openlocfilehash: 47e2d4d77f58f8f1c2135da5867dfa47cedfd83d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784225"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="ab868-103">CorSaveSize 열거형</span><span class="sxs-lookup"><span data-stu-id="ab868-103">CorSaveSize Enumeration</span></span>

<span data-ttu-id="ab868-104">저장 작업의 크기를 쿼리할 때 필요한 전체 자릿수 수준을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab868-104">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab868-105">구문</span><span class="sxs-lookup"><span data-stu-id="ab868-105">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="ab868-106">구성원</span><span class="sxs-lookup"><span data-stu-id="ab868-106">Members</span></span>  
  
|<span data-ttu-id="ab868-107">멤버</span><span class="sxs-lookup"><span data-stu-id="ab868-107">Member</span></span>|<span data-ttu-id="ab868-108">설명</span><span class="sxs-lookup"><span data-stu-id="ab868-108">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="ab868-109">반환 값을 정확 하 게 지정 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab868-109">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="ab868-110">반환 값을 예상 값으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab868-110">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="ab868-111">삭제 가능한 형식을 제거 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab868-111">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab868-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab868-112">Requirements</span></span>  

 <span data-ttu-id="ab868-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab868-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab868-114">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="ab868-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ab868-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab868-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab868-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab868-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab868-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab868-117">See also</span></span>

- [<span data-ttu-id="ab868-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ab868-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
