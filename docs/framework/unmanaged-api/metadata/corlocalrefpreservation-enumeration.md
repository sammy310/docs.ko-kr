---
description: '다음에 대 한 자세한 정보: CorLocalRefPreservation 열거'
title: CorLocalRefPreservation 열거형
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: afcdf6ce22c5f786e8f728cc1e45ad3ca44e7ef5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784420"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="49fa3-103">CorLocalRefPreservation 열거형</span><span class="sxs-lookup"><span data-stu-id="49fa3-103">CorLocalRefPreservation Enumeration</span></span>

<span data-ttu-id="49fa3-104">로컬 참조의 처리에 대한 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="49fa3-104">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49fa3-105">구문</span><span class="sxs-lookup"><span data-stu-id="49fa3-105">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="49fa3-106">구성원</span><span class="sxs-lookup"><span data-stu-id="49fa3-106">Members</span></span>  
  
|<span data-ttu-id="49fa3-107">멤버</span><span class="sxs-lookup"><span data-stu-id="49fa3-107">Member</span></span>|<span data-ttu-id="49fa3-108">설명</span><span class="sxs-lookup"><span data-stu-id="49fa3-108">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="49fa3-109">로컬 참조를 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49fa3-109">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="49fa3-110">로컬 형식 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fa3-110">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="49fa3-111">로컬 멤버 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fa3-111">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49fa3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49fa3-112">Requirements</span></span>  

 <span data-ttu-id="49fa3-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49fa3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49fa3-114">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="49fa3-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="49fa3-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49fa3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fa3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49fa3-116">See also</span></span>

- [<span data-ttu-id="49fa3-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="49fa3-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
