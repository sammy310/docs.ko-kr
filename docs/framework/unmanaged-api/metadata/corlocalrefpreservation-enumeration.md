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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6338034d6714e8770e06ff61994fdf4433eb1684
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781784"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="ab764-102">CorLocalRefPreservation 열거형</span><span class="sxs-lookup"><span data-stu-id="ab764-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="ab764-103">로컬 참조의 처리에 대한 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab764-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab764-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab764-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="ab764-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ab764-105">Members</span></span>  
  
|<span data-ttu-id="ab764-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ab764-106">Member</span></span>|<span data-ttu-id="ab764-107">Description</span><span class="sxs-lookup"><span data-stu-id="ab764-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="ab764-108">없는 로컬 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab764-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="ab764-109">로컬 형식 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab764-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="ab764-110">로컬 멤버 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab764-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab764-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab764-111">Requirements</span></span>  
 <span data-ttu-id="ab764-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab764-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab764-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ab764-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ab764-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab764-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab764-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab764-115">See also</span></span>

- [<span data-ttu-id="ab764-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ab764-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
