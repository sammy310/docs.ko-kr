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
ms.openlocfilehash: 845994b96445d8ec2a0e37affc5164b432894a91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102195"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="a7c81-102">CorLocalRefPreservation 열거형</span><span class="sxs-lookup"><span data-stu-id="a7c81-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="a7c81-103">로컬 참조의 처리에 대한 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c81-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7c81-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7c81-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="a7c81-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a7c81-105">Members</span></span>  
  
|<span data-ttu-id="a7c81-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a7c81-106">Member</span></span>|<span data-ttu-id="a7c81-107">설명</span><span class="sxs-lookup"><span data-stu-id="a7c81-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="a7c81-108">없는 로컬 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c81-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="a7c81-109">로컬 형식 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c81-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="a7c81-110">로컬 멤버 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c81-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7c81-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7c81-111">Requirements</span></span>  
 <span data-ttu-id="a7c81-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7c81-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7c81-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a7c81-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="a7c81-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a7c81-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7c81-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7c81-115">See also</span></span>

- [<span data-ttu-id="a7c81-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="a7c81-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
