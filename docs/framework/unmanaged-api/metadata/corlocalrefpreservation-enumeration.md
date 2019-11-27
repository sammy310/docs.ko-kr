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
ms.openlocfilehash: 706ea37101f9f961e92d8cef2cf508c1dd0d56c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450249"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="dd113-102">CorLocalRefPreservation 열거형</span><span class="sxs-lookup"><span data-stu-id="dd113-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="dd113-103">로컬 참조의 처리에 대한 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dd113-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd113-104">구문</span><span class="sxs-lookup"><span data-stu-id="dd113-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="dd113-105">멤버</span><span class="sxs-lookup"><span data-stu-id="dd113-105">Members</span></span>  
  
|<span data-ttu-id="dd113-106">멤버</span><span class="sxs-lookup"><span data-stu-id="dd113-106">Member</span></span>|<span data-ttu-id="dd113-107">설명</span><span class="sxs-lookup"><span data-stu-id="dd113-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="dd113-108">로컬 참조를 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd113-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="dd113-109">로컬 형식 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd113-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="dd113-110">로컬 멤버 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd113-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd113-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd113-111">Requirements</span></span>  
 <span data-ttu-id="dd113-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd113-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd113-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="dd113-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="dd113-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd113-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd113-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd113-115">See also</span></span>

- [<span data-ttu-id="dd113-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="dd113-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
