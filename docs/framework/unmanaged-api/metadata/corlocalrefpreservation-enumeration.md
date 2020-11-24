---
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
ms.openlocfilehash: 49b0298f4fa776c93f89ac380ce65568b493379b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677117"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="89929-102">CorLocalRefPreservation 열거형</span><span class="sxs-lookup"><span data-stu-id="89929-102">CorLocalRefPreservation Enumeration</span></span>

<span data-ttu-id="89929-103">로컬 참조의 처리에 대한 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="89929-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89929-104">구문</span><span class="sxs-lookup"><span data-stu-id="89929-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="89929-105">멤버</span><span class="sxs-lookup"><span data-stu-id="89929-105">Members</span></span>  
  
|<span data-ttu-id="89929-106">멤버</span><span class="sxs-lookup"><span data-stu-id="89929-106">Member</span></span>|<span data-ttu-id="89929-107">설명</span><span class="sxs-lookup"><span data-stu-id="89929-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="89929-108">로컬 참조를 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89929-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="89929-109">로컬 형식 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="89929-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="89929-110">로컬 멤버 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="89929-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89929-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89929-111">Requirements</span></span>  

 <span data-ttu-id="89929-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89929-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89929-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="89929-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="89929-114">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89929-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89929-115">참조</span><span class="sxs-lookup"><span data-stu-id="89929-115">See also</span></span>

- [<span data-ttu-id="89929-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="89929-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
