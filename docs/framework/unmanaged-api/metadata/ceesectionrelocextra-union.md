---
title: CeeSectionRelocExtra 공용 구조체
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: d11fefe220fdb00457cc48a6cd166673350be049
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006036"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="3cdd6-102">CeeSectionRelocExtra 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="3cdd6-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="3cdd6-103">[ICeeGen](iceegen-interface.md) 인터페이스에서 섹션의 위치를 다시 배치 하는 데 사용 되는 주소 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3cdd6-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cdd6-104">구문</span><span class="sxs-lookup"><span data-stu-id="3cdd6-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="3cdd6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3cdd6-105">Members</span></span>  
  
|<span data-ttu-id="3cdd6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3cdd6-106">Member</span></span>|<span data-ttu-id="3cdd6-107">설명</span><span class="sxs-lookup"><span data-stu-id="3cdd6-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="3cdd6-108">섹션에 대 한 상한 주소 조정입니다.</span><span class="sxs-lookup"><span data-stu-id="3cdd6-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3cdd6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3cdd6-109">Requirements</span></span>  
 <span data-ttu-id="3cdd6-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cdd6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cdd6-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3cdd6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3cdd6-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cdd6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3cdd6-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cdd6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdd6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cdd6-114">See also</span></span>

- [<span data-ttu-id="3cdd6-115">메타데이터 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="3cdd6-115">Metadata Unions</span></span>](metadata-unions.md)
