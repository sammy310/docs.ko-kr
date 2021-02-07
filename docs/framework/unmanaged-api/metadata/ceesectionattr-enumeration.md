---
description: '자세히 알아보기: CeeSectionAttr 열거형'
title: CeeSectionAttr 열거형
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
ms.openlocfilehash: 13cfb635aaa606905745146d7c3caae3f9162e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678863"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="e9a55-103">CeeSectionAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="e9a55-103">CeeSectionAttr Enumeration</span></span>

<span data-ttu-id="e9a55-104">[ICeeGen](iceegen-interface.md) 인터페이스에서 사용할 섹션의 특성을 지정 하는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a55-104">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a55-105">구문</span><span class="sxs-lookup"><span data-stu-id="e9a55-105">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="e9a55-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e9a55-106">Members</span></span>  
  
|<span data-ttu-id="e9a55-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e9a55-107">Member</span></span>|<span data-ttu-id="e9a55-108">설명</span><span class="sxs-lookup"><span data-stu-id="e9a55-108">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="e9a55-109">섹션에는 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9a55-109">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="e9a55-110">섹션에는 업데이트 되지 않고 읽을 수만 있는 초기화 된 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9a55-110">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="e9a55-111">섹션에는 읽거나 업데이트할 수 있는 초기화 된 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9a55-111">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="e9a55-112">섹션에는 읽고 실행할 수 있는 실행 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9a55-112">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9a55-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9a55-113">Requirements</span></span>  

 <span data-ttu-id="e9a55-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9a55-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a55-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e9a55-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9a55-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9a55-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9a55-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a55-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a55-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9a55-118">See also</span></span>

- [<span data-ttu-id="e9a55-119">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e9a55-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
