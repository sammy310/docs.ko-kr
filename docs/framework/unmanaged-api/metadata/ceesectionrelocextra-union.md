---
description: CeeSectionRelocExtra 공용 구조체에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 40001c1a0772e24633f4232da8e7817f3747f8ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678850"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="13883-103">CeeSectionRelocExtra 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="13883-103">CeeSectionRelocExtra Union</span></span>

<span data-ttu-id="13883-104">[ICeeGen](iceegen-interface.md) 인터페이스에서 섹션의 위치를 다시 배치 하는 데 사용 되는 주소 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13883-104">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13883-105">구문</span><span class="sxs-lookup"><span data-stu-id="13883-105">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="13883-106">구성원</span><span class="sxs-lookup"><span data-stu-id="13883-106">Members</span></span>  
  
|<span data-ttu-id="13883-107">멤버</span><span class="sxs-lookup"><span data-stu-id="13883-107">Member</span></span>|<span data-ttu-id="13883-108">설명</span><span class="sxs-lookup"><span data-stu-id="13883-108">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="13883-109">섹션에 대 한 상한 주소 조정입니다.</span><span class="sxs-lookup"><span data-stu-id="13883-109">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13883-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13883-110">Requirements</span></span>  

 <span data-ttu-id="13883-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13883-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13883-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="13883-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13883-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13883-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13883-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13883-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13883-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13883-115">See also</span></span>

- [<span data-ttu-id="13883-116">메타데이터 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="13883-116">Metadata Unions</span></span>](metadata-unions.md)
